# SANS LDR553: Cyber Incident Management -- Course Notes

**Course:** LDR553 Cyber Incident Management  
**Instructor:** Steve Armstrong-Godwin  
**Completed:** May 2026

---

## Why This Course

I've spent most of my career on the program side of security - building the encryption programs, the PKI infrastructure, the compliance frameworks. The incident side was always adjacent work: something happened, the IR and SOC teams ran the response, the TPM showed up to track remediation actions and report status to leadership.

LDR553 made me rethink that division. The skills the course is actually teaching aren't technical incident response skills - those belong to the SOC and IR engineers. The skills are about leading the humans in the room when the facts are incomplete, the executives are impatient, and the clock is running. That is TPM territory.

The gap between a technical team that understands what is happening and an executive audience that needs to make decisions about it doesn't close itself. This course gave me better tools for closing it.

---

## What the Course Covers

LDR553 runs five days through a fictional company called Submarine Studios, which experiences a progressively more complex cyber incident throughout the week. Each day adds new complications: the attacker escalates, a third party is involved, regulators come into the picture, and eventually you're dealing with questions about AI systems, ransomware, and regulated manufacturing. Nine case studies total, building on each other.

The lab structure maps roughly to this:

| Lab | Focus |
|-----|-------|
| 1.2 Initial Incident Briefing | Turning a chaotic report into a managed incident |
| 1.3 CIMTK: The Grid | Structured scoping questions for the first hour |
| 1.5 Making GPTs in OpenAI | Using GenAI to draft executive briefs and simulate stakeholder reactions |
| 2.1 Briefing the Execs | Executive 3x5 format under pressure |
| 2.2 Dealing with the Attackers | Attacker contact, extortion handling, when to engage |
| 2.3 Drafting a Public Statement | Getting the external communications right |
| 2.6 What is a Good RCA | Running a retrospective that generates real learning |
| 3.1 Choosing Cyber Training Exercises | How to design an exercise program |
| 3.2 Planning a Hot Seat Exercise | Running tabletop exercises that build real capability |
| 3.3 Submitting a Request for Intelligence | Working with threat intelligence |
| 3.4 Reviewing a Third-Party Incident Notification | Supplier incidents as a major incident until proven otherwise |
| 3.6 Planning and Handling the Third-Party Call | Getting real answers from a vendor in crisis mode |
| 3.7 Preparing to Update the Execs | Executive briefing discipline in the middle of a complex incident |
| 4.1 Reviewing Incident Timelines | How timelines drive decisions, not just document history |
| 4.2 Credential Loss Impact Assessment | Blast radius thinking - it is never just one password |
| 4.3 We Paid the Wrong Account | Business Email Compromise investigation |
| 4.4 The Cloud Bill Is Vast | Cloud abuse, rogue compute, IAM key exposure |
| 5.1 Updating the Public Statement | Evolving communications as facts change |
| 5.4 Capstone | Full incident management cycle, end to end |

---

## The Ideas That Stuck

### Manage uncertainty explicitly

The most useful framework from the course is simple: separate everything into facts, assumptions, unknowns, decisions, and constraints. Every briefing, every update, every conversation with leadership should make this separation visible.

A fact is evidence-backed, tied to a source and a time. An assumption is a reasonable theory you're using to prioritize work - stated as an assumption, not presented as a fact. An unknown is a material question that, if answered differently, would change what you do next.

The reason this matters: under pressure, assumptions migrate into facts. Someone says "we think the domain is compromised" in hour one and by hour six it has become "the domain was compromised" in the executive briefing - without the evidence actually changing. That is how incidents get mismanaged. Explicit uncertainty tracking prevents it.

### The 3 Whats executive briefing format

The course pushes hard on a five-bullets-per-section format for executive updates:

- **What happened?** Confirmed facts only. Scope, systems, data, identities. What is confirmed vs. assumed.
- **What is happening now?** Active workstreams. Containment status. External support engaged.
- **What happens next?** Decisions needed. Risks that may worsen. Next milestone. When is the next update.

The discipline here is keeping each section to five bullets or fewer, and never letting the technical detail outrun what executives can act on. An executive briefing that makes the IC feel thorough but leaves the executive unable to make a decision has failed.

### Credentials are a blast-radius problem

One of the most practically useful reframes from the course: a credential compromise is never just one password. It's sessions, tokens, OAuth grants, app passwords, API keys, SSH keys, mailbox rules, shared files, recovery accounts, and every other place that credential touches.

Resetting a password without killing sessions is not closure. Rotating an API key without reviewing what it accessed isn't closure. The credential loss impact assessment lab made this concrete: the checklist for a single compromised account is longer than most organizations run through.

### Suppliers start as major incidents

The third-party incident management content was the part of the course I found most practically useful for TPM work. The default posture the course teaches: treat a supplier security notice as a major incident until evidence proves your access, data, service, and customer exposure aren't affected.

Supplier legal notices are almost never enough. A vague statement that there was "an incident" and the supplier has "taken steps" to address it's not information. The course gives a structured RFI - request for information - with specific questions that elicit real answers: what was the timeline, what of ours was accessible, which of our credentials or access paths existed, what has been revoked.

The confidence scoring framework for supplier answers is practical: high confidence means specific logs, timestamps, scope, access lists, and containment evidence. Low confidence means generic reassurance, no named owner, and shifting answers. Low confidence means maintain worst-case posture.

### Communications is an operational workstream

Not an add-on, not something the PR team handles independently - an integrated workstream with its own tracker, its own approval process, and its own cadence. Every external or broad internal message needs to be drafted, validated against the evidence register, reviewed by Legal and Comms, approved by a named person, and recorded.

The course makes this concrete through a communications tracker with fields for: message ID, audience, exact message text or link, who can release it, who delivers it, status, and release details. This is the difference between incident communications that are controlled and communications that happen because someone sent an email without thinking.

### Public statements should be narrow and verified

The public closeout guardrails section was a direct counterweight to the instinct to say more than you know. The guidance: acknowledge impact and actions taken at a high level, thank partners where confirmed, point to support resources. Avoid: mixing unrelated incidents into one statement, speculating about actor identity or root cause, disclosing internal control gaps unnecessarily, contradicting prior filings.

The framing I found most useful: no message should outrun the evidence. Draft early, approve carefully, track everything.

### The IC does not need perfect knowledge to manage well

The final line of the capstone playbook: "The IC doesn't need perfect knowledge to manage well. The IC needs clear ownership, evidence discipline, honest uncertainty, controlled communications, and a repeatable rhythm for decisions."

That is the summary of the course. And it applies well beyond incident management.

---

## The GenAI Component

Lab 1.5 was genuinely interesting - building GPTs in OpenAI to assist with incident management work. The practical applications the course explored: drafting executive briefings from raw incident notes, simulating stakeholder reactions to test communications before sending them, and structuring analysis of complex evidence logs.

The AI security scenario in the capstone (Lab 5.4 in the full playbook) covered GenAI application compromise specifically - prompt injection, authorization failures, data exposure across tenants. The key point: authorization must be enforced server-side, not through prompt wording. A system prompt that says "only share data with authorized users" isn't an access control. It is a suggestion.

---

## What I Built: The Cyber Incident Management Playbook

The capstone deliverable was a full operational playbook synthesizing the week's labs into a reusable reference. It covers:

- Rapid Response Card (first 15 minutes)
- Operating principles and uncertainty discipline
- Severity model and command structure
- First 90-minute checklist (three phases)
- Scoping, evidence, and timeline management
- Battle rhythm and executive reporting
- Communications playbook with audience matrix and approval workflow
- Law enforcement, regulators, insurers, and outside counsel
- Threat actor and extortion handling
- Third-party and supply-chain incident management
- Impact assessment and counter-compromise sequencing
- Scenario runbooks (malware, BEC, cloud abuse, GenAI compromise, ransomware, regulated manufacturing)
- Recovery, closeout, RCA, and exercise program
- Appendix templates (intake form, 3x5 brief, action tracker, decision log, evidence register, comms tracker, third-party RFI, credential reset tracker, counter-compromise tracker, RCA action register)

The playbook lives in `security-program-playbooks` as a sanitized reference document.

---

## Recommended For

Security TPMs, incident commanders, and anyone who sits between technical response teams and executive leadership during a security event. The technical IR skills aren't the gap this course closes - the gap it closes is the leadership and communications discipline that keeps a complex incident from being managed by whoever is loudest in the room.

If you work in an organization that runs tabletop exercises, the exercise program design content alone (Labs 3.1 and 3.2) is worth the time.

---

## Course Resources

- Course site: [ldr553.com](https://ldr553.com)
- Instructor: [Steve Armstrong-Godwin on LinkedIn](https://www.linkedin.com/in/steveag/)
- SANS course catalog: [sans.org/cyber-security-courses/cyber-incident-management/](https://www.sans.org/cyber-security-courses/cyber-incident-management/)

---

*Notes completed May 2026. These reflect my own synthesis and takeaways - not official SANS course material.*
