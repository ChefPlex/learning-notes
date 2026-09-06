# Lessons from Leading Large-Scale Encryption Programs

**What nobody tells you at the start.**

Companion piece: [Encryption Program Playbook](https://github.com/ChefPlex/security-program-playbooks/blob/main/encryption-program-playbook.md)
in security-program-playbooks. **That is how to run one. This is what running one teaches you.**

Notes from running encryption modernization at scale: coverage from roughly 10 percent to 80 percent
plus, across 300+ distributed services, 100+ engineering teams and 10+ cloud environments, plus a TLS
upgrade program that ran twice and key lifecycle work on hardware security modules.

These are the patterns that generalize. The specifics of any one estate will not.

---

## 1. Get out in front of it, and spend the time on analysis

**There are a million moving parts and you'll never have enough time.** That's the permanent
condition of this work, not a symptom of a badly run program.

Which is exactly why the analysis phase is the one to protect. **Give yourself as much time for it
as you can get**, because every hour you don't spend understanding the estate up front is bought
back later at a much worse exchange rate, usually in the middle of execution when you've already
committed to a date.

The pressure runs the other way. Analysis looks like nothing is happening. Remediating the twenty
services you already know about looks like progress. **It is not progress if the denominator is
still moving.**

## 2. Build the program assuming you will be blocked, because you will be

**Small things come up constantly and continuously throughout the program.** Not once, not in a
bad quarter. Throughout.

The pattern that repeats: you hit something that can't be done the way the plan says, and **you go
back to the architects and back to the engineering teams and work out a different solution.** That
loop is not an exception path. It's a normal, recurring part of the work, and it needs to be in
the schedule and in the operating rhythm from day one.

**A long-term plan that has no allowance for re-solving problems is a plan that will be wrong by
month two** and will then spend the rest of the program being defended instead of used.

## 3. Executive visibility is a lever, so pull it deliberately

**The more you can give executives a genuine bird's-eye view of what is happening, the better the
program runs.** Not because they need reassurance, but because visibility lets them do two things
you cannot do yourself:

- **Celebrate progress**, which is worth more than it sounds when a hundred teams are doing work
  that's not on their roadmap and nobody outside the program can see it
- **Move blockers**, which is frequently the only path when the obstacle is another organization's
  priorities

⚠️ **A status report that only says how far along you're wastes the lever.** The value of executive
attention is that it can be pointed at something. Show them what is stuck and who could unstick it.

## 4. Automate the measurement, and it changes what you can promise

**Once you know how many nodes you're working with, write the script that goes out and counts how
many still need to be done.**

This sounds mundane and it's one of the highest-return things in the whole program:

- **It replaces self-reported status with observed state.** A hundred teams reporting their own
  progress produces a number that is wrong in a consistent direction.
- **It makes the number cheap to refresh.** Manual status collection is expensive enough that it
  happens monthly. An automated count can happen continuously, which means you find out about a
  regression in days rather than at the next reporting cycle.
- **It's what makes the dashboard honest.** Dashboards built on self-reporting are a rendering of
  what people believe. Dashboards built on a script are a rendering of what is true.

**This type of dashboard and this type of reporting was the single biggest reporting improvement in
the program.**

## 5. 🔑 Priority is displacement, and it does not propagate on its own

**This is the lesson with the most teeth, and it's the one most likely to sink a program that's
otherwise well run.**

Every team already has priorities. They were set during planning, they are committed, and people
are measured on them. **Your program almost certainly arrives in the middle of the year, after all
of that has been decided.**

So the request isn't "please add this." The request is: **something that's already a priority has
to move so that yours can go in.** Naming that honestly is the only way the conversation goes
anywhere, and it has to happen in two places:

**Upward, through the executives.** They're the only people who can authorize the displacement.
This isn't a status conversation, it's a trade, and you've to be able to say what specifically
gets deprioritized.

**Then downward, all the way to every engineering team.** And this is the part people skip:

> **Priority granted at the top does not arrive at the bottom by itself.**

You have to walk it down the chain and hand-hold it into each team's actual plan. **Otherwise it
gets dropped along the way** and the engineering teams simply don't have it as a priority, whatever
was agreed three levels above them. Nobody is being obstructive. The decision just never reached
them in a form that changed what they work on Monday.

⚠️ **The failure mode is invisible and it's slow.** You have executive agreement, you've a
committed date, and nothing is moving, because the priority exists in a leadership deck and not in
any team's sprint. By the time that shows up in the numbers you've lost a quarter.

## 6. 🔑 What we were wrong about: we thought we could do it without the workaround

**The belief going in was that everything could be encrypted directly. No sidecar, no third-party
solutions engineered around the problem, just the work done properly on each service.**

That turned out not to be the case.

Many of the paths that looked viable during up-front analysis were **simply not tenable** once we
were into them. The correction was to go back, look again, and find an approach that would actually
get across the finish line - which is where the sidecar came from.

Three things worth taking from this:

- **The sidecar was not the plan. It was the correction.** The approach that ended up carrying a
  large share of the program was the one adopted after the original approach failed. If you are
  reading a clean architecture diagram of a finished program, you're looking at the second answer.
- **Analysis is necessary and it's not sufficient.** Lesson 1 says protect the analysis time, and
  that still holds. But some paths only reveal themselves as impossible when you try them.
  **Up-front analysis reduces the number of wrong turns. It does not eliminate them**, and a program
  planned as though it will is a program with no room to correct.
- **"Do it properly on every service" is a purity argument, and purity loses to finished.** The
  workaround that gets 300 services encrypted beats the correct approach that gets 40 done and
  stalls. Recognizing that early is worth a quarter.

⚠️ **The tell that you're in this situation: the plan is fine and the progress isn't.** When
several independent teams all fail to complete the same kind of work, the problem is usually the
approach rather than the teams, and the right response is to go back to the architects rather than
to push harder.

## 7. How these programs actually end, and why that is fine

**It ends at diminishing returns, not at a wall.**

The program ran to roughly 80 percent, which got almost everything done. What was left was a
handful of legacy services with no realistic path, and those were **deliberately scoped out.** Then
the program manager came off, because most of the work was done and what remained was a slow dribble
over the following six months that did not need dedicated reporting. Periodic check-ins, occasional
help with an item, and those items were genuinely past the end of the program.

**This isn't specific to encryption.** Large programs reach 80 or 90 percent and the final 10
percent frequently never gets done as originally scoped. The mature response is to look at the
residual again and ask whether it still belongs in scope. Often it does not. **You reduce the scope,
and against the revised scope you've delivered 90, 95, or 99 percent** - and it meets the bar for
what actually needed to happen.

Two things make this legitimate rather than a dodge:

- **The scope reduction is explicit.** Made in the open, recorded, agreed by whoever set the
  original target. A quiet redefinition of success is a different thing entirely and everyone can
  tell the difference.
- **The program ends when it no longer needs coordinating.** The signal is organizational, not
  numerical. **Keeping a program manager on a tail that doesn't require one is its own failure**,
  and reading that moment honestly - rather than defending the role - is part of doing the job well.

⚠️ **Plan for this ending from the beginning.** A program that has only defined success as 100
percent has no language for the moment it should stop, and will either grind for quarters against
work that doesn't justify it, or end in something that feels like failure despite having delivered
almost everything that mattered.

---

## The short version

If you are handed one of these tomorrow:

1. **Buy analysis time** and spend it on the denominator, not on the services you already know about
2. **Find the owners early** - that's the schedule, not the service count
3. **Expect the work to concentrate** on whoever absorbs the ownerless services, and negotiate
   relief for them specifically
4. **Get the priority displaced formally, then walk it down** to every team yourself
5. **Automate the count** so status is observed rather than reported
6. **Assume your first approach is partly wrong**, and leave room to go back to the architects
7. **Celebrate the teams publicly** - it's the only renewable currency you've
8. **Decide in advance what "done enough" means**, so you can end it honestly at diminishing returns
