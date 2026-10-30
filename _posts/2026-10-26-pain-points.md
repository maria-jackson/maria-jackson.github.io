---
layout: post
title: "Figuring Out What Your Platform Team Should Fix Next"
date: 2026-10-26 12:00:00 +0000
categories: essays
---
Recently, in [Rands Leadership Slack](https://randsinrepose.com/welcome-to-rands-leadership-slack/), someone (who approved my sharing) asked a great question:
 
> Hi, Starting a new gig soon in Platform Engineering / DevEx!
>
> What ideas/tools/practices do y'all recommend for end-user observability? I haven't started yet, but besides surveying + just talking to people, what are the best ways of learning about your engineers' biggest pain points, most FAQ, etc?
 
For 7 years, I've worked in some kind of platform engineering role, and before that I worked on platform teams for plant scientists. There are often a lot of things that you can fix, but prioritizing them can be difficult.
 
To start building intuition from data, look at GitHub and your CI/CD platform. They have information about build times, flaky tests, and PR wait times. Your team might have additional telemetry like SLOs or real user monitoring (RUM) for your internal tools. Additionally, you can easily scan (or generate a summary of) the last 2 months of your support Slack channels or tickets to get an overall understanding of what is most frequent. The most interesting part is often how much of your overall support work isn't repeated. And always, just sitting back and watching a user or teammate walk through the process will reveal their actual workflow.
 
Now, the above take no training, no reading, and no explanation for your teammates, and just doing them will give you some intuition about how you are serving your users. As [Thoughtworks](https://www.thoughtworks.com/radar/techniques/platform-engineering-product-teams) and [DORA](https://dora.dev/report/2024) both recommend treating your platform as a product, more advanced tools for understanding your internal users may be the right next step. They require a little more initial investment, but they've paid off for me.
 
**For surveys**, I've run several DevEx surveys and analyzed the results. DORA's [Choosing measurement frameworks to fit your organizational goals](https://dora.dev/insights/measurement-frameworks/) gave me the understanding that these surveys actually serve several purposes. Additionally, if you have a specific area that you realize needs work, DORA's [Capabilities: Catalog](https://dora.dev/capabilities/) often has additional questions from over the years.
 
**For interviewing**, while I've done a week-long UAT interview camp, the book [Just Enough Research](https://www.mulebooks.com/just-enough-research) is a short, practical guide to doing it well. The questions let the interviewee answer you in ways that you haven't preconceived. I've done it repeatedly with engineers and internal business users and been surprised by the answers.
 
Additionally, people tend to really enjoy the process of being asked about their work. I've been on teams where there were conflicts over priorities, and just having engineers sit in on a few interviews immediately got us aligned. I've even used it to help my late mother with her cancer journey and learned new things about her.
 
**When some teams have succeeded and others are struggling**, and you want to centralize, I have used [Positive Deviance](https://en.wikipedia.org/wiki/Positive_deviance) or "Bright Spot Analysis" from [Switch](https://heathbrothers.com/books/switch/). It looks at what's different about the success cases and whether you can recreate those conditions elsewhere. This is especially useful when you need to figure out whether something is possible with your current leverage. I've used this to deprioritize work when I realized that the successful teams had members with years of experience in the space and we didn't have that in other areas. Peter Seibel's [Let a thousand flowers bloom. Then rip 999 of them out by the roots](https://gigamonkeys.com/flowers/) helps walk through when it is worth it to centralize those practices.
 
**For improving mostly linear processes**, [Value Stream Mapping](https://dora.dev/guides/value-stream-management/) (or any kind of Business Mapping) has helped me both understand a process and get buy-in for changing it.
 
I once came into a team that had been debating how to improve their process for years. There were lots of ideas and several attempts to improve it, but there was still a ton of rework and general slowness. I threw together a value stream map in half an hour, and I remember a teammate saying out loud, "Oh, so that's how it works." It became absolutely obvious what needed to change and what it was costing us. Everyone already knew how to fix it. What we actually needed was alignment. Once we were aligned, we fixed it in a day.
 
**For understanding unintended consequences**, Causal Loop Diagrams have helped me think through interventions before I make them. I've repeatedly looked at the diagram and realized that I was trying to change the system in the wrong place. I needed to make the change (sometimes a much smaller one) somewhere else, or I'd just be fighting gravity. If you've never seen those, [LOOPY: a tool for thinking in systems](https://ncase.me/loopy/) is an interactive tool that explains it far better than I can. For applying them to IT specifically, check out [Signals & Levers](https://itrevolution.com/product/signals-and-levers/). For a free starting point, Donella Meadows' essay [Leverage Points](https://donellameadows.org/archives/leverage-points-places-to-intervene-in-a-system/) ranks the types of leverage you can have in a system.
 
**When I've needed to define what my platform team does** for users and leaders, I've found [Team Topologies](https://teamtopologies.com/)' language around platform teams and the Thinnest Viable Platform resonates. Leaders and teammates have consistently understood when I've explained things using their diagrams. Their [Team API](https://github.com/TeamTopologies/Team-API-template) walkthrough helped me work with a sister team to reduce our dependencies on each other.
 
**And when you can't figure out what to do next**, Hazel Weakly's [So You Want To Hire For Developer Tooling](https://hazelweakly.me/blog/so-you-want-to-hire-for-developer-tooling/) has a section on ideas that likely have high ROI. Personally, I love working on onboarding because the payoff is so clear. (But it might not [always be rewarded](https://www.noidea.dog/glue).)
 
## If I were in their shoes
 
If I were starting a new position in this area, here's what I'd do:
 
1. Read and do the steps in [The First 90 Days](https://store.hbr.org/product/the-first-90-days-updated-and-expanded-proven-strategies-for-getting-up-to-speed-faster-and-smarter/11323?srsltid=AYCX9vIrx_NkobhZ6FX2pn-4Y3kyfy4bvZGU09bPfNWu10DKbcyGUz4f). It's general business advice and more targeted for business leaders, but it will give you a solid plan for your first few months. If you want to invest in better questions for your one-on-ones in those days, read [Just Enough Research](https://www.mulebooks.com/just-enough-research).
2. When you feel like you want to invest more, try [Value Stream Mapping](https://dora.dev/guides/value-stream-management/) your own CI/CD pipeline. Just dogfooding a single one of these techniques helps you get a handle on applying new frameworks.
3. Keep an eye open for when one of these tools might help with the specific issue you're having.

We can always find more things to fix, but having a clearer picture of your system can help you and your team align on priorities.
 
