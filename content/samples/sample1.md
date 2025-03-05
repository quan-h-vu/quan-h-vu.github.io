+++
date = '2025-02-18T16:34:16-08:00'
draft = false
title = 'Success Story: Internal Release Notes template'
type = 'post'
description = 'I led an initiative to improve our internal release notes template. This story highlights my leadership and expertise in content strategy.'
tags = ['release notes','content strategy','leadership']
weight = 10
+++

I led an initiative to improve our internal release notes template. This story highlights my leadership and expertise in content strategy.

## Problem Addressed

Product managers were responsible for providing internal release notes to operations teams to allow them to prepare for upcoming releases. However, some teams expressed dissatisfaction with the lack of detail. Some even admitted they stopped reading the release notes because of this.

The PMs themselves were also frustrated because they used the release notes to communicate important information. But they still received questions on details addressed in the release notes.

I investigated the issue. In my analysis, I concluded that the existing template for each release item was too vague. This didn’t cause vague release notes directly. But the level of detail and writing quality varied widely between PMs. The inconsistency discouraged users from reading the release notes on a regular basis.

## Solution Implemented

I crafted a new template calling for more specific information. Rather than one generalized ‘Description’ field, I created separate fields for:

- Problem Addressed
- Solution Implemented
- Why It Matters to Clients

To finalize the template, I gathered feedback from several stakeholders, including:

- product managers
- director of Product Management
- another tech writer
- tech support leads
- Client Success leads
- Sales Education lead

## Why It Matters

Calling details out separately–and in terms familiar to product managers–helped the PMs understand how to write more effective release notes. 

This collaboration also helped establish trust with PMs and various operations teams. This led to more consistent, detailed release notes, which led to increased views on release notes going forward.

## About This Sample

The sample below uses a modified version of the final internal release notes template. I also added a fictional release item based on a real release I documented, though many details have been changed for this sample.

The sample begins below the line.

---

## Bugfix: Corrected timestamps on Ignitions Report

- **Clients Affected**: All Maintenance Solutions clients
- **Problem Addressed**: A temporary service outage of a third-party processor caused incorrect timestamps to be applied to ignition changes recorded during the outage. This outage took place from 04:44 A.M. PDT to 05:09 A.M. PDT.
- **Solution Implemented**: The timestamps for affected ignition records were corrected by sourcing the timestamp from the associated device instead of from the processor. The Ignitions Report was also updated to use the same source.
- **Why It Matters to Clients**: Ignition has significant downstream impact, affecting employee drive time and vehicle usage metrics. The updated source provides a more accurate representation of the ignition change. This also prevents future processor outages from affecting ignition data.
- **Jira ID**: LLCJ-4321
- **Product Manager**: Dawn O. Era
