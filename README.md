# learning-notes

Notes on things I am learning, thinking about, and trying to understand better. Mostly centered on security engineering, distributed systems, program management craft, and the intersection of AI with all of the above.

This is not a polished reference library. It is a working notebook made public on the theory that thinking out loud is more useful than thinking in private - for me and occasionally for whoever stumbles across it.

Some of this will be wrong. Some of it will get updated as I learn better. That is the point.

---

## What Is Here

### Technical Concepts

| Note | What It Covers |
|------|---------------|
| [System Design Concepts for Security TPMs](system-design-concepts-for-tpms.md) | Working notes on the distributed systems and security concepts that come up most in large-scale platform security programs - encryption, PKI, TLS, zero trust, compliance frameworks, and emerging AI security considerations. Written from a TPM perspective: enough to be useful in the room, not a deep implementation guide. |

### Craft and Practice

| Note | What It Covers |
|------|---------------|
| [TPM Craft: Notes on Running Programs at Scale](tpm-craft-notes.md) | Things learned running security, infrastructure, and compliance programs at enterprise scale that are not in any certification curriculum. On starting programs, planning, execution, stakeholders, teams, reporting, and finishing. Updated as the work teaches new things. |
| [Introducing PM Concepts to Career Changers](pm-for-career-changers.md) | A teaching guide for explaining project management to people who have never worked in a formal PM environment - career changers, early-career professionals, and anyone coming from a non-corporate background. Developed from teaching at Year Up (2015-2016). Covers framing, analogies, common stumbling blocks, and what actually lands in a room versus what sounds good in a curriculum. |

### Course Notes

| Note | What It Covers |
|------|---------------|
| [SANS LDR553: Cyber Incident Management](sans-ldr553-course-notes.md) | Notes from completing SANS LDR553, taught by Steve Armstrong-Godwin. The course is not about technical IR - it is about leading the humans in the room when facts are incomplete and executives are impatient. Covers the 3 Whats executive briefing format, uncertainty discipline, credential blast-radius thinking, supplier incident management, and the GenAI component. Includes a summary of the capstone playbook produced during the course. |

### Source Materials

The following materials from the Year Up teaching work are archived here for reference. They are the raw source behind the career changers guide.

| File | What It Is |
|------|-----------|
| [Year_Up_-_ProSkills_101_Part1_Fall2016.ppt](Year_Up_-_ProSkills_101_Part1_Fall2016.ppt) | ProSkills 101, Part 1 - Introduction to project management for Year Up students. Covers the PM role, project lifecycle, stakeholders, scope, requirements, constraints, risk, and Agile basics. Fall 2016. |
| [Year_Up_-_ProSkills_101_111715v02.ppt](Year_Up_-_ProSkills_101_111715v02.ppt) | ProSkills 101 - Earlier version co-taught with Taos Mountain colleagues. Same core content, November 2015. |
| [Year_Up_-_ProSkills_102_20151124_v02.ppt](Year_Up_-_ProSkills_102_20151124_v02.ppt) | ProSkills 102 - Second session covering tech org structures, conflict resolution, leadership versus management, motivation theory, and interviewing. November 2015. |
| [Year_Up_-_Project_Prep_v_02_19.ppt](Year_Up_-_Project_Prep_v_02_19.ppt) | Project Prep - Advanced session on PM effectiveness, the 7 Habits of an Effective PM, team dynamics, organizational structures, ethics, and a case study. January 2016. |

These decks are in their original .ppt format. They are not polished for a general audience - they were working teaching materials used in a specific program context. The career changers guide extracts what held up and leaves behind what was context-specific to Year Up.

---

## What Is Coming

### Technical Concepts

| Note | What It Will Cover |
|------|-------------------|
| Cryptography Fundamentals for TPMs | Symmetric vs. asymmetric encryption, hashing, digital signatures, key exchange - enough to understand what the engineering team is doing and why it matters |
| Identity and Access Management Concepts | Authentication vs. authorization, OAuth, SAML, MFA, privileged access management - the concepts behind IAM programs |
| Cloud Security Architecture | Shared responsibility model, cloud-native security controls, multi-cloud security considerations - what changes when the infrastructure is someone else's |
| AI/ML Security: A TPM's Field Guide | Prompt injection, training data exposure, model governance, the emerging compliance landscape for AI systems - notes from the current frontier |

### Craft and Practice

| Note | What It Will Cover |
|------|-------------------|
| Book Notes: An Elegant Puzzle | Will Larson's systems-oriented approach to engineering management - useful reading for TPMs thinking about organizational scale |
| Book Notes: Staff Engineer | Tanya Reilly's framework for operating at senior individual contributor level - relevant for TPMs thinking about influence without authority |
| Lessons from Leading Large-Scale Encryption Programs | Patterns and anti-patterns from running encryption modernization at scale - what works, what does not, and what nobody tells you at the start |
| Working with Compliance Teams | How to build a productive working relationship with GRC, what they need from you, and how to avoid the most common friction points |

---

## How I Think About This Repo

The job of a Technical Program Manager in security is to sit at the intersection of three things that do not naturally talk to each other: engineering teams who think in systems and code, compliance and legal teams who think in requirements and controls, and executive stakeholders who think in outcomes and risk.

Being effective at that intersection requires more than process skills. It requires enough technical fluency to understand what the engineering team is building and why it matters, enough compliance literacy to know when a regulatory requirement changes the plan, and enough domain knowledge to make the tradeoffs visible to the people who need to make decisions.

These notes are how I build and maintain that fluency. They are written for TPMs, not engineers - the goal is practical understanding, not implementation depth.

The teaching materials here come from a different angle - not what I am learning, but what I have learned well enough to explain to someone who is learning it for the first time. That is a different kind of test, and a useful one.

---

## A Note on Currency

Security and AI are fast-moving fields. Notes here reflect my understanding at the time they were written. Where I know something has changed, I will update it. Where I am uncertain, I will say so.

If something here is wrong or outdated, open an issue. Getting it right is more important than being right the first time.

---

## Related Repos

- [tpm-templates](https://github.com/ChefPlex/tpm-templates) - Program lifecycle templates, including the PM: A Thanksgiving Story teaching deck
- [tpm-toolbox](https://github.com/ChefPlex/tpm-toolbox) - Tools and trackers

---

*Maintained by [Eric White](https://www.linkedin.com/in/edwhite) | [ChefPlex](https://github.com/ChefPlex)*
