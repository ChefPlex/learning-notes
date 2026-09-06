# Lessons from Putting AI Into a Company

**What nobody tells you at the start.**

Companion piece: the [frameworks](https://github.com/ChefPlex/ai-automations/tree/main/frameworks)
in ai-automations - execution tiers, the activity mapping method, the multi-agent delivery
framework, and the tool decision matrix. **Those are the method. This is what running it teaches
you.**

These are patterns that generalize. The specifics of any one organization will not.

---

## 1. 🔑 It is already there, and the first job is finding out where

**The belief going in is that you're bringing AI into the company. You are not. It is already in
use, everywhere, in every fashion, and it got there without you.**

This single misreading invalidates most governance plans before they start, because a plan to
*introduce* something and a plan to *get control of something already running* are different
programs with different first steps.

### So the first job is discovery, not rollout

**You have to find out who is doing what, where.** And it's chaotic, because nobody coordinated it
and nobody was supposed to. People had work to do and reached for whatever helped.

Only after that can you ask the two real questions:

1. **Is what they're already doing what the business actually needs?** Sometimes yes. People
   closest to the work often found something good before anyone approved it.
2. **Or do they need pushing in a different direction?** Which is a redirection problem, not an
   adoption problem, and it's much harder - you're asking someone to give up something that's
   already working for them.

⚠️ **This is the same shape as the discovery problem in any large remediation program.** In
encryption modernization, the first finding is that nobody knows what is already encrypted. Here,
nobody knows what AI is already in use. **In both cases the instinct is to start fixing, and in
both cases the denominator is unknown and the fixing is premature.**

### The mechanism underneath it, and why it holds

> **People take the easiest path to get things done.**

That is not a compliance failure or a culture problem. It is how work gets done everywhere, by
everyone, permanently. **Any governance design that requires people to choose a harder path over an
easier one is a design that loses**, and it loses quietly, because nobody announces that they routed
around you.

### Therefore: make the sanctioned path the easy one

The design goal is that **the easiest path - or realistically, the second-easiest path that doesn't
get them in trouble - is the one that gets them across the finish line**, and keeps the work inside
a walled garden where governance is even possible.

Note what that formulation concedes, because the concession is what makes it work:

- **The sanctioned path may never be the single easiest option**, and pretending otherwise produces
  a policy nobody follows. Consumer tools with no controls will usually be more convenient than
  anything you can approve.
- **It has to be close enough that the risk tips the balance.** "Second easiest, and it doesn't get
  you in trouble" is an honest target and an achievable one.
- **You're competing on convenience, not on authority.** The moment the approved path costs
  materially more effort, usage migrates back out and your registry silently becomes fiction.

**A walled garden isn't a restriction, it's the precondition for governing anything at all.** You
can't review, inventory, or set a cadence over work you can't see. Everything in the framework
depends on the work happening somewhere you can observe it, and the only reliable way to achieve
that is to make the observable path the convenient one.

### 🔗 The same lesson turned up in a completely different program

This is the identical finding from large-scale encryption modernization, where the approach that
carried the program was the one that was **easier**, not the one that was most correct. The central
team built the path and the teams adopted it, because adopting something that already worked was
cheaper than solving it themselves.

**Two unrelated programs, same conclusion: you don't win adoption by mandating the right thing. You
win it by making the right thing the easy thing.** Mandates set direction. Convenience determines
what actually happens.

## 2. The map gets drawn by how people feel about it

**The classification questions in a framework are objective. The people answering them are not.**

You will be working with two populations at once, and they distort the map in opposite directions:

- **People who are afraid of it.** Afraid of the tool, of what it means for their work, of being the
  one who let something through. They will place activities higher up the human-only end than the
  work actually requires.
- **People who are going forward with it hard**, because they want to get ahead of it. They will
  push things toward autonomy faster than the blast radius justifies.

**Neither group is being unreasonable, and neither can be argued out of its position with a
framework.** The map you get back is a reading of your organization's relationship with the tool at
least as much as it is a reading of the work. **Expect that, and read the map accordingly** - a
function that classifies everything at tier 1 is telling you something about the people, not
necessarily about the activities.

### 🔑 The reframe that actually helps: none of this is as new as it feels

**A lot of what we now call AI tooling is the current step in a very long line of tools that have
been doing versions of this job for years.**

The example that lands, because everyone has lived it:

> **We used to go to Google to look something up. Now we use AI. But Google replaced going to the
> library.**

Each step felt like a rupture at the time and became ordinary. **Framing AI as the next tool in a
sequence, rather than as a categorically new thing, does more for adoption than any policy
document** - because it moves the question from "is this safe and am I allowed" to "is this better
than what I was doing," which is a question people already know how to answer.

⚠️ **This isn't a rhetorical trick and it shouldn't be used as one.** The comparison is honest:
each of those transitions genuinely changed what work looked like, genuinely displaced something,
and genuinely turned out fine for the people who learned the new tool. **Someone who is afraid is
not wrong that something is changing.** They're wrong that it's unprecedented.

### Make it easy to *try*, which is a different problem from making it easy to *use*

Lesson 1 is about the sanctioned path being convenient. This is narrower and it comes earlier:
**lower the stakes of the first attempt.**

People get locked up about how it will go. If trying the tool feels like a commitment, or like a
test they might fail publicly, or like a decision they will be held to, **they won't form a view
from experience - they will keep the one they arrived with.** And the one they arrived with is
either fear or hunger, neither of which is information.

**Cheap, low-stakes, reversible trials are the only thing that moves either group toward the
middle.** They're also, not coincidentally, how you find out where the tool is actually good, which
is the input the map needed in the first place.

## 3. 🔑 The real objection is headcount, and it is rational

**When people push back on the exercise itself, it's almost never about the tool. It is about what
the map will be used for.**

The fear has two faces, and the second one is the one that gets missed:

1. **Losing people they already have.** The obvious version.
2. **Being unable to hire people they don't have yet.** The subtler and more common one. A manager
   with a growing team, already being asked to take on more work, reads a map showing AI leverage in
   their function and sees the argument that will be used against their next headcount request.

**Both reduce to the same question, and it's a fair one:** *am I going to be asked to do more work
with fewer people, and then more work again with fewer still, while the expectation stays the same?*

### The quieter half of the objection is standing

Team size is not just capacity. It's trajectory, scope and standing - **what someone runs and where
they're going.** Asking a manager to document where their function could be more efficient is
asking them to write the case against their own growth, in public, with their name on it.

**Nobody is being obstructive when they hesitate at that.** They're reading the situation
correctly.

### Concede the rational part out loud

⚠️ **If efficiency findings have ever been used to justify cuts anywhere in the organization's
history, people have learned the correct lesson and they will apply it here.** You aren't arguing
against a superstition. You're arguing against evidence, and you should know which one you're
doing.

### The first case sets the precedent, whatever the policy says

The framework says the point is leverage rather than replacement - finding the work that was never
worth a person's attention so the person can do the work that's. **Saying that does not make anyone
believe it.**

**What settles it's what happens to the first team that reports a real efficiency gain.**

- If that team keeps its headcount and gets more interesting work, the message travels faster than
  any policy document, and honest reporting becomes safe.
- **If that team loses headcount, the program is finished** - not loudly, but permanently. Everyone
  else will quietly under-report their gains from then on, forever, and they will be right to.

🔗 **And note where that lands: a map built on under-reported gains is fiction.** Which is the same
failure as lesson 1's registry going stale when people route around a slow path. **Two different
self-protective behaviours, one identical outcome - the data you're governing from stops being
true.** Watch for both, because neither announces itself.

### The other objection is real too, and cheaper to fix

**"This will slow me down"** is not a proxy for anything. It is the honest cost of having to learn
something new, and it lands hardest on people who are already good at doing it the current way.

That one is answerable with time, decent onboarding, and the low-stakes trials from lesson 2.
**The headcount objection isn't answerable that way, and treating them as the same problem wastes
the answer on the easier half.**

## 4. 🔑 Show them it makes their life better. Do not mandate it.

**This is where most AI programs go in wrong, and you can see it everywhere.** The dominant pattern
is a mandate: adopt the tool, use the tool, keep using the tool, and usage gets measured.

**That is the opposite of what works.**

A mandate produces exactly one thing reliably: **usage metrics.** People will open the tool, do
something nominal, and go back to however they were working. You get a number that goes up and a
practice that doesn't change, and you've spent the goodwill you needed for the part that
mattered.

The alternative is slower at the start and it's the only thing that compounds: **let people warm up
to it, and show them how it makes their own work easier.**

### Why this is the answer to lesson 3, specifically

You cannot argue someone out of the headcount fear. **But someone whose own week got measurably
better stops relating to the tool as a threat to their job and starts relating to it as something
that helps them do it.** That shift isn't achievable by policy and it's not achievable by
reassurance. It is achievable by an afternoon where the thing actually helped.

**So the first uses you promote should be chosen for whether they make an individual's day better,
not for whether they make the organization's numbers better.** Those are different lists, and
starting with the second one is how you end up mandating.

### Two that reliably land

Both of these give time back immediately, to the person doing them, with no process change and
nothing at risk:

- **Voice to text dictation.** Removing the friction between having a thought and having it written
  down is a bigger unlock than it sounds, particularly for anyone who thinks faster than they type
  or who does their best thinking out loud. *(This document was produced that way.)*
- **Summarization into action items with named owners.** Turning a meeting, a long thread, or a
  rambling set of notes into a list of to-dos that each have somebody's name on them. **It
  accelerates work directly**, and it does the thing people find genuinely tedious rather than the
  thing they find satisfying.

Note what these two have in common, because it's the selection criterion:

- **The benefit is immediate and personal.** Not "this will improve our cycle time next quarter."
  This afternoon, for you.
- **Neither requires anyone to change how they work**, only to stop doing a chore by hand.
- **Neither touches judgment.** Nobody has to trust the tool with a decision to get value, which
  means the fearful population from lesson 2 can use them without conceding anything they're
  worried about conceding.

⚠️ **Resist the temptation to lead with the impressive use case.** The one that demonstrates the most
capability is rarely the one that converts a skeptic. **The chore nobody wanted to do converts
skeptics**, because it delivers on the actual promise - time back for the work that needed a person.

## 5. 🔑 The human review gate really does rot, and the cause is the ask rate

**This is observed, not predicted.** Automated code review is where it shows up most clearly: the
tool posts its findings, a human is meant to review them, and over time the review becomes a
formality. The output is mostly right, which is exactly the problem - **being mostly right is what
teaches a reviewer to stop reading.**

### The more honest example, because it is first-hand

The same thing happens in ordinary AI-assisted work. **Asked to confirm something often enough, you
start rubber-stamping**, and you know you're doing it while you do it. It is a bad habit and it
sets in fast.

**The cause isn't that the reviewer is lazy or careless.** It's the rate and the significance of
what is being put in front of them:

> **Ask often enough about things that are usually fine, and you get the boy who cried wolf.**

Attention is finite. A reviewer facing a stream of low-stakes confirmations will triage by
approving, because that's the rational response to a signal that's almost always green. **The
gate does not fail because someone stopped caring. It fails because it was designed in a way that
made caring impractical.**

### What this means for designing a tier-4 gate

**A gate's integrity is a function of how often it fires and how much each firing matters.** That
reframes what to measure:

- **Measure the ask rate, not only the approval rate.** A gate firing fifty times a day isn't a
  control regardless of what its approval percentage says.
- **Treat reviewer attention as the scarce resource it's**, and spend it deliberately. Every
  low-value confirmation you put in front of someone is drawn from the same budget as the one that
  actually needed a human.
- **Consolidate.** Many small confirmations are worse than one substantive decision, even when the
  total surface reviewed is identical.

### The pattern that works: decide once, then execute

The fix that made the difference in practice was to **restructure the interaction so that the human
answers one meaningful question, and the work then proceeds without further confirmation.**

Not fewer decisions - **fewer, larger, better decisions**, each one placed where judgment genuinely
changes the outcome, and everything downstream of it executed without stopping to ask again.

**This is the tier model applied to itself.** The confirmations being eliminated were never tier-4
judgment calls; they were tier-5 mechanical steps wearing a gate. Removing them does not weaken
oversight, **it concentrates it where it does something** - and it makes the remaining gate real
again, because a question that only arrives when it matters gets read.

⚠️ **The diagnostic, and it's uncomfortable: if the reviewer can predict their own answer before
reading the item, that gate is already gone.** It's worth asking people directly, because they will
usually tell you honestly, and the approval statistics will not.

### Calibrate the friction to the consequence, not uniformly

**The answer is not fewer guardrails. It is guardrails whose friction matches what they protect.**
Two properties decide the design, and they interact:

| | **Rarely fires** | **Fires constantly** |
|---|---|---|
| **Severe if wrong** | ✅ Keep hard friction. It survives *because* it is rare | 🔴 Redesign. This is the one that will rot, and it is the dangerous one |
| **Minor if wrong** | Fine either way | ⛔ Remove the gate entirely - this is mechanical work wearing a gate |

A working example of the top-left: **destructive commands.** Deleting things, removing infrastructure,
anything irreversible. **A hard stop there stays effective indefinitely, precisely because it almost
never fires** - so when it does, it gets read. The friction is the point and nobody has been trained
to click through it.

Compare that with a routine action gated on every single invocation. Same mechanism, opposite
outcome, and the difference is entirely the rate.

### 🔑 The failure to design against: a bypass that becomes routine

**The real danger is not the guardrail. It is the standard way around it.**

Most guardrails need an escape hatch, because sometimes the right answer genuinely is to proceed.
But **the moment the override is used routinely, the guardrail has become decoration** - a speed
bump with paperwork attached, which is worse than having no guardrail at all, because now there's
documentation suggesting a control exists.

What keeps an exception an exception:

- **It's explicitly named as an exception**, not absorbed as new normal practice
- **It's scoped narrowly** - this action, this time, not a pattern or a standing allowance
- **It expires**, so the next occurrence starts over rather than inheriting the last approval
- **It's logged**, and the log is read - a run of exceptions is the signal the gate is
  miscalibrated and should be redesigned rather than repeatedly waived

⚠️ **A logged exception is evidence the rule was followed carefully. A pattern of them is evidence
the rule has quietly stopped existing.** Those look identical one at a time, which is why the rate
has to be watched rather than each instance judged on its own.

### The honest open problem

**Working out which questions genuinely need a human, and asking only those, is unsolved.** It's
one of the real open challenges in applying AI to work: not whether to keep a human in the loop,
but **how to spend that human's attention on the decisions where it changes the outcome** rather
than spreading it thinly across everything the system happens to be uncertain about.

Nobody should claim to have solved this. **Getting it approximately right, and re-checking the
calibration when people start rubber-stamping, is currently the state of the art** - and noticing
the rubber-stamping at all puts you ahead of most implementations.

## 6. 🔑 The volume is the surprise, and most of it is invisible to the people doing it

**The single biggest surprise when you actually look is how many people are already using it.** Not
a few early adopters. Broadly, across functions, already part of how work gets done.

And the sharper half:

> **Even if people do not realize they are using AI, they are.**

It is embedded in tools they already had. Search, mail, documents, note-takers, meeting
transcription, support tooling. Nobody made a decision to adopt it and nobody would list it if
asked.

### Which breaks the obvious discovery method

⚠️ **Don't run discovery by asking people whether they use AI.** The answers will be sincere and
badly wrong in both directions - people who use it constantly through embedded features will say no,
and the question itself sounds like an audit, which suppresses the rest.

**Ask what tools they use and what they use them for.** Work out the AI exposure yourself. It is the
same discipline as any inventory: **the population is defined by what is actually running, not by
what people report running.**

### The real risk is data leaving without anyone deciding it should

This is the part that has been pointed out many times and is still the live exposure. **Someone with
a personal account or a free tier pastes something into a general-purpose assistant to get help with
their work.** Reasonably. Helpfully. Trying to do their job well.

**What has just happened is that company data left the company**, into a service with no agreement
covering it, no retention control, no audit trail, and no way to get it back. There is no malice
anywhere in that sequence, which is exactly why policy alone doesn't stop it.

### The fix is to buy the accounts, even if you would rather not

**Give people paid accounts. Enterprise accounts. Even when you do not particularly want to spend
the money.**

The reframe that makes this an easy decision once you see it:

> **The license is a data-loss control, not an enablement budget.**

Justify it by what it prevents rather than by what it enables, and the business case stops being
about productivity gains that are hard to measure and starts being about a leak you can describe
concretely. Paid and enterprise tiers are where the agreements, the retention settings, the
administrative visibility and the audit trail live. **The free tier is the same product with none of
the controls**, which is why "we haven't approved AI yet" isn't a safe position. It is an unmanaged
one.

🔗 **And notice that this is lesson 1, arriving from the finance side.** Making the sanctioned path
the easy path and buying people proper accounts are **the same action**. The control and the
convenience aren't in tension here, they're purchased together - which is unusual enough in
security work to be worth saying out loud.

## 7. 🔑 Provenance is the old problem, and library science already solved it once

**When the web took off, nobody knew how to judge a page.** Anything could look authoritative. The
discipline that supplied the answer wasn't computer science, it was **library science** - the
existing practice of asking, of any document: **who wrote this, who published it, who paid for it,
and when.**

Applied to a web page, that gave you the thing that actually mattered: **a route back to whoever was
responsible**, so that if something was wrong you knew whose door to knock on.

**The same question is now the AI question**, and it applies to any tool that creates or publishes
anything:

> **Where did this come from, and what is its provenance?**

### Why this is the operational concern and not the philosophical one

It is tempting to file provenance under ethics or compliance. **It is neither. It is
maintainability.**

- **You can't correct what you can't trace.** A document, a decision, or a body of code with no
  provenance isn't merely unattributed - it's unfixable, because nobody knows who understood it.
- **You can't review what you can't attribute.** The distinction between fully generated, partly
  generated, and generated-then-reviewed only exists if somebody recorded which one happened.
- **You can't improve a process you can't reconstruct.** This is why the delivery framework keeps
  thread, cost and decision logs and voids artifacts rather than deleting them: **a superseded
  version usually explains why the current one looks the way it does.**

### It also explains why every governance standard converges on the same thing

Look across the AI management standards, the risk frameworks and the regulation and the common
thread is not any particular control. **It is a named accountable person and a traceable record.**
The EU AI Act's transparency carve-out turns on *a natural or legal person holding editorial
responsibility.* The management standards ask who owns the system. Every one of them is asking the
library-science question in its own vocabulary.

**Which means the practical work is the same regardless of which regime you land under**, and you
can do it before you know: **record what produced a thing, who reviewed it, and who is answerable
for it.** That's cheap while the work is happening and close to impossible to reconstruct
afterwards.

⚠️ **The failure is silent and it compounds.** Nobody notices missing provenance until the day
something is wrong and there's no route back - by which point the person who knew has moved on and
the record was never kept. **Provenance is not documentation overhead. It is the thing that keeps
the work correctable.**

---

## The short version

If you are handed this tomorrow:

1. **Assume it's already in use**, including by people who would say it's not, and start with
   discovery rather than rollout
2. **Ask what tools people use, not whether they use AI** - the direct question under-reports by
   design
3. **Buy the paid accounts**, and justify them as a data-loss control rather than a productivity bet
4. **Make the sanctioned path the easiest one available**, or accept that you're governing a
   fiction
5. **Expect fear and hunger in the same room**, and read a lopsided map as information about people
   rather than about the work
6. **Treat the headcount objection as rational**, because it usually is, and understand that the
   first team to report a real gain decides whether anyone else reports honestly
7. **Lead with the boring chore**, not the impressive demo - dictation and turning notes into owned
   action items convert skeptics
8. **Watch your own gates for rubber-stamping**, calibrate friction to consequence, and consolidate
   many small confirmations into one decision that actually gets read
9. **Record provenance while the work is happening** - what produced it, who reviewed it, who is
   answerable - because it's cheap now and unreconstructable later, and it's what keeps the work
   correctable rather than merely attributed
