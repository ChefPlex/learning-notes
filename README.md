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

---

## A Note on Currency

Security and AI are fast-moving fields. Notes here reflect my understanding at the time they were written. Where I know something has changed, I will update it. Where I am uncertain, I will say so.

If something here is wrong or outdated, open an issue. Getting it right is more important than being right the first time.

---

*Maintained by [Eric White](https://www.linkedin.com/in/edwhite) | [ChefPlex](https://github.com/ChefPlex)*
