---
date: 2025-03-25T09:58:04-07:00
description: "Writing abounds at all levels of any organization. Often, it's created by non-writers who just happen to write at times. For these non-writers, here are my tips to help communicate more effectively."
# image: ""
lastmod: 2025-03-25
showTableOfContents: false
tags: ["collaboration","writing tips","lessons learned"]
title: "Writing Tips for Non-Writers"
type: "post"
draft: false
showTableOfContents: true
---

I have spent much of my technical writing career as a "team-of-one" writer. One lesson I've learned is that, even when I'm the only technical writer at a company, I'm not the only one making documentation. People all around the company are developing content to serve various needs. Consider the following examples.

- Product managers write Jira stories to communicate acceptance criteria to engineers.
- Engineers document their development decisions to promote consistency.
- Technical support leads write troubleshooting articles and scripts for specific scenarios.
- Account managers answer client questions via email.

Writing abounds at all levels of any organization. Sometimes, content is created by professional writers. But often, it's created by non-writers who need to write for their profession at times.

As a technical writer, one way to affect content strategy on a broad scale is to help non-writers improve their writing skills. For these non-writers, here are my writing tips to help you write more effectively.

## Write for Scanning

People like to say that no one reads but that's not strictly true. No one reads *thoroughly*, at least not initially. They scan. Their eyes skim text, looking for evidence of the information they desire. If they detect something, then they slow down and read a certain portion more thoroughly.

As a writer, one of your goals is to facilitate the visual scanning of text. You can accomplish this in many ways.

- **Sections and headings**: Break up content into logical sections with descriptive headings (the title also counts as a type of heading). Users typically look to headings first to guide their search for information. Craft accurate, concise headings to help users decide quickly if a section of the document is relevant to them. 
- **Lists and tables**: Use lists and tables frequently. Lists and tables are highly organized forms of information, making them easy to scan.
- **Graphics and screenshots**: Include graphics and screenshots that aid comprehension. Some examples include screenshots/mockups of software, line drawings of hardware, and workflow diagrams.
- **Table of contents**: For longer documents, a table of contents can give users an overview of the document and let them quickly jump to various sections.

### Example: Using Lists

As an example, consider the following excerpt from a posting for a technical writer position, describing desired knowledge and skills from applicants:

> **Knowledge and Skills**: Broad knowledge and understanding of computer hardware, applications, network, and operating systems. Knowledge and understanding of related Information Technology trends. Able to read; write legibly; speak in English with professional quality; use computer, printer, and software programs necessary to the position (e.g., Word, Excel, Outlook, PowerPoint). Strong knowledge of project management software such as MS Project, Access, and other project management tools for task tracking and team collaboration efforts. Able to relate and communicate positively, effectively, and professionally with others; work calmly and respond courteously when under pressure; lead, supervise, teach, and collaborate; accept direction. Ability to deal effectively with people and elicit support from other department areas, vendors, and customers. Excellent analytic, communication, and documentation skills. Able to organize technical work; demonstrate excellent planning, problem solving, analysis, documentation, presentation and organization skills; analyze and interpret data, processes and needs based on limited information; organize work and resources; define problems and solutions, prioritize work load; make recommendations; manage time effectively and plan and implement objectives effectively. Able to communicate effectively in English in person, in writing, and on the telephone; think critically; work independently; perform basic math and statistical functions; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay close attention to detail. Able to distinguish colors as necessary; hear sufficiently for general conversation in person and on the telephone, and identify and distinguish various sounds associated with the workplace; see adequately to read computer screens, and written documents necessary to the position.

This large block of text is hard to scan visually, except for its inline section heading. It would be much easier to scan if it were turned into a list.

> **Knowledge and Skills**
> - Broad knowledge and understanding of computer hardware, applications, network, and operating systems. Knowledge and understanding of related Information Technology trends.
> - Able to read; write legibly; speak in English with professional quality; use computer, printer, and software programs necessary to the position (e.g., Word, Excel, Outlook, PowerPoint).
> - Strong knowledge of project management software such as MS Project, Access, and other project management tools for task tracking and team collaboration efforts.
> - Able to relate and communicate positively, effectively, and professionally with others; work calmly and respond courteously when under pressure; lead, supervise, teach, and collaborate; accept direction.
> - Ability to deal effectively with people and elicit support from other department areas, vendors, and customers.
> - Excellent analytic, communication, and documentation skills.
> - Able to organize technical work; demonstrate excellent planning, problem solving, analysis, documentation, presentation and organization skills; analyze and interpret data, processes and needs based on limited information; organize work and resources; define problems and solutions, prioritize work load; make recommendations; manage time effectively and plan and implement objectives effectively.
> - Able to communicate effectively in English in person, in writing, and on the telephone; think critically; work independently; perform basic math and statistical functions; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay close attention to detail.
> - Able to distinguish colors as necessary; hear sufficiently for general conversation in person and on the telephone, and identify and distinguish various sounds associated with the workplace; see adequately to read computer screens, and written documents necessary to the position.

This list breaks up a single, large wall of text into several smaller, more digestible chunks. The bullets in the list above also provide visual anchors for each knowledge/skill requirement, letting readers jump between different requirements easily.

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

Both versions make sense. They both communicate the same information. Taken in full, both versions are functionally identical.

Now, imagine our reader is interrupted. Because of this, they're only able to catch the first 160 characters of the paragraph.

With the original paragraph, the reader catches this excerpt:

> The AM2 model of hazard identification is designed to reward reactive drivers. The model integrates audio alerts and incident logs into a cohesive system of esc...

With the edited paragraph, the reader catches this excerpt:

> With the AM2 model of hazard identification, audio alerts allow drivers to correct their own driving behavior; an incident log is only generated as the next lev...

The main difference between these excerpts is the mention of a reward for reactive drivers. Readers of the edited excerpt would miss this important detail completely. The original paragraph leads with this detail to give it the best chance of being seen.

## Remove Clutter

Knowing that readers can and will be interrupted, yet another way to facilitate scanning of text is to remove clutter. This is similar to the idea of clutter in UX design.

In UX, designers are often tasked with [reducing visual clutter from designs](https://www.lionandmason.com/ux-blog/reducing-cognitive-overload-declutter-your-design-for-better-ux/). Clutter distracts users, slowing them down from achieving their user goals.

Similarly, in writing, clutter includes details that distract readers from finding the desired information. This can include details that are unimportant or unrelated to the issue at hand. This can also include duplicate content.

As a writer, one of your goals is to minimize clutter. If we imagine our reader is interrupted again after only 160 characters, if those 160 characters contained any clutter, that reader has likely gained very little value, if any.

### Example: Removing Unnecessary Details

As an example, let's revisit the excerpt above from the job posting. Let's use the version wherein we've turned the paragraph into a bulleted list.

> **Knowledge and Skills**
> - Broad knowledge and understanding of computer hardware, applications, network, and operating systems. Knowledge and understanding of related Information Technology trends.
> - Able to read; write legibly; speak in English with professional quality; use computer, printer, and software programs necessary to the position (e.g., Word, Excel, Outlook, PowerPoint).
> - Strong knowledge of project management software such as MS Project, Access, and other project management tools for task tracking and team collaboration efforts.
> - Able to relate and communicate positively, effectively, and professionally with others; work calmly and respond courteously when under pressure; lead, supervise, teach, and collaborate; accept direction.
> - Ability to deal effectively with people and elicit support from other department areas, vendors, and customers.
> - Excellent analytic, communication, and documentation skills.
> - Able to organize technical work; demonstrate excellent planning, problem solving, analysis, documentation, presentation and organization skills; analyze and interpret data, processes and needs based on limited information; organize work and resources; define problems and solutions, prioritize work load; make recommendations; manage time effectively and plan and implement objectives effectively.
> - Able to communicate effectively in English in person, in writing, and on the telephone; think critically; work independently; perform basic math and statistical functions; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay close attention to detail.
> - Able to distinguish colors as necessary; hear sufficiently for general conversation in person and on the telephone, and identify and distinguish various sounds associated with the workplace; see adequately to read computer screens, and written documents necessary to the position.

Although this version is easier to scan than the original, it still contains a lot of information. At a glance, a few items stand out as potential clutter. Each item should be evaluated separately.

The most glaring example of clutter is the last item:

> - Able to distinguish colors as necessary; hear sufficiently for general conversation in person and on the telephone, and identify and distinguish various sounds associated with the workplace; see adequately to read computer screens, and written documents necessary to the position.

These are skills generally required of most jobs. These statements are so obvious, they do not need to be called out explicitly. This should be removed.

Similarly, the following two items contain many obvious statements. However, they cannot be removed completely because they also contain useful information.

> - Able to read; write legibly; speak in English with professional quality; use computer, printer, and software programs necessary to the position (e.g., Word, Excel, Outlook, PowerPoint).
> - Able to communicate effectively in English in person, in writing, and on the telephone; think critically; work independently; perform basic math and statistical functions; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay attention to detail.

Since the position in question is a technical writer role, we can deduce that communication is an important skill to highlight. However, many of the details here seem too obvious to call out because these are skills required of most jobs. This includes:

- the ability to read, write, and speak
- the language used (English)
- the ability to use a computer and printer
- the ability to "perform basic math and statistical functions"

If we remove these details, the two items can be shortened as follows:

> - Able to use software programs necessary to the position (e.g., Word, Excel, Outlook, PowerPoint).
> - Able to communicate effectively in person, in writing, and on the telephone; think critically; work independently; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay attention to detail.

After removing these more obvious details, we must remove duplicate content as some of the remaining skills overlap with each other.

One remaining skill overlaps with multiple other listed skills. This can be removed.

> - Excellent analytic, communication, and documentation skills.

In addition, these two items overlap regarding the ability to communicate effectively.

> - Able to relate and communicate positively, effectively, and professionally with others; work calmly and respond courteously when under pressure; lead, supervise, teach, and collaborate; accept direction.
> - Able to communicate effectively in person, in writing, and on the telephone; think critically; work independently; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay attention to detail.

These can be re-written as follows:

> - Able to relate and communicate positively, effectively, and professionally with others in person, in writing, and on the telephone; work calmly and respond courteously when under pressure; lead, supervise, teach, and collaborate; accept direction.
> - Able to think critically; work independently; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay attention to detail.

With the suggestions above, the excerpt is finalized as follows:

> **Knowledge and Skills**
> - Broad knowledge and understanding of computer hardware, applications, network, and operating systems. Knowledge and understanding of related Information Technology trends.
> - Able to use software programs necessary to the position (e.g., Word, Excel, Outlook, PowerPoint).
> - Strong knowledge of project management software such as MS Project, Access, and other project management tools for task tracking and team collaboration efforts.
> - Able to relate and communicate positively, effectively, and professionally with others in person, in writing, and on the telephone; work calmly and respond courteously when under pressure; lead, supervise, teach, and collaborate; accept direction.
> - Ability to deal effectively with people and elicit support from other department areas, vendors, and customers.
> - Able to organize technical work; demonstrate excellent planning, problem solving, analysis, documentation, presentation and organization skills; analyze and interpret data, processes and needs based on limited information; organize work and resources; define problems and solutions, prioritize work load; make recommendations; manage time effectively and plan and implement objectives effectively.
> - Able to think critically; work independently; manage multiple assignments; compose written material; work well under pressure; recall information with accuracy; pay attention to detail.