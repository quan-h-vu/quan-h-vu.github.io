---
date: 2025-03-25T09:58:04-07:00
description: "Writing abounds at all levels of any organization. Often, it's created by non-writers who just happen to write at times. For these non-writers, here are my tips to help communicate more effectively."
# image: ""
lastmod: 2025-03-25
showTableOfContents: false
# tags: ["collaboration",]
title: "Writing Tips for Non-Writers"
type: "post"
draft: true
showTableOfContents: true
---

I have spent much of my technical writing career as a "team-of-one" writer. One lesson I've learned is that, even when I'm the only technical writer at a company, I'm not the only one making documentation. People all around the company are developing content to serve various needs. Consider the following examples.

- Product managers write Jira stories to communicate acceptance criteria to engineers.
- Engineers document their development decisions to promote consistency.
- Technical support leads write troubleshooting articles and scripts for specific scenarios.
- Account managers answer client questions via email.

Writing abounds at all levels of any organization. Sometimes, content is created by professional writers. But often, it's created by non-writers who just happen to write for their profession at times. For these non-writers, here are my writing tips to help you communicate more effectively.

## Write for Scanning

People like to say that no one reads but that's not strictly true. No one reads *thoroughly*, at least not initially. They scan. Their eyes skim text, looking for evidence of the information they desire. If they detect something, then they slow down and read a certain portion more thoroughly.

As a writer, one of your goals is to facilitate the visual scanning of text. You can accomplish this in many ways.

- **Sections and headings**: Break up content into logical sections with descriptive headings (the title also counts as a type of heading). Users typically look to headings first to guide their search for information. Craft accurate, concise headings to help users decide quickly if a section of the document is relevant to them. 
- **Lists and tables**: Use lists and tables frequently. Lists and tables are highly organized forms of information, making them easy to scan.
- **Graphics and screenshots**: Include graphics and screenshots that aid comprehension. Some examples include screenshots/mockups of software, line drawings of hardware, and workflow diagrams.
- **Table of contents**: For longer documents, a table of contents can give users an overview of the document and let them quickly jump to various sections.

## Organize by Importance

Another way to facilitate scanning is to organize information by importance, leading with the most important information. In journalism, this is known as the inverted pyramid method.

![Inverted pyramid diagram](https://typewriter.media/wp-content/uploads/2020/09/Inverted-Pyramid-Style-of-Writing.jpg)

[With the inverted pyramid method](https://www.nngroup.com/articles/inverted-pyramid/), you assume that readers are busy, busy enough that they can and will be interrupted midway through reading your article. Maybe a more urgent issue takes their attention away. Maybe they just arrive at their bus stop. If they are scanning text, they may "interrupt" themselves to jump to another part of the document.

As a writer, one of your goals is to organize information such that, when readers inevitably get interrupted, they still learn the most important details. This applies on a micro level, meaning within each section or paragraph, details should be organized by importance. This also applies on a macro level, meaning the sections and paragraphs of a document should be organized by importance.

### Example: Organizing a Paragraph

As an example, consider the following introduction paragraph from [one of my own samples](/samples/hww).

> The AM2 model of hazard identification is designed to reward reactive drivers. The model integrates audio alerts and incident logs into a cohesive system of escalation. Audio alerts allow drivers to correct their own driving behavior; an incident log is only generated as the next level of escalation if they fail to react. Even further, prevention logs are generated for reactive drivers, giving managers an opportunity to recognize them.

Let's edit this to see how the organization of details affects reading. Let's re-organize the information, moving the first two sentences to the back.

>  With the AM2 model of hazard identification, audio alerts allow drivers to correct their own driving behavior; an incident log is only generated as the next level of escalation if they fail to react. Even further, prevention logs are generated for reactive drivers, giving managers an opportunity to recognize them. This model is designed to reward reactive drivers. It integrates audio alerts and incident logs into a cohesive system of escalation.

Both versions make sense. They both communicate the same information. Taken in full, both versions are nearly identical.

Now, imagine our reader is interrupted. Because of this, they're only able to catch the first 160 characters of the paragraph.

With the original paragraph, the reader catches this excerpt:

> The AM2 model of hazard identification is designed to reward reactive drivers. The model integrates audio alerts and incident logs into a cohesive system of esc...

With the edited paragraph, the reader catches this excerpt:

> With the AM2 model of hazard identification, audio alerts allow drivers to correct their own driving behavior; an incident log is only generated as the next lev...

The main difference between these excerpts is the mention of a reward for reactive drivers. Readers of the edited excerpt would miss this important detail completely. The original paragraph leads with this detail to give it the best chance of being seen.

## Remove Clutter

The details you decide to exclude from your document are almost as important as the details you decide to include. This is similar to the idea of clutter in UX design.

In UX, designers are often tasked with [reducing visual clutter from designs](https://www.lionandmason.com/ux-blog/reducing-cognitive-overload-declutter-your-design-for-better-ux/). The idea is that clutter distracts users, slowing them down from achieving their user goals.

In writing, details that are unimportant can be seen as clutter. Every unimportant detail is a chance to distract readers. By removing unimportant details, readers can more easily focus on the important details.

As an example, consider this section from [one of my own samples](/samples/hww). This section details how a fictional dashcam product detects instances of tailgating on the road:

> 1. During a trip, the camera scans the road for the object vehicle in front of the driver's vehicle. It uses the driver's vehicle speed to calculate the distance in terms of seconds.
> 2. The camera issues an audio alert when the distance between the driver's vehicle and the object vehicle is 1.0 seconds or less for 10 continuous seconds (min. speed: 40 km/h).
> 3. If the driver's vehicle continues to meet the HWW criteria, the camera repeats the audio alert every 5 seconds.
> 4. If the driver's vehicle meets the HWW criteria for 25 continuous seconds, an [incident log](/samples/hww "timeline of incident progression from first alert") is generated. Conversely, if the driver's vehicle stops meeting the HWW criteria before the 25-second threshold, a [prevention log](/samples/hww "timeline of incident progression and resolution") is generated.
> 5. After generating a log, the timer for HWW identification is reset. 
> 6. At the end of the trip, all logs are sent to users in the Drivecast online portal.

Step 4 above uses two unique terms, "incident logs" and "prevention logs." In the version above, they are linked to a different resource, a glossary.

However, if you wanted to keep readers on the page rather than sending them to a different page, you could add term definitions directly into the text. Consider this edited version:

> 1. During a trip, the camera scans the road for the object vehicle in front of the driver's vehicle. It uses the driver's vehicle speed to calculate the distance in terms of seconds.
> 2. The camera issues an audio alert when the distance between the driver's vehicle and the object vehicle is 1.0 seconds or less for 10 continuous seconds (min. speed: 40 km/h).
> 3. If the driver's vehicle continues to meet the HWW criteria, the camera repeats the audio alert every 5 seconds.
> 4. If the driver's vehicle meets the HWW criteria for 25 continuous seconds, an incident log (a timeline of incident progression from first alert) is generated. Conversely, if the driver's vehicle stops meeting the HWW criteria before the 25-second threshold, a prevention log (a timeline of incident progression and resolution) is generated.
> 5. After generating a log, the timer for HWW identification is reset. 
> 6. At the end of the trip, all logs are sent to users in the Drivecast online portal.




Maybe try the Hazard ID section instead. Explain why I didn't explain incident logs/prevention logs.