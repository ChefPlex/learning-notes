# Introducing PM Concepts to Career Changers

A teaching guide for explaining project management to people who have never worked in a formal PM environment.

Developed from teaching ProSkills and Project Prep at Year Up (2015-2016), a workforce development program that places young adults without four-year degrees into tech internships at companies like Salesforce and VMware. The students were smart, motivated, and had zero tolerance for corporate abstraction. That wasn't a problem - it was a constraint that made the teaching better.

This guide is for anyone trying to explain PM to an audience that doesn't yet have the vocabulary: bootcamp graduates, career switchers, people coming from trades, food service, retail, the military, or any context where "deliverable" isn't a word anyone uses without apologizing for it first.

---

## The Core Problem with How PM Is Usually Taught

Most PM instruction starts with frameworks. PMBOK, Agile, Waterfall, Scrum. Vocabulary before meaning. The student learns to define "scope" before they understand why scope matters. They can recite the triple constraints before they have ever felt the pain of a project that had none of them defined.

This is backwards. And for a career changer - someone who is already being asked to learn a new industry, a new culture, a new set of unwritten rules, and a new vocabulary all at once - it creates a confidence problem that has nothing to do with ability.

The fix is simple: start with the experience, not the vocabulary. Give people the feeling of a concept before you give them its name. Let them discover the insight themselves, then hand them the word for what they just figured out.

That is what these notes are about.

---

## Know Your Room

Year Up students ranged from 18 to 24. Most had some work experience - restaurants, retail, customer service, community organizing. Some had military backgrounds. A few had taken community college classes. Almost none had worked in an office environment, and several had never sat through a professional presentation before this program.

What they shared: they were not beginners at life. They had managed things - households, younger siblings, jobs with real stakes. They understood responsibility, accountability, and what happens when someone doesn't show up. They just had not seen those concepts translated into corporate PM language.

Your career changers may be different in age and background, but that underlying pattern is likely the same. Treat them as experienced humans who are new to this particular vocabulary, not as blank slates. The fastest way to lose a room is to explain something they already know using words they don't recognize yet, and then look surprised when they aren't following.

Before you start: ask what they do, what they want to do, and what they think is blocking them. Those three questions tell you everything you need to know about how to pitch the material.

---

## What Actually Lands in the Room

These are the frames and analogies that worked. Not because they're clever - because they connect PM concepts to things people have already done.

### Thanksgiving Dinner

The single most effective teaching tool. Works for every audience, every time. Use it first, use it fully, build everything else on top of it.

Thanksgiving dinner is a project. It has a scope (how many people, what dishes, formal or casual), a plan (the menu, the shopping list, who is bringing what), a timeline with a genuine critical path (you can't make gravy until the turkey is done - that's a dependency, and it determines your finish time), risks (the Paleo cousin, the undercooked bird, the person who says they're bringing a dish and then doesn't), stakeholders with competing opinions (everyone has a position on stuffing), a team that needs to collaborate and delegate, and a retrospective built into the cleanup conversation.

Every PM concept maps onto it cleanly. Walk through all seven steps with Thanksgiving first, then introduce the vocabulary. By the time you say "critical path," they already know what it means. They just learned it with a turkey.

A companion presentation and worksheet are in the `tpm-templates` repo: [PM: A Thanksgiving Story](https://github.com/ChefPlex/tpm-templates).

### The Contractor Analogy for the PM Role

When someone asks what a project manager actually does, the instinct is to list tasks: run meetings, manage schedules, track risks. That answer is accurate and immediately forgettable.

Try this instead: "You know when you hire a contractor to remodel your kitchen? The contractor doesn't do all the work themselves - they have electricians, plumbers, tile people, cabinet installers. The contractor's job is to make sure the right people show up in the right order, nothing blocks anything else, you know what is happening and when, and the kitchen is done when they said it would be. That is a project manager."

This lands because almost everyone has hired a contractor, watched a family member hire one, or been one. It puts the PM role in a context where the function makes intuitive sense.

Follow with: "Now imagine the kitchen is a software product, and the electricians are engineers, and the tile people are QA, and you're the contractor. That is the job."

### Day in the Life Before Concepts

Before any slide about what PMs do, spend five minutes on a real Day in the Life. Not a flowchart - a narrative. What does a PM's morning look like? What is in their inbox? What meeting are they walking into and why does it matter? What fires are they managing?

Make it concrete and slightly messy, because that's what the job actually is. Students who have worked in restaurants and retail have a high tolerance for operational complexity and a low tolerance for sanitized job descriptions that don't match reality. Give them the real version and they will trust the rest of what you teach.

### The WAN Outage Case Study

From the Project Prep deck: a network operations incident where a WAN outage was escalated incorrectly, communication broke down across teams, and the root cause (a line card failure, not a WAN issue) wasn't identified until well after resources had been mobilized unnecessarily.

This case study works because it shows the cost of poor communication and unclear ownership in a situation that feels urgent and real. The PM isn't in the case study - that's the point. Someone should have been playing that coordination role. Walk through who should have done what, and you've just taught escalation paths, role clarity, and communication protocol without putting any of that vocabulary on a slide first.

For career changers who have worked in high-stakes operational environments - restaurants during a dinner rush, retail during a holiday weekend, warehouse fulfillment - this translates immediately. They have lived the version where there was no coordinator and everyone found out what that costs.

---

## The Concepts, in the Order That Works

### Start Here: What Is a Project?

A project is a temporary endeavor with a beginning, an end, and a unique result. It is not ongoing operations. Making coffee every morning is operations. Designing and building a new coffee program for 50 locations is a project.

This distinction matters because career changers often come from operational roles and need to understand that PM isn't about running the recurring work - it's about running the work that's different, bounded, and has a finish line.

### Scope First, Always

Scope is what you agreed to deliver, and just as importantly, what you didn't agree to deliver.

The most intuitive way to explain scope is through the absence of it. Tell a story where scope wasn't defined and someone ended up building something different from what was asked for, or delivered half of what was expected, or spent months on a feature nobody wanted. Every person in the room has a version of this story from their own life. Ask for it. Let them tell it. Then name what they just described.

Scope creep - requirements that grow without corresponding adjustments to timeline or budget - is equally intuitive once you frame it right. Ask: has anyone ever agreed to do one thing and then ended up doing five things because they kept saying yes to small additions? That is scope creep. The fix is not to be inflexible. The fix is to make the additions visible and have an honest conversation about what adjusting for them costs.

The key mechanic to teach: every change to scope is a conversation about time, cost, or both. Not a negotiation - a conversation. The PM's job is to make that conversation happen, not to prevent change.

### Stakeholders: Start With Who Has a Stake

Don't define stakeholders as "anyone with an interest or concern in the business." That's accurate and it means nothing to someone who has never worked in a formal project context.

Instead: who do you need something from, who needs something from you, and who will be affected by what you do whether or not they're involved? That is your stakeholder list.

The practical skill is identification - people miss stakeholders all the time, usually the ones who show up at the end with opinions about a product they were never consulted on during development. Teach identification with examples. Ask the room to think of a decision a previous employer made that affected them and that they had no input into. That is a stakeholder who was not engaged.

The follow-on concept is engagement: knowing what each stakeholder needs from you, and at what frequency. Not everyone needs the same update at the same time. A sponsor needs a different view than a team member.

### The Triple Constraints

Scope, schedule, cost. The iron triangle. Squeeze one, the others feel it.

This is intuitive for anyone who has managed a budget, planned a party, or run a kitchen. You can have it fast, you can have it cheap, you can have it exactly as specified - pick two, argue about the third.

The teaching moment isn't the concept itself - it's what to do with it. When a stakeholder asks for more scope without more time or money, the PM's job isn't to say yes or no. It's to say: here is what that costs, and here is what we can do about it. Put the decision back where it belongs - with the person who has the authority to make it.

### Requirements: Gather, Document, Process, Repeat

You gather, you document, you get feedback, you filter, you break the big ideas into smaller ones, and then you do it again, because requirements change. The heading says Repeat for a reason.

The practical lesson is about documentation. In a verbal culture - which most career changers come from - decisions are made in conversation and then lost. Requirements documented in writing create a record that protects everyone: the PM, the team, and the stakeholder who will otherwise remember the conversation differently six months later.

Teach documentation not as bureaucracy but as a memory aid for the whole project. The requirement that's not written down is the requirement that causes a problem at go-live.

### Risk: Not Everything Deserves a Plan

The instinct is to treat all risks equally. It is not the right instinct.

Risk has two dimensions: likelihood and impact. A risk that is likely and high-impact needs a mitigation plan. A risk that's unlikely and low-impact needs to be acknowledged and set aside. A risk that is likely and low-impact needs monitoring. A risk that's unlikely but catastrophic needs a contingency even if you never use it.

The practical skill is triage. You can't mitigate every risk - you'll spend all your time managing risks that never materialize while the ones that do catch you unprepared. The PM's job is to identify, rate, and prioritize. Then focus attention and resources on the risks that actually matter.

The Paleo cousin in the Thanksgiving deck is a risk. Medium likelihood, low impact. The fix is a big salad. That is proportionate mitigation. Do not build a whole parallel menu. Cover 80% of the concern and move on.

### The Project Lifecycle

Whatever methodology you use - Waterfall, Agile, something in between - every project has phases. Assess, plan, develop, deploy, manage. Or: feasibility, planning, design, production, turnover. The names change; the underlying shape does not.

For career changers, the most useful thing to teach is that the lifecycle isn't a straight line you walk from left to right. You will revisit phases. Planning does not end when execution begins. You will find things in execution that require you to replan. That's not failure - that's how projects work in the real world.

The second most useful thing: know where you're in the lifecycle at all times, and know what artifacts should exist at each phase. If you're in execution and there's no project charter, someone skipped something important. The lifecycle is a map. If you know where you're, you can figure out what is missing.

### Communication Is the Actual Job

The DITL slide from ProSkills 101 lists communication first and in all caps. That was deliberate.

Everything else a PM does - planning, tracking, risk management, stakeholder engagement - is in service of communication. The PM is the person who makes sure the right people know the right things at the right time. When that doesn't happen, projects fail regardless of how good the plan is.

For career changers, this is often the easiest concept to grasp and the hardest to execute in practice. Communication in a corporate environment has norms that aren't obvious from the outside: who gets CC'd on what, how to write a status update that an executive will actually read, when to escalate and to whom, how to deliver bad news without creating panic. Those norms take time to learn. Teach the principle and be honest that the specifics come with practice.

### Agile: Not a Replacement for Discipline

Agile gets introduced to career changers as a contrast to Waterfall, and then sometimes as a solution to all the problems with Waterfall. Neither framing is accurate.

The Agile Manifesto is worth reading in full, in the original, once. It's four value statements that describe a set of priorities - not a methodology, not a process, and explicitly not a reason to skip documentation or planning. The opening line is "we're uncovering better ways of developing software by doing it and helping others do it." That's a statement of ongoing learning, not a permission slip for chaos.

The practical lesson for career changers: Agile means iterating on real working output rather than planning everything up front and hoping the plan survives contact with reality. It means shorter feedback loops and faster course correction. It does not mean no plan. It does not mean no documentation. It does not mean requirements do not matter.

Whatever your shop uses - Scrum, Kanban, SAFe, something hybrid - the underlying skill is the same: communicate clearly, deliver incrementally, learn from each iteration.

---

## Concepts That Trip People Up

### Manager vs. Leader

Most PM curricula spend time on this distinction. It is worth covering, but do not let it become abstract.

The practical version: managers produce order and consistency. Leaders produce change and movement. A PM needs to do both depending on the moment. In a stable execution phase, you are managing. When the project hits a wall and the team needs to find a new path, you're leading. The skill is knowing which mode the moment requires.

For career changers who are early in their professional lives, the distinction between managing and leading is less important than understanding that influence without authority is a real and learnable skill. Most PMs don't have direct authority over the people doing the work. They get things done through relationships, communication, and credibility. That is worth saying out loud.

### Functional vs. Matrix vs. Projectized Orgs

This concept matters because it determines how much authority a PM actually has, where the team's loyalty lies (to the PM or to their functional manager), and how decisions get made.

Teach it with the question: who does your team work for when they aren't on your project? If they go back to a functional manager who controls their reviews and their career - that's a functional or matrix org. If the project IS their team and their home - that's projectized. The implication is practical: in a matrix org, you negotiate for people's time with their functional managers. That is a political skill as much as a PM skill.

Most career changers entering tech will land in matrix environments. Knowing this ahead of time removes some of the confusion about why people who are nominally "on your project" keep getting pulled into other things.

### Ethics Is Not Optional Material

The Project Prep deck treated ethics as a full module, not an afterthought. That was right.

The practical framing: answer "what should I do?" rather than "what would I do?" Those two questions lead to different places. The PMI Code of Ethics covers honesty, responsibility, respect, and fairness - not as platitudes but as practical guidance for situations PMs actually encounter: conflicts of interest, inaccurate reporting, stakeholders who want you to shade the truth in a status update, team members who aren't performing and need to be managed out.

For career changers who are new to professional environments, this is also a conversation about norms that may not be obvious: what counts as a conflict of interest, why you don't commit the organization to things that aren't yours to commit, what to do when you're asked to do something that feels wrong. Give them a framework before they need it.

---

## What to Do in the Room

### The Introduction Round

Start every session with three questions: name, technology experience, what they want to do, and what they think is blocking them.

Do not skip this. It is not just icebreaker protocol. It tells you how technical the room is, what aspirations look like, and where the anxiety lives. Someone who says "I want to be a PM but I don't have any tech background" needs a different pitch than someone who says "I've been in IT support for three years and want to move into program management." The content is the same; the framing is different.

### The Exercise Structure That Works

Give the concept. Give the example. Let them do it.

For Year Up sessions, the standard exercise was: take a real thing from your life - planning an event, managing a household move, organizing a community project - and apply the PM framework to it. Define the scope. Name the stakeholders. Identify the constraints. Map the risks. Two to three minutes to present to the room.

This works because it forces application immediately, it uses material they already know, and it surfaces the gaps between understanding the concept and being able to use it. The gap is always smaller than they expect. That is the point.

### When the Room Gets Lost in the Vocabulary

It will happen. Someone will ask what "deliverable" means, or why "scope" is a noun in one sentence and a verb in another, or what the difference between a milestone and a deliverable is.

Stop. Answer the question. Do not treat vocabulary questions as interruptions. Vocabulary questions are the most important questions a career changer can ask, because it means they're trying to integrate the concept rather than just pass the session.

Keep a running translation table on a whiteboard if you've one. Plain English on one side, PM vocabulary on the other. By the end of the session, they will have built their own glossary.

### Do Not Over-Certify

Year Up students asked regularly: do I need a PMP to get a PM job? The honest answer is no - not at entry level. The PMP is a mid-career credential that requires documented PM experience as a prerequisite anyway.

What they need first: the vocabulary, the concepts, the ability to apply the framework to a real problem, and enough self-confidence to say "I managed that project" about things they have already done without formal PM titles. Most people have managed projects. They just have not been calling it that.

The path is: vocabulary and concepts first, then internship experience where they can practice, then entry-level roles with PM responsibilities, then the credential when it makes sense. Don't let the credential become a reason to feel unqualified before they have started.

---

## The Personal Development List

From the Project Prep closing session - books and activities that help develop the PM skillset for people who are early in their careers. These held up.

Reading worth assigning or recommending:

- "The 7 Habits of Highly Effective People" by Stephen Covey - not a PM book, but the habits (proactivity, beginning with the end in mind, thinking win-win, seeking first to understand) are the behavioral foundation of effective PM work
- "How to Win Friends and Influence People" by Dale Carnegie - dated in tone, still accurate about how influence actually works
- "The Mythical Man-Month" by Fred Brooks - for anyone heading into software PM, essential reading on why adding people to a late project makes it later

Activities that build PM-relevant skills:

- Toastmasters - public speaking and facilitation are core PM skills, and Toastmasters is free and widely available
- Any role that requires coordinating multiple people toward a deadline - organizing a community event, running a volunteer crew, coaching a team
- Tabletop role-playing games (this was on the Year Up list and it's not a joke - Dungeons and Dragons and similar games build systems thinking, collaborative problem-solving, and comfort with ambiguity)

---

## Source Material

This guide was distilled from four decks taught at Year Up San Francisco through Taos Mountain, 2015-2016. The original presentations are archived in [`year-up/`](year-up/) alongside this file. They're in their original .ppt format and reflect the specific program context - some content will need adjustment for different audiences.

The Thanksgiving deck referenced throughout this guide has been rebuilt as a modern presentation and lives in [`tpm-templates`](https://github.com/ChefPlex/tpm-templates) as a standalone teaching resource.

---

*Eric White - Director TPM, Public Glass Board President, Year Up guest instructor 2015-2016*
*[github.com/ChefPlex](https://github.com/ChefPlex)*
