---
layout: post
title: "“Don’t Measure It That Way!”: Why Reliability Measurements End Up at Cross-Purposes"
date: 2026-11-05 12:00:00 +0000
categories: essays
---
In software, we have a lot of ways to measure our systems. Some are generally derided (counting lines of code), but others can be more contentious.

When we want to increase our reliability, we hear a lot of different ways to measure and then arguments against those measurements:

| What we hear | The pushback |
|---|---|
| "Our SLO hasn't run out of budget." | "Don't turn SLOs into performance targets. It will ruin their usefulness." |
| "My MTTR keeps improving!" | "MTTR isn't statistically valid in your situation." |
| "We finished all our action items from that incident review." | "Action items measure whether you did something, not whether you improved the system!" |

So, why are intelligent people at odds over how to measure reliability?

> **Many arguments about reliability measurements are really arguments about purpose.**

## Eight Reasons to Measure

In his paper [Why Measure Performance? Different Purposes Require Different Measures](https://doi.org/10.1111/1540-6210.00322), Robert Behn lists eight purposes for measuring performance, and what a measurement needs for each. He was writing about government agencies, but they translate well to reliability work. The table below is a very simplified and adapted version of his argument. I would highly recommend reading his paper first.

| Purpose and the question it answers | What the measure needs | Reliability example |
|---|---|---|
| **Evaluate:** What did our reliability work accomplish, compared to doing nothing? | What users experienced, weighed against what you invested, after accounting for things outside your control | SLO attainment, adjusted for team size, priorities and outages (often contentious) |
| **Control:** Are people doing the reliability work they committed to? | Things people can directly do and be checked on | Action item completion |
| **Budget:** Where should we spend engineering time on reliability? | Outputs/inputs | Error budgets |
| **Motivate:** What will push the team to improve reliability? | Frequent, visible signs of progress toward a goal the team owns | Reducing a team's pages |
| **Promote:** How do we show others our reliability work is paying off? | Clear numbers that connect with the audience | MTTR on a leadership slide |
| **Celebrate:** What reliability success is worth having a party for? | Milestones meaningful enough that people feel proud reaching them | No Sev 1 incidents this quarter |
| **Learn:** Why is our system working, or not? | Detailed data that shows surprises | Incident reviews |
| **Improve:** Did this change make the system better? | Evidence connecting what you changed to what happened | Chaos experiment |

> Adapted from Behn (2003), “Why Measure Performance?”

## Different Purposes Don't Line Up

Dr. Behn explains that no metric can answer all of these questions, and sometimes the purposes work against each other. We are unlikely to find a single metric that meets all these needs, or even one need perfectly. Using a measurement like "no Sev 1 incidents this quarter" to celebrate, for example, can work against declaring incidents and learning from reviews.

This doesn't mean that any of the purposes are inherently bad. They just can have consequences for other purposes.

## Back to Those Arguments

**"Don't turn SLOs into performance targets."** Error budgets are built to *budget*, and they can work reasonably well to *motivate*. But SLOs make a poor *control* measure, because teams can't directly control them. Using them to *evaluate* takes a lot of adjustment.

**"MTTR isn't statistically valid in your situation."** MTTR is great for *promoting*. But for *evaluating*, it has [real statistical problems](https://resilienceinsoftware.org/news/1157532), and it only tells you what happened, not how you affected it.

**"Action items measure whether you did something, not whether you improved the system!"** Action item completion is great for *control*, but it doesn't really speak to the other questions.

## Wow, That Seems Hard

Yeah, figuring out how to meet eight purposes at once in a complex system with a large number of stakeholders isn't realistic. We'll make tradeoffs, accept different risks and use proxy measurements that aren't ideal.

Purpose isn't the only thing we argue about, either. Sometimes the disagreement is really about validity, acceptable levels of risk, or shaping a measurement to redirect who is accountable. Purpose is just one of the easier ones to spot.

And frankly, sometimes it isn't worth even going through the process of making these measurements at all. (Hubbard's [How to Measure Anything](https://www.wiley.com/en-us/How+to+Measure+Anything%3A+Finding+the+Value+of+Intangibles+in+Business%2C+3rd+Edition-p-9781118539279) is good on deciding when it's worth it.)

Hopefully, this gives you a quick way to see why a metrics discussion is going sideways, and helps in your next goals meeting.

## Additional Reading

- Cedric Chin, [Goodhart's Law Isn't as Useful as You Might Think](https://commoncog.com/goodharts-law-not-useful/): how to design metrics that hold up when people are measured by them.
- John Cutler, [Mapping Beliefs (and Agreeing to Disagree)](https://cutlefish.substack.com/p/tbm-2453-mapping-beliefs-and-agreeing): deciding where alignment actually helps.
- Fred Hebert, [Plato's Dashboards](https://ferd.ca/plato-s-dashboards.html): evaluating proxy metrics and what they leave out.
- Douglas Hubbard, [How to Measure Anything: Finding the Value of Intangibles in Business](https://www.wiley.com/en-us/How+to+Measure+Anything%3A+Finding+the+Value+of+Intangibles+in+Business%2C+3rd+Edition-p-9781118539279): estimating whether a measurement is worth what it costs, given the decision it informs.
- Vanessa Huerta Granda, [Making Sense out of Incident Metrics](https://web.archive.org/web/20250319200029/https://www.learningfromincidents.io/posts/looking-beyond-the-metrics): using incident metrics to support change.
- Ron Kohavi, Diane Tang and Ya Xu, [Trustworthy Online Controlled Experiments](https://www.cambridge.org/core/books/trustworthy-online-controlled-experiments/D97B26382EB0EB2DC2019A7A7B518F59): widely considered the standard text on A/B testing in software. Reliability work has no similar tradition of experiment design, beyond chaos experiments and canary analysis.
