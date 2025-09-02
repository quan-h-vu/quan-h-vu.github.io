---
date: '2025-08-28T11:20:51-07:00'
draft: true
title: 'Concept: Behavioral Change Score'
description: "This sample explains the algorithm behind a complex metric in a road safety program."
# image: ""
lastmod: 2025-08-28
tags: ["concept","MadCap Flare","PowerPoint"]
type: "post"
showTableOfContents: true
---

## About The Sample

The sample below explains the algorithm behind a complex metric in a road safety program. This metric is used to gauge managers' performance in training their drivers on safe driving habits.

This document has been anonymized for portfolio purposes. Company names, personal identifiers, and specific implementation details have been modified. This was originally drafted using MadCap Flare. The timeline graphics and equations were produced with Microsoft PowerPoint. I have recreated it here with Markdown and PowerPoint.

| Criteria | Description                                        |
|----------|----------------------------------------------------|
| Tools    | MadCap Flare, Microsoft PowerPoint                 |
| SMEs     | product manager, database engineers, data analysts |
| Others   | none                                               |

The sample begins below the line.

---

The Behavioral Change Score helps gauge managers' performance in training their drivers. The score is built on the premise that if drivers are trained effectively on a specific behavior, they should be less likely to repeat that behavior. The score compares the number of behaviors a manager has coached ("Targeted Behaviors") with the number of behaviors their drivers have repeated ("Recurring Behaviors"). In addition, Recurring Behaviors are weighted by their ages (Behavior Age); as time passes, older instances of Recurring Behaviors are weighted less heavily than recent instances.

![Behavioral Change Score equation](/content/samples/CEscore/BCSequation.png)

## Basics

To understand the score, we'll use a training scenario. Refer to the chart below while following the scenario as it tracks how the manager's Behavioral Change Score fluctuates throughout.

![Line graph showing Behavioral Change Score in the given scenario](/content/samples/CEscore/BCSoverview.png)

1. February 15: Driver Jake uses his cell phone while driving, triggering an incident report. His manager, Holt, sees the incident in the Fleet Safety System. He calls Jake to address the behavior.
2. February 28: Unfortunately, Jake once again uses his cell phone while driving. The recurrence now impacts Holt's Behavioral Change Score, showing that the training wasn't effective.
3. March 1: Holt sees the recurrence and conducts another training session with Jake to further understand his situation and to provide support. With the additional training session, Holt's Behavioral Change Score now improves.
4. April 4: Jake hasn't triggered another 'Phone Usage' incident for 35 days, indicating that the training had a positive effect. During this period, Holt's Behavioral Change Score rises steadily.
5. May 12: Jake uses his phone again while driving. Holt's Behavioral Change Score drops.
6. May 15: Holt trains Jake after the latest recurrence. With the additional training, Holt's Behavioral Change Score improves.

Note that the Targeted Behavior continues to count favorably towards Holt's Behavioral Change Score until the last associated Recurring Behavior (from May 12) becomes older than 90 days.

### Behaviors Included

By default, only behaviors on your organization's Flagged Behaviors list are included in the Behavioral Change Score.

However, if a manager decides to train an unflagged behavior—for example, they decide an FYI status incident requires training—that behavior now becomes flagged on that particular incident and that incident counts towards the Behavioral Change Score. But if the driver repeats the behavior again afterward, the new incident must also be turned from FYI status to Training status for it to count in the score. If the incident remains in FYI status, it would not count.

### Targeted Behaviors

Targeted Behaviors are defined by behavior, driver, and the training date.

- If multiple behaviors are addressed in one training session, each is counted separately.
- If multiple drivers are trained on the same behavior, each is counted separately.
- If multiple events with the same behavior are addressed in one session (i.e. bulk training), they count as one Targeted Behavior. Any recurrences are counted as just one Recurring Behavior.
- If a driver is trained multiple times in the same day on the same behavior, that is counted together as one Targeted Behavior. Any recurrences are counted as just one Recurring Behavior.

### Recurring Behaviors

- A Recurring Behavior occurs when a driver repeats a behavior that was targeted for training within the past 90 days.
- A behavior is considered a recurrence as soon as the behavior is applied in incident review.
- Each Recurring Behavior is tied to at least one Targeted Behavior in the past. If the driver has not yet received training for a behavior, this is not considered a recurrence. If the driver received training for a behavior BUT the training occurred over 90 days ago, this is also not considered a recurrence.

### Behavior Age Impact

The age of the Recurring Behavior determines its impact. If the behavior was repeated today, it retains its full weight. In 45 days, it will be weighted at 50%. In 90 days, it will be weighted at 0%, at which point it stops affecting the Behavioral Change Score.

![Chart showing Behavior Age impact](/content/samples/CEscore/BCSage.png)

## Advanced Scenarios

### The Effect of Multiple Recurring Behaviors

If the driver Jake uses his cell phone while driving multiple times after Holt has coached him, each repetition counts separately. This situation indicates that Jake may have received less effective training than a driver who repeated that behavior just once after training. In the diagram below, the yellow indicates the period after coaching during which 'Phone Usage' events would qualify as Recurring Behaviors.

![Chart showing the effect of multiple Recurring Behaviors](/content/samples/CEscore/BCSmulti1.png)

When the first Recurring Behavior becomes older than 90 days, it drops out of the score. However, because the second Recurring Behavior is still less than 90 days old, it still counts. And because that second recurrence is within the qualifying period of the Targeted Behavior, the Targeted Behavior also still counts in favor of Holt.

![Chart showing the effect of multiple Recurring Behaviors](/content/samples/CEscore/BCSmulti2.png)