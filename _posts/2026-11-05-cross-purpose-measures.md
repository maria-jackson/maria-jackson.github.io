---
layout: post
title: "“Don’t Measure It That Way!”: Why Reliability Measurements End Up at Cross-Purposes"
date: 2026-11-09 12:00:00 +0000
categories: essays
---
Reliability measurements are an area where I've seen a lot of disagreement. It can be about validity, acceptable levels of risk, where to invest effort, shaping a measurement to redirect who is accountable, or whether it's worth measuring at all. I want to focus on a specific issue.

You've probably heard some of these:

| What we hear | The pushback |
|---|---|
| "We're doing well, our SLOs aren't running out of budget." | "Don't turn SLOs into performance targets. It will ruin their usefulness." |
| "My MTTR keeps improving!" | "MTTR isn't statistically valid in your situation." |
| "We finished all our action items from that incident review." | "Action items measure whether you did something, not whether you improved the system!" |

I didn't have a vocabulary to describe what I was seeing when I was disagreeing with a trusted coworker about a measurement. This person was clearly thoughtful and we had different needs, but I couldn't quite verbalize what the disconnect was.

> **Many arguments about reliability measurements are arguments about measurement purpose. This can happen even if you align on overall purpose.**

## Eight Reasons to Measure

Robert Behn's paper [Why Measure Performance? Different Purposes Require Different Measures](https://doi.org/10.1111/1540-6210.00322) gave me that vocabulary. He lists eight purposes for measuring performance, and what a measurement needs for each. He was writing about government agencies, but the purposes translate well to reliability work. The table below is a simplified, adapted version of his argument, and it's worth reading the whole thing.

| Purpose and the question it answers | What the measure needs | Reliability example |
|---|---|---|
| **Evaluate:** What did our reliability work accomplish, compared to doing nothing? | What users experienced, weighed against what you invested, after accounting for things outside your control | No ideal example; see [Niall Murphy's list](https://non-functional.net/posts/2026-08-21-niall-s-naive-list-of-unsolved-problems-in-software-reliability/). |
| **Control:** Are people doing the reliability work they committed to? | Things people can directly do and be checked on | Action item completion |
| **Budget:** Where should we spend engineering time on reliability? | Outputs/inputs | Error budgets |
| **Motivate:** What will push the team to improve reliability? | Fast feedback against a near-term target | Reducing a team's pages |
| **Promote:** How do we show others our reliability work is paying off? | Simple numbers appreciated by the audience | MTTR on an all-hands slide |
| **Celebrate:** What reliability success is worth having a party for? | Milestones meaningful enough that people feel proud reaching them | No Sev 1 incidents this quarter |
| **Learn:** Why is our system working, or not? | Detailed data that shows surprises | Incident reviews |
| **Improve:** Did this change make the system better? | Evidence connecting what you changed to what happened | Chaos experiment |

## One Measure Can't Serve Every Purpose

We won't find a single metric that meets all these needs, or even one need perfectly.

Say we all agree to the same reliability project. The product owner needs to understand the *budget*, the lead engineer needs to know if it actually *improves* things, the VP needs to verify commitments (unflatteringly called *control*, sorry VPs!), and the whole team needs to be *motivated* to do a big lift over the course of months. No measurement can meet all those jobs.

## We Won't Always Interpret the Purpose the Same Way

Let's say we share that a team is declaring more incidents as a way to show that people are engaging in the incident process. But if other teams interpret "more incidents = more problems," they start declaring fewer incidents. We meant to *promote*, but it got interpreted as *evaluate*. Just having a measurement out there can change behavior in ways we don't expect.

The [McNamara fallacy](https://en.wikipedia.org/wiki/McNamara_fallacy), [Goodhart's law](https://en.wikipedia.org/wiki/Goodhart%27s_law), and [Campbell's law](https://en.wikipedia.org/wiki/Campbell%27s_law) are good warnings to keep in mind when designing measurements. But since not measuring has its own effects, we are still in the land of tradeoffs.

## Back to Those Arguments

**"Don't turn SLOs into performance targets."** SLOs make a poor *control* measure, because teams can't directly control them, and using them to *evaluate* takes a lot of adjustment. But error budgets are built to *budget*, and they can work well to *motivate*.

**"MTTR isn't statistically valid in your situation."** For *evaluating*, MTTR has [statistical limitations](https://resilienceinsoftware.org/news/1157532), and it only tells you what happened, not how you affected it. But because it has wide familiarity, it can work for *promoting*.

**"Action items measure whether you did something, not whether you improved the system!"** A well-formed action item list might lead to improvements, but the quality of the list is fairly independent of the completion rate. Still, completion is great for *control* and *motivating*.

In each case, both sides have a point. They're measuring for different reasons.

## So, there is no perfect measurement?

Right. These purposes pull against each other, but that doesn't make any of them bad.

If we understand what each person needs from a measurement, we can more often propose metrics that work for more people. We can better articulate our needs and tradeoffs. And we can design countermeasures for the ones we accept.

Thinking back to that disagreement with my coworker, I want to understand the other person's needs better. Next time, I'd ask:

- **"If this measurement worked perfectly, what would it get us?"**
- **"When we've used similar measurements in the past, what were the knock-on effects?"**

## Additional Reading

- Cedric Chin, [Goodhart's Law Isn't as Useful as You Might Think](https://commoncog.com/goodharts-law-not-useful/): how to design metrics that hold up when people are measured by them.
- John Cutler, [Mapping Beliefs (and Agreeing to Disagree)](https://cutlefish.substack.com/p/tbm-2453-mapping-beliefs-and-agreeing): deciding where alignment actually helps.
- Fred Hebert, [Plato's Dashboards](https://ferd.ca/plato-s-dashboards.html): evaluating proxy metrics and what they leave out.
- Douglas Hubbard, [How to Measure Anything: Finding the Value of Intangibles in Business](https://www.wiley.com/en-us/How+to+Measure+Anything%3A+Finding+the+Value+of+Intangibles+in+Business%2C+3rd+Edition-p-9781118539279): estimating whether a measurement is worth what it costs, given the decision it informs.
- Vanessa Huerta Granda, [Making Sense out of Incident Metrics](https://web.archive.org/web/20250319200029/https://www.learningfromincidents.io/posts/looking-beyond-the-metrics): using incident metrics to support change.
- Ron Kohavi, Diane Tang and Ya Xu, [Trustworthy Online Controlled Experiments](https://www.cambridge.org/core/books/trustworthy-online-controlled-experiments/D97B26382EB0EB2DC2019A7A7B518F59): widely considered the standard text on A/B testing in software. Reliability work has little similar tradition of experiment design, beyond chaos experiments and canary analysis.
