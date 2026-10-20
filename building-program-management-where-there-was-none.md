# Building Program Management Where There Was None

**Notes from setting it up inside a cryptography group at a large SaaS company.**

Companion piece: [Rescuing Work That Is Off Track](https://github.com/ChefPlex/tpm-templates/blob/main/rescuing-work-that-is-off-track.md)
in tpm-templates. That one is the method step by step. This one is about the order I put the pieces in.

---

## The wrong picture

When people hear that a group had no program management, they picture something missing on paper: no charter, no plan, no status report. So the instinct is to bring the paper. Write the charter, stand up the weekly status, build the dashboard.

The group I joined had most of what you would see from the outside. It had a backlog, a work tracker and engineers who were working hard. What it did not have was any agreed answer to the question of how much work it could actually finish. Every request that came in was a promise nobody had sized, and the backlog was about two years deep.

The teams that depended on it were unhappy, and they had reason to be. Things they had asked for kept not arriving, and nobody could tell them when they would.

It was also a standing team with a continuous stream of requests, which is different from running a program. Nobody hands you a charter for a team, so you attach yourself to it and work out what is broken.

## What the PMI plan taught me about where to start

A couple of years before this, in early 2016, I laid out the PMI (Project Management Institute) process groups as a Microsoft Project schedule. Every process was a task under its process group (initiation, planning, execution, monitoring and controlling, closing), and through the front of the plan each one was linked to the processes it feeds.

Doing that changes how you read the framework. On paper the PMI processes look like a long checklist of things a competent program manager does. Laid out as a schedule they are a dependency chain. The output of one process is the input to the next. You cannot develop a schedule until you have estimated the work, you cannot estimate the work until you have collected requirements, and the requirements wait on knowing who your stakeholders are. Control comes after all of it, because there is nothing to control until a baseline exists.

That told me where to start in a group with no program management, which is at the front of the chain. The parts that look like program management from the outside, the status report and the dashboard, sit near the end. If you put them in first you are reporting on a plan that was never estimated.

So the order I put things in followed the chain, roughly:

| Order | What I put in |
|:---|:---|
| 1 | Separate first meetings with the engineers, their management, and the teams that needed work from them (PMI: Identify Stakeholders) |
| 2 | The same questions to everyone: what are you doing, what are you asking for, what do you expect, what frustrates you (PMI: Collect Requirements) |
| 3 | Level-of-effort estimation, built from work the team had already finished (PMI: Estimate Activity Durations) |
| 4 | A per-person cap on what the team would commit to each sprint, which is where expectations get set (PMI: Develop Schedule) |
| 5 | A rule for emergency work: when something urgent is pushed in, the requester helps pick what gets pushed out (PMI: Perform Integrated Change Control) |
| 6 | A dashboard showing what had been done and how fast, then the same view going forward (PMI: Manage Communications) |

Large parts of the PMI list had nothing to attach to. A team that never ends has no closing phase, for one. I don't think that's a flaw in the framework. It was written for projects, and the job here was to pick the part of it that a standing team could actually use.

## Why estimation came before everything else

In those first meetings I was collecting three versions of the job from each person. What they thought they were trying to do, what they were actually doing, and what they thought they were supposed to be doing. Lined up across everyone, the gaps between those three told me where it was breaking. Most of the gaps came back to the same thing. The people asking for work expected far more than the team could produce, and nobody had a number to show them otherwise.

Nobody had done any real sizing. So I went back through the work the team had already completed and sized it, using small, medium and large on a 5, 8 and 13 point scale. I started by calling everything a medium, because it was the simplest way to get a baseline, and adjusted from there. That gave a realistic number for what one person could finish in a sprint.

The number mattered because of what people do without one. A stakeholder asks for everything, because asking costs nothing, and the team lead says yes, because saying no to a senior requester is expensive and the missed date is a problem for later. Then it is one opinion against another and the louder person wins. If you can show what the team actually finished, that is hard for people to refute, and once they see it they tend to line up behind it.

It is the same reason a good kitchen quotes a time on a large party before it fires the order. The cooks aren't any slower for saying it, and the table is a lot happier waiting forty minutes it was told about than twenty it wasn't.

## Setting the expectation

With a capacity number in hand I walked the backlog with each of the teams asking for work. Most of it did not need doing now. What was the most important work, and was each item large, medium or small?

The commitment that came out of it was two large, two medium and two small items per person per sprint. The smalls and mediums fill in around the larges, so there is always something to pick up while a large is waiting on a review or another team. It was a ceiling on what we would promise. If someone finished early they pulled more in, and that extra work landed on a stakeholder who was already getting what they had been told to expect.

My side of the bargain was blockers. If anyone was stuck for more than a day, it came to me and I cleared it.

## What it cost

This made people very unhappy up front. The teams depending on us were being told they would get less than they had asked for, and the resistance came from both directions. Leadership had to accept the smaller number, and the engineers had to accept working to a cap at all.

After a few sprints of the work actually landing when we said it would, the people asking for it started to believe the next date too. By about ninety days things had settled. Within six months the group was delivering on time, and the teams that had complained about it were praising it instead.

The team's throughput went up over the same period. I read that as morale more than method. They had been in a bad place for a long time and had never seen anything come back as positive feedback. So I made a point of giving it, to the team and to their managers and their managers' managers, so that everyone could see what was getting done.

## Where this stops

I can't separate how much of the improvement came from the estimation and how much came from a team finally hearing that its work was landing. I suspect the two fed each other, but that is a guess.

The sizing was crude, too. Starting everything at medium gets you a baseline, and it took several sprints before the estimates were worth much. I am also not sure now whether I sized the last year of completed work or the last two, so call it at least a year.

And this was a standing team doing a steady stream of similar work with the same people. For a one-off program with new people, new technology and a hard date, I would expect to need a good deal more of the PMI chain than I used here, though I would still start at the front of it and build the reporting last.

---

*Working notes. Updated as the work teaches me new things.*

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](LICENSE).*
