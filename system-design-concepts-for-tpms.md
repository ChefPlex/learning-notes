# System Design Concepts for Security TPMs

You don't need to be a systems architect to run platform security programs. But you need to understand the systems well enough to ask the right questions, recognize when an engineering decision has security implications, and translate technical tradeoffs into language a stakeholder can act on.

These are working notes on the distributed systems and security concepts that come up most often in large-scale platform security programs. Written from a TPM perspective - not a deep dive into implementation, but enough to be useful in the room.

---

## Encryption

### Encryption in Transit vs. Encryption at Rest

**In transit** means data is encrypted while moving between systems - service to service, client to server, across network boundaries. The standard mechanism is TLS (Transport Layer Security).

**At rest** means data is encrypted while stored - on disk, in a database, in object storage. When someone says "encrypt the database," they usually mean at rest.

Both matter. A system that encrypts at rest but not in transit protects data from someone who steals a disk but not from someone who intercepts network traffic. A system that encrypts in transit but not at rest protects data on the wire but not if the storage layer is compromised.

**What this means for a program:** Encryption programs typically need to address both surfaces separately. Encryption in transit programs often involve TLS modernization across services. Encryption at rest programs often involve key management infrastructure and storage layer changes. They're different engineering problems with different teams, different tooling, and different timelines.

### TLS

TLS (Transport Layer Security) is the protocol that encrypts data in transit. You will hear version numbers: TLS 1.0, 1.1, 1.2, 1.3.

TLS 1.0 and 1.1 are deprecated - they have known vulnerabilities and are no longer considered secure. Most compliance frameworks require 1.2 or higher; 1.3 is current and preferred.

A TLS modernization program typically involves: inventorying all services and endpoints, identifying which are still running 1.0 or 1.1, remediating each service, and verifying through scanning that the old versions are gone. The long tail - legacy services, third-party integrations, embedded clients - is always harder than it looks.

**What a TPM needs to know:** TLS version is a binary compliance question in most regulatory frameworks. Either you meet the minimum version requirement or you do not. There is no partial credit. That means tracking coverage to 100%, not to "substantially complete."

### PKI and Certificate Lifecycle

PKI (Public Key Infrastructure) is the system that issues, manages, and revokes digital certificates. Certificates are what makes TLS work - a certificate tells a client that the server it's talking to is who it claims to be.

Certificates have expiration dates. An expired certificate breaks service - most clients will refuse to connect to a server with an expired cert. Certificate lifecycle management is the discipline of making sure certificates get renewed before they expire.

**What a TPM needs to know:** Certificate expiration events are predictable outages. A well-run PKI program has automated renewal, an inventory of all certificates and their expiration dates, and alerting that surfaces upcoming expirations before they become emergencies. If you're running a program that touches certificate infrastructure, ask how renewals are being automated and what the alert threshold is for upcoming expirations.

### HSM (Hardware Security Module)

An HSM is a physical device that generates, stores, and manages cryptographic keys. Keys stored in an HSM can't be exported in plaintext - the HSM performs cryptographic operations with the key without ever exposing it.

Enterprise HSMs (Thales, Entrust, formerly Gemalto) are the standard in regulated environments. They're expensive, operationally complex, and compliance-required in many contexts (PCI HSM requirements, for example).

**What a TPM needs to know:** HSM procurement, provisioning, and integration have long lead times. If your program depends on HSM infrastructure, start that work earlier than you think you need to.

---

## Distributed Systems Concepts

### Services and Service Boundaries

Modern platform architectures are built from many small services that communicate with each other over a network. Each service boundary is a potential attack surface - a place where data moves from one service to another and needs to be protected.

A security program at enterprise scale often involves tracking and securing hundreds or thousands of service-to-service communication paths. The challenge is that the inventory is rarely complete, services get added without going through a security review process, and the teams that own each service are distributed across the organization.

**What a TPM needs to know:** Service inventory is often the hardest part of a platform security program. Before you can encrypt all service-to-service traffic, you need to know all the traffic. Before you can remediate all vulnerable services, you need to know all the services. Budget time and engineering resources for discovery, not just remediation.

### Certificates and mTLS

Standard TLS authenticates the server to the client - you know you're talking to the right server. mTLS (mutual TLS) authenticates both sides - the server also knows it's talking to the right client. This is important for service-to-service communication inside a platform, where you want to ensure that only authorized services can call each other.

mTLS is common in zero trust architectures and service mesh implementations (Istio, Linkerd, etc.).

**What a TPM needs to know:** mTLS programs often involve rolling out a service mesh or a certificate management system across a large number of services simultaneously. That is a complex, high-coordination migration. Understand the rollout sequence, the rollback plan, and what happens to services that can't be migrated on the primary timeline.

### Zero Trust

Zero trust is a security model based on the principle that no user, device, or service should be trusted by default - even inside the network perimeter. Every request is authenticated, authorized, and encrypted regardless of where it originates.

The contrast is with traditional perimeter security: trust everything inside the firewall, distrust everything outside. Zero trust treats the internal network as untrusted by default.

Implementing zero trust at enterprise scale is a multi-year program - it touches identity, network, endpoint, and application layers simultaneously.

**What a TPM needs to know:** "Zero trust" is both a legitimate security model and a marketing term that gets applied to almost anything. When you hear it in a program context, ask specifically: which zero trust principles apply here, what is in scope for this program, and how does this connect to the broader zero trust architecture (if one exists)?

---

## Compliance Frameworks

### SOX (Sarbanes-Oxley)

US law requiring public companies to maintain accurate financial records and adequate internal controls. IT controls (access controls, change management, audit logging) are a significant part of SOX compliance.

**TPM relevance:** If your program touches financial systems, access to financial data, or the change management process for financial systems, it likely has SOX implications. SOX controls need to be designed in from the start - retrofitting them is expensive.

### PCI-DSS (Payment Card Industry Data Security Standard)

Industry standard for organizations that handle credit card data. Covers encryption, access control, network segmentation, logging, and vulnerability management.

**TPM relevance:** Any program touching cardholder data or the systems that process, store, or transmit it requires PCI compliance. PCI has specific requirements around encryption (TLS 1.2 minimum, specific cipher suites), access control, and audit logging.

### HIPAA (Health Insurance Portability and Accountability Act)

US law governing the privacy and security of health information. The Security Rule covers electronic protected health information (ePHI) - how it's stored, transmitted, and accessed.

**TPM relevance:** Any program at a healthcare organization or involving health data requires HIPAA analysis. Key controls: encryption of ePHI in transit and at rest, access controls, audit logging, breach notification procedures.

### FedRAMP (Federal Risk and Authorization Management Program)

US government framework for cloud services used by federal agencies. Rigorous and prescriptive - FedRAMP authorization is a significant program in itself.

**TPM relevance:** FedRAMP programs have strict timelines, extensive documentation requirements, and external assessors (3PAOs). Start compliance work early - FedRAMP authorization typically takes 12-18 months and can't be rushed at the end.

### SOC 2 (Service Organization Control 2)

An auditing standard for service organizations - cloud providers, SaaS companies - covering security, availability, processing integrity, confidentiality, and privacy. SOC 2 Type I is a point-in-time assessment; SOC 2 Type II covers a period of time (usually 6-12 months).

**TPM relevance:** SOC 2 Type II requires demonstrating controls over a period of time, not just at the audit date. That means programs that build controls need to be operational and documented well before the audit period begins.

---

## Security Operations Concepts

### MTTR (Mean Time to Remediate)

The average time between a vulnerability being identified and being fixed. One of the primary metrics for vulnerability management programs.

Different severity levels have different MTTR targets: critical vulnerabilities get days, high get weeks, medium get months. The targets are often defined by compliance frameworks or internal security policy.

**What a TPM needs to know:** MTTR is the metric that security and audit teams will ask about first. Make sure your vulnerability remediation program defines MTTR targets by severity at the start and tracks against them consistently.

### CVE and CVSS

CVE (Common Vulnerabilities and Exposures) is a standardized identifier for known security vulnerabilities. CVSS (Common Vulnerability Scoring System) is the scoring system that rates their severity on a 0-10 scale.

CVSS scores translate to severity buckets: Critical (9.0-10.0), High (7.0-8.9), Medium (4.0-6.9), Low (0.1-3.9).

**What a TPM needs to know:** Not all CVEs are equal. A Critical CVE in a widely deployed, internet-facing service is a different priority than a Medium CVE in an internal tool with no external exposure. Context matters - work with your security team to triage based on actual exposure, not just CVSS score.

### Defense in Depth

The security principle that multiple layers of controls are more effective than relying on any single control. If one layer fails, others remain.

Applied to a platform security program: encryption in transit plus encryption at rest plus access controls plus audit logging is more secure than any one of those alone - and the combination is what most compliance frameworks require.

**What a TPM needs to know:** When a security program is making tradeoffs due to resource constraints or timeline pressure, defense in depth is the framework for evaluating what to prioritize. A gap in one layer that's compensated by strength in another may be an acceptable interim state. A gap with no compensating control is a risk that needs to be named explicitly.

---

## AI and Security: Emerging Considerations

This section is intentionally brief - the field is moving fast and anything more specific would be outdated quickly.

**AI as an attack surface:** Models trained on sensitive data, APIs that accept user input, and AI-generated content pipelines all introduce new attack surfaces. Security programs for AI systems need to consider prompt injection, training data exposure, model inversion attacks, and output validation.

**AI in security operations:** Machine learning models are increasingly used for anomaly detection, threat hunting, and log analysis. These tools can surface signals that would otherwise be lost in the noise of large-scale platforms.

**What a TPM needs to know:** AI security isn't yet a mature discipline with established compliance frameworks and standard controls. Programs in this space require closer collaboration with security architects and researchers, and more tolerance for ambiguity in what "done" looks like.

---

## Further Reading

These are worth the time if you're going deeper in any of these areas:

- *Designing Data-Intensive Applications* by Martin Kleppmann - distributed systems fundamentals
- *The Web Application Hacker's Handbook* - attack surface understanding
- *Zero Trust Networks* by Evan Gilman and Doug Barth - zero trust architecture in practice
- NIST SP 800-53 - the reference catalog for security controls used in US federal compliance
- OWASP Top Ten - the standard reference for web application security risks

---

*These are working notes, updated as I learn and as the field evolves. Last updated May 2026.*
