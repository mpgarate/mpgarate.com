---
layout: post
title:  "Building Team Trust with Code Reviews"
date:   2020-05-27
---

As developers, we can treat code review as an opportunity to build trust. There is something vulnerable about asking for feedback, and by responding with collaboration rather than confrontation, we build psychological safety. Imagine a world where you look forward to getting a review because the feedback makes the code better, shows respect for your work, and makes you glad you work with the people around you. We can choose to live in that world.

### Show gratitude

**Consider saying "thanks for putting this together!" or "thanks for reviewing this!"** The reviewer and author both went to work in good faith to make an improvement to the software. No matter what feedback we might have, we should show appreciation for the effort spent on it.

There is a [body of research](https://en.wikipedia.org/wiki/Gratitude#Empirical_findings) (outside my area of expertise) that links gratitude to happiness, stress reduction, relationship satisfaction, and personal growth. When we review a piece of code, in addition to showing gratitude, we can take a few seconds to **actually believe it**. Isn't it great that someone took the time to improve this software?

### Language matters

Text on code reviews lacks the expressiveness of other mediums that can help show good faith (i.e. smiling, voice tone, real time responsiveness). With this in mind, we can **over**compensate to make up for the limitations of text.

**Consider using "we" instead of "you"**. When one developer writes code and submits it to the team for review, they may be tempted to have a "me vs them" mentality: my code is ready and good, and they just need to give approval. A comment framed as "we" shows that the reviewer and author are aligned in an effort to improve the code and release it promptly. A comment framed as "you" can come across as combative and blameful, even though that is not the intent. The "we" mentality goes beyond language. Code changes are owned by the team as a whole, and except in an emergency, no one individual should release something without the support of teammates. Effective teams succeed and fail as a group.

**Consider saying "I think."** Using the phrase "I think" shows the reader that you acknowledge your own limitations and are open to hearing their input as well. Guides for academic writing and presentations suggest avoiding the phrase "I think" in order to sound more assertive. Code reviews, on the other hand, benefit from collaboration, where increased information flow from multiple sources leads to a better result. Underrepresented people in tech sometimes hear advice to sound more assertive at work, and this places responsibility in the wrong place. Strong communicators know how to listen well and identify good ideas from anyone on the team, regardless of background, seniority, or role.

### Review to release

**Consider saying "It's ok to address this comment in a later change."** Code authors and managers want code to ship ASAP. Time spent rewriting code after code review is time where the user benefit is not in production and where the author could be working on a new task. Code reviewers can support this interest by distinguishing between changes that should be addressed before or after release. For example, it might be a good idea to refactor a long function, but if that is the only thing blocking release, then the team could agree to release the user benefit, refactor, and release again. This also leads to smaller changesets, which allows for faster feedback cycles.

### Trivial changes

**Consider applying the trivial suggestions.** Choosing not to battle a nitpick can be a cheap way to build team ownership of a shared codebase. Reviewers should ideally keep comments about minor syntax changes to a minimum to prioritize discussion on impactful issues. If there is a pattern of too many nitpicks, that can be discussed in a team meeting. Still, nitpicks will inevitably come up, and while it can be tempting to push back against these, that also takes time away from bigger issues and releasing the user benefit. When implementing them is trivial and not harmful to the codebase, doing so tells your teammate that you value their input and increases their sense of ownership of the code. This helps people internalize the reality that once released, the code is owned by the team and no individual.
