# TPM Craft: Notes on Running Programs at Scale

Things I have learned running programs at enterprise scale - across security, infrastructure, and compliance - that are not in any certification curriculum. Not rules, more like working principles. Updated as I learn new things and unlearn old ones.

---

## On Starting Programs

**The charter conversation is the program.** Everything after the charter is execution. If the charter conversation is sloppy - vague objectives, undefined scope, missing owners, unresolved tradeoffs - execution will be sloppy. Spend the time.

**Name the out-of-scope items explicitly.** The things you decide not to do are as important as the things you decide to do. A charter without explicit out-of-scope items will absorb adjacent work until nobody can remember what the original objective was.

**The first question is not "how do we build this" - it is "why are we building this."** Teams that understand the business problem they are solving make better technical decisions than teams that are handed a spec. Make sure they know the why.

**If you cannot get executive sponsor sign-off, you do not have a program yet.** You have an idea. That is different. Do not start spending resources until someone with authority and accountability has said yes.

**Compliance reviews started late are problems you pay for twice.** First you pay to build the thing. Then you pay to rebuild the parts that do not meet the compliance requirement you discovered too late. Triage compliance at intake, every time.

---

## On Planning

**The plan is a hypothesis.** It reflects your best understanding of the work at the time you made it. As you learn more, update it. A plan that does not change is not being maintained, it is being protected.

**T-shirt sizing is lying with confidence.** Rough estimates are better than no estimates, but everyone in the room knows they are rough. The danger is when they get treated as commitments. Be explicit about what level of precision an estimate carries.

**Plan for the long tail.** In most programs, getting to 80% is easier than getting from 80% to 100%. In security programs especially - legacy systems, edge cases, teams that are perpetually too busy - the last 20% often takes as long as the first 80%. Budget for it.

**Dependencies are risks that have not activated yet.** Every external dependency is a potential blocker. Map them, own them, and review them regularly. The dependency that slips is almost never a surprise to the team on the other side - it is only a surprise to you because you stopped checking.

**Know the difference between a constraint and an assumption.** A constraint is fixed - a regulatory deadline, a budget ceiling, a contractual obligation. An assumption is something you are treating as true that might not be. Both need to be documented. Only one of them might be negotiable.

---

## On Execution

**The weekly sync is a forcing function, not a status meeting.** Its job is to surface blockers, make decisions, and create accountability. If it turns into a round-robin of status updates that everyone could have read in the RAID log, it is wasting everyone's time. Change the format.

**"Working on it" is not a status.** "Working on it, expected complete by [date], currently blocked by [specific thing] which [person] is resolving by [date]" is a status. Train the team to give you the second version.

**A risk without an owner is not being managed.** It is being acknowledged and ignored. Every item in the RAID log has a named owner, or it is not really in the RAID log.

**Escalate early or escalate late - those are your only choices.** Early escalation is a feature. Late escalation is a failure. When something is trending wrong, say so. Bring a recommendation, not just the problem.

**The 90% complete problem is real in security programs.** A remediation program that closes 90% of vulnerabilities still has open vulnerabilities. An encryption program that covers 90% of services still has unencrypted services. Name this explicitly and hold the standard. The long tail is where the real risk lives.

**Silence from a dependency owner is not a green status.** Follow up. If you have not heard back, that is the information. Something is either fine and they forgot to tell you, or it is not fine and they are hoping you will not notice. Either way, you need to know.

---

## On Stakeholders

**Understand what your stakeholders are accountable for.** An executive sponsor who is accountable for security posture needs different information than one who is accountable for engineering budget. Same program, different framing.

**Earn the right to be trusted with bad news.** Stakeholders who learn about problems from you first, with a plan already forming, will eventually start asking you things before they ask anyone else. Stakeholders who learn about problems from other sources will start asking you less.

**Not every stakeholder needs the same update.** The engineering team running the sprint needs tactical detail. The executive sponsor needs the outcome-level picture. Writing one update and sending it to everyone serves nobody well.

**The ask you do not make does not get answered.** If you need a decision, ask for it explicitly - name what you need, from whom, and by when. If you need an executive to clear a cross-organizational blocker, say so. Hinting is not stakeholder management.

**Stakeholders who feel informed stay in their lane.** Stakeholders who feel out of the loop start asking for access to the detailed tracking, sitting in on engineering syncs, and managing around the TPM. Keep them informed and they will trust you to run the program.

---

## On Teams

**Credibility with engineering teams is earned, not granted.** Show up prepared. Know what they are building. Do not waste their time. Follow through on what you say you will do. Surface their blockers faster than they expected. That is the whole playbook.

**The TPM's job is to make the team's job easier, not harder.** If the process you are running creates more overhead than it removes, fix the process. Structure serves delivery, not the other way around.

**When the team is stuck, help them get unstuck.** Not by solving the technical problem - that is not your job. By removing blockers, making decisions, getting the right people in a room, or escalating the thing that has been sitting unresolved for two weeks because nobody wanted to be the one to push it.

**Protect the team's time.** An engineer who spends three hours a week in status meetings that could have been a written update is an engineer spending three hours a week not building the thing. Respect that.

**Security engineers have no patience for theater.** They have seen too many programs that generate artifacts without reducing risk. Show them you understand the difference.

---

## On Reporting

**Bad news delivered early is a problem. Bad news delivered late is a crisis.** The gap is usually a week or two and a loss of options. Report honestly, always.

**Status colors mean something. Use them that way.** If everything is always green until it suddenly fails, the reporting is broken. Yellow exists for a reason - use it.

**The status report is not for you.** It is for the people who need to make decisions based on it. Write it for them.

**Numbers beat adjectives.** "Encryption coverage increased significantly" tells nobody anything actionable. "Encryption coverage increased from 67% to 78% this month, on track for 90% by end of quarter" is useful.

**Close the loop.** When a decision gets made, communicate it. When a risk gets resolved, note it. When a milestone lands, acknowledge it. Stakeholders who feel like things just happen to them without explanation will eventually stop trusting the reporting.

---

## On Finishing

**Define done before you start.** This seems obvious. It is frequently skipped. "Done" that is agreed on at the start is the objective. "Done" that is negotiated at the end is a compromise.

**The close-out report is not a formality.** It is the most useful thing you leave behind. Write it honestly - what the program achieved, what it did not, what the team learned, what the next program team should know. Someone will read it.

**Retrospectives generate insight when they generate honesty.** A retrospective where everyone says things went well is not a retrospective. Create enough psychological safety that people will say the thing they actually think. Then do something with it.

**Celebrate the work.** Programs are hard. People spent real effort on this. Acknowledge it before you move on to the next one.

---

*Working notes. Updated as the work teaches me new things.*
