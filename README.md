# learning-notes

Notes on things I'm learning, thinking about, and trying to understand better. Mostly centered on security engineering, distributed systems, program management craft, and the intersection of AI with all of the above.

This is not a polished reference library. It's a working notebook made public on the theory that thinking out loud is more useful than thinking in private - for me and occasionally for whoever stumbles across it.

Some of this will be wrong. Some of it will get updated as I learn better. That is the point.

---

## What Is Here

### Technical Concepts

| Note | What It Covers |
|------|---------------|
| [System Design Concepts for Security TPMs](system-design-concepts-for-tpms.md) | Working notes on the distributed systems and security concepts that come up most in large-scale platform security programs - encryption, PKI, TLS, zero trust, compliance frameworks, and emerging AI security considerations. Written from a TPM perspective: enough to be useful in the room, not a deep implementation guide. |
| [Cryptography Fundamentals for TPMs](cryptography-fundamentals-for-tpms.md) | Symmetric and asymmetric encryption, hashing, digital signatures, certificates and PKI, key management, deprecated algorithms, and the questions worth asking during technical reviews. Written for TPMs who need to understand what the engineering team is building without becoming cryptographers. |
| [Lessons from Leading Large-Scale Encryption Programs](lessons-from-large-scale-encryption-programs.md) | What nobody tells you at the start. Seven lessons from encryption modernization at scale: why analysis time is the thing to protect, executive visibility as a lever rather than reporting, automating the count so status is observed instead of self-reported, why priority is displacement and does not propagate down the chain on its own, what we were wrong about at the outset, and how these programs actually end - at diminishing returns, with the scope reduced deliberately, not at 100 percent. Companion piece: [Encryption Program Playbook](https://github.com/ChefPlex/security-program-playbooks/blob/main/encryption-program-playbook.md) in security-program-playbooks. |
| [Lessons from Putting AI Into a Company](lessons-from-putting-ai-into-a-company.md) | What nobody tells you at the start. Seven lessons on AI adoption and governance: why you are never introducing AI but getting control of something already running, how fear and enthusiasm both distort the map, why the headcount objection is rational and what actually answers it, showing people it helps rather than mandating use, how a human review gate rots into a rubber stamp and how to calibrate friction to consequence, why buying paid accounts is a data-loss control rather than an enablement budget, and why provenance is the same question library science answered for the early web - who made this, who is answerable, and how do you get back to them. Companion piece: the [frameworks](https://github.com/ChefPlex/ai-automations/tree/main/frameworks) in ai-automations. |

### Craft and Practice

| Note | What It Covers |
|------|---------------|
| [TPM Craft: Notes on Running Programs at Scale](tpm-craft-notes.md) | Things learned running security, infrastructure, and compliance programs at enterprise scale that are not in any certification curriculum. On starting programs, planning, execution, stakeholders, teams, reporting, and finishing. Updated as the work teaches new things. |
| [Program Management for Career Changers](pm-for-career-changers.md) | A practical PM introduction for people coming in from other fields. The vocabulary, the lifecycle, the skills that actually matter, and how to get your first role - without the jargon and theory that make most PM training materials difficult to use. Developed from teaching professional skills to Year Up students. |

### Course Notes

| Note | What It Covers |
|------|---------------|
| [SANS LDR553: Cyber Incident Management](sans-ldr553-course-notes.md) | Notes from completing SANS LDR553, taught by Steve Armstrong-Godwin. The course is not about technical IR - it is about leading the humans in the room when facts are incomplete and executives are impatient. Covers the 3 Whats executive briefing format, uncertainty discipline, credential blast-radius thinking, supplier incident management, and the GenAI component. Includes a summary of the capstone playbook produced during the course. |

### Source Materials

| Folder | What It Contains |
|--------|----------------|
| [year-up/](year-up/) | Teaching materials from my time as a volunteer instructor with Year Up, a workforce development program for young adults entering tech careers. Four slide decks from the ProSkills and Project Prep curriculum (Fall 2015 and Fall 2016 cohorts). The Thanksgiving deck in this folder is the original source for the rebuilt [PM: A Thanksgiving Story](https://github.com/ChefPlex/tpm-templates/blob/main/PM_Thanksgiving_Story.pptx) in tpm-templates. See the [year-up README](year-up/README.md) for full context. |

---

## Where the AI Security Material Actually Lives

This section used to promise an "AI/ML Security: A TPM's Field Guide" covering prompt injection,
model governance, and the compliance landscape for AI systems. **Most of it got written, and none of
it got written here** - it shipped into the repos where it was useful instead:

| Topic | Where it landed |
|-------|----------------|
| Prompt injection, trust boundaries, permission-aware retrieval | [enterprise-rag-security](https://github.com/ChefPlex/security-program-playbooks/tree/main/enterprise-rag-security) in security-program-playbooks |
| Model governance, execution tiers, where AI belongs in a company | [frameworks](https://github.com/ChefPlex/ai-automations/tree/main/frameworks) in ai-automations |
| AI tooling under HIPAA and SOC 2, BAA gating, data classification | [AI Tooling in Regulated Environments](https://github.com/ChefPlex/security-program-playbooks/blob/main/ai-tooling-regulated-data.md) |

Leaving a "coming soon" up while the work sits finished in the next repo over is worse than never
having listed it, so the list is replaced with pointers. **The lesson generalizes: a per-repo roadmap
goes stale the moment work ships somewhere else, and nobody re-reads a roadmap to notice.**

## Still Unwritten

Honest about these, and they are not scheduled. They get written when there is something to say
that is not already said better elsewhere.

| Note | What It Would Cover |
|------|-------------------|
| Identity and Access Management Concepts | Authentication vs. authorization, OAuth, SAML, MFA, privileged access management - the concepts behind IAM programs |
| Cloud Security Architecture | Shared responsibility model, cloud-native security controls, multi-cloud security considerations - what changes when the infrastructure is someone else's |
| Working with Compliance Teams | How to build a productive working relationship with GRC, what they need from you, and how to avoid the most common friction points |
| Book Notes: An Elegant Puzzle | Will Larson's systems-oriented approach to engineering management |
| Book Notes: Staff Engineer | Tanya Reilly's framework for operating at senior individual contributor level |

---

## How I Think About This Repo

The job of a Technical Program Manager in security is to sit at the intersection of three things that don't naturally talk to each other: engineering teams who think in systems and code, compliance and legal teams who think in requirements and controls, and executive stakeholders who think in outcomes and risk.

Being effective at that intersection requires more than process skills. It requires enough technical fluency to understand what the engineering team is building and why it matters, enough compliance literacy to know when a regulatory requirement changes the plan, and enough domain knowledge to make the tradeoffs visible to the people who need to make decisions.

These notes are how I build and maintain that fluency. They're written for TPMs, not engineers - the goal is practical understanding, not implementation depth.

---

## A Note on Currency

Security and AI are fast-moving fields. Notes here reflect my understanding at the time they were written. Where I know something has changed, I will update it. Where I am uncertain, I will say so.

If something here is wrong or outdated, open an issue. Getting it right is more important than being right the first time.

---

*Maintained by [Eric White](https://www.linkedin.com/in/edwhite) | [ChefPlex](https://github.com/ChefPlex)*

## License

Copyright (c) 2026 Eric White. Licensed under [CC BY 4.0](LICENSE): use it, adapt it, put it to
work in your own program. Credit is the only condition.
