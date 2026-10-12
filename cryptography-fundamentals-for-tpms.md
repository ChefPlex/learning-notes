# Cryptography Fundamentals for TPMs

You don't need to be a cryptographer to run security programs. But you need enough fluency to understand what the engineering team is building, ask the right questions when something seems off, and translate the technical decisions into terms a compliance team or executive can act on.

These are working notes on the cryptographic concepts that come up most in enterprise security programs. Written for TPMs - enough to be useful in the room, not a deep implementation guide.

---

## The Two Fundamental Problems Cryptography Solves

Everything in cryptography comes back to two problems:

**Confidentiality:** How do I make sure only the intended recipient can read this message?

**Integrity and authentication:** How do I make sure the message hasn't been tampered with, and that it really came from who it claims to come from?

Encryption addresses confidentiality. Digital signatures and hashing address integrity and authentication. Most real-world systems need to solve both problems simultaneously - which is why modern protocols like TLS combine multiple cryptographic mechanisms.

---

## Symmetric Encryption

**What it is:** Both the sender and the receiver use the same key to encrypt and decrypt data. The key must be kept secret by both parties.

**How it works conceptually:** Imagine a lockbox where both parties have identical keys. The sender locks the box, sends it, and the receiver unlocks it with their copy of the key.

**Common algorithms:** AES (Advanced Encryption Standard) is the current standard. AES-256 (256-bit key length) is widely used and considered secure. 3DES is legacy and should no longer be used.

**Strengths:** Fast. Efficient at encrypting large amounts of data. AES hardware acceleration is built into modern processors.

**Weaknesses:** The key distribution problem. How do you securely share the key with the other party in the first place? If you're already communicating securely, you don't need the encryption. If you aren't, how do you share the key without it being intercepted?

**What this means for TPMs:** When you hear "encryption at rest," it's almost always symmetric encryption. Data on disk, in databases, and in backups is typically encrypted with AES. The key question for a TPM isn't the algorithm (AES-256 is almost certainly correct) but the key management - where are the keys stored, who has access to them, and how does the rotation work?

---

## Asymmetric (Public Key) Encryption

**What it is:** Two mathematically related keys - a public key and a private key. Data encrypted with the public key can only be decrypted with the private key. The public key can be shared freely; the private key must be kept secret.

**How it works conceptually:** Imagine a special padlock where anyone can lock it (using the public key) but only you can unlock it (using the private key). You distribute the padlocks widely; people use them to send you locked messages that only you can open.

**Common algorithms:** RSA is the historical standard. Elliptic Curve Cryptography (ECC) is increasingly preferred - it provides equivalent security with much smaller key sizes, which matters for performance-sensitive applications.

**Strengths:** Solves the key distribution problem. You can freely publish your public key. Anyone can encrypt a message to you that only you can decrypt.

**Weaknesses:** Slow. Much more computationally expensive than symmetric encryption. Not practical for encrypting large amounts of data directly.

**In practice:** Asymmetric encryption is almost never used to encrypt data directly at scale. Instead, it's used to securely exchange a symmetric key (a process called key exchange or key encapsulation). Once both parties have the shared symmetric key, they switch to symmetric encryption for the actual data.

This is exactly what TLS does: asymmetric cryptography is used in the handshake to establish a shared session key, and symmetric encryption (AES) is used to encrypt the actual data transfer.

**What this means for TPMs:** When you hear about "key pairs," "public/private keys," or "certificates," you're in asymmetric cryptography territory. The private key is the thing that must be protected at all costs - losing it or having it stolen compromises the security of everything encrypted or authenticated with that key pair.

---

## Hashing

**What it is:** A one-way function that converts input data of any size into a fixed-size output (the hash or digest). One-way means you can't reverse the process - you can't reconstruct the input from the hash.

**How it works conceptually:** A hash function is like a meat grinder. You put data in, you get a hash out. If you change even one character of the input, the hash changes completely and unpredictably. But you cannot reconstruct the original input from the hash.

**Common algorithms:** SHA-256 and SHA-3 are current standards. MD5 and SHA-1 are broken - collision attacks exist, meaning two different inputs can produce the same hash. Never use MD5 or SHA-1 for security purposes.

**What hashing is used for:**
- **Data integrity:** Store the hash of a file. Later, recompute the hash and compare. If they match, the file has not been tampered with.
- **Password storage:** Never store passwords in plaintext. Store the hash. When a user logs in, hash their input and compare to the stored hash.
- **Digital signatures:** Hash the message first, then sign the hash (signing the full message is too slow).
- **Checksums:** Verify file downloads haven't been corrupted or tampered with.

**What this means for TPMs:** If your organization is storing passwords, the correct answer is salted hashing with a purpose-built password hashing algorithm (bcrypt, Argon2, or PBKDF2). Plain SHA-256 is not appropriate for password storage. If an audit or security review surfaces password storage practices, this is the relevant framing.

---

## Digital Signatures

**What it is:** A cryptographic mechanism that proves a message came from a specific sender and hasn't been modified since it was signed. Uses asymmetric cryptography - the sender signs with their private key, and anyone with the public key can verify the signature.

**How it works conceptually:** The sender hashes the message, then computes a signature over the hash using their private key. The recipient runs the message, the signature and the sender's public key through the matching verification algorithm, which checks that the signature fits this message and this key. If it does, the message is authentic and unmodified. "Encrypting the hash with the private key" is a picture of textbook RSA only; ECDSA, EdDSA, ML-DSA and SLH-DSA do not encrypt or decrypt anything.

**What digital signatures prove:**
- **Authenticity:** This message came from the holder of the private key (authentication)
- **Integrity:** The message hasn't been modified since it was signed
- **Non-repudiation:** The signer cannot plausibly deny having signed, because only they hold the private key

**Common uses:** Software signing (proving a software package is from its publisher), certificate signing (certificates are signed by certificate authorities), code signing (proving code hasn't been tampered with), document signing.

**What this means for TPMs:** Software supply chain security increasingly relies on digital signatures. If your organization is deploying software from vendors or open source, the question of whether packages are signed and verified is a real security control. This is especially relevant in the wake of supply chain attacks.

---

## Certificates and PKI

**What it is:** A digital certificate is a document that binds a public key to an identity (a person, an organization, a server). A certificate authority (CA) is a trusted third party that issues and signs certificates. Public Key Infrastructure (PKI) is the system of CAs, certificates, and processes that manages this.

**Why certificates exist:** Asymmetric encryption solves the key distribution problem, but it creates a new problem. If I give you my public key, how do you know it's really mine and not an attacker's? Certificates solve this by having a trusted third party (the CA) vouch for the binding between the key and the identity.

**Certificate components:**
- The public key
- The identity it belongs to (for TLS certificates, usually a domain name or IP address)
- The validity period (not before / not after dates)
- The digital signature of the issuing CA

**How trust works:** Browsers and operating systems come pre-loaded with a list of trusted root CAs. When a browser connects to a website over HTTPS, the server presents its certificate. The browser verifies the certificate was signed by a trusted CA and that the domain matches. This chain of trust is what makes HTTPS work.

**Certificate lifecycle:** Certificates expire. An expired certificate breaks service - clients will refuse to connect. Certificate lifecycle management is the discipline of tracking certificates, automating renewal, and alerting before expiration.

**What this means for TPMs:** Certificate management is operational work that's easy to neglect. The consequences of neglect are outages - usually at the worst possible time, because certificates tend to expire at off-hours or holidays when nobody is watching. Any program that involves TLS or PKI should include an explicit plan for certificate lifecycle management.

**Public certificate lifetimes are shrinking, so renewal has to be automated.** The CA/Browser Forum, which sets the rules public certificate authorities follow, passed ballot SC-081 in 2025. The maximum validity of a publicly trusted TLS certificate drops from 398 days to 200 days from 15 March 2026, to 100 days from 15 March 2027, and to 47 days from 15 March 2029 (source: the CA/Browser Forum TLS Baseline Requirements, section 6.3.2). At 47 days a certificate renews roughly eight times a year. A calendar reminder and a manual ticket do not survive that cadence, so the program question becomes whether issuance and renewal are automated (for example with the ACME protocol) and whether every certificate is in an inventory that alerts before expiry. Internal certificates from a private CA are not bound by these rules, but they usually follow the same direction.

---

## Key Concepts for Security Program TPMs

### Key Length

Longer keys are harder to break. For symmetric encryption, 256-bit AES is current standard. For RSA, 2048-bit minimum with 4096-bit preferred for long-lived keys. For ECC, 256-bit provides similar security to 3072-bit RSA. If someone is proposing shorter keys than these, ask why.

### Key Rotation

Cryptographic keys should be rotated periodically. If a key is compromised, rotation limits the damage. Common rotation schedules: public TLS certificates at least every 200 days today and every 47 days by 2029 (see Certificates and PKI above), symmetric data encryption keys annually or on demand, password-derived keys on password change. The question for a TPM is whether rotation is automated and whether there's a process for emergency rotation when a key is suspected compromised.

### Key Storage

Keys must be protected. A key stored in a configuration file alongside the data it protects doesn't add security. Hardware Security Modules (HSMs) provide the strongest protection - keys are generated and stored inside tamper-resistant hardware and can't be exported in plaintext. For cloud environments, managed key management services (AWS KMS, GCP Cloud KMS, Azure Key Vault) provide strong software-based alternatives.

### Deprecated Algorithms

Some algorithms are no longer considered secure and shouldn't be used:
- **Encryption:** DES, 3DES, RC4 - replaced by AES
- **Hashing:** MD5, SHA-1 - replaced by SHA-256/SHA-3
- **Key exchange:** Diffie-Hellman with small parameters, RSA key transport - replaced by ECDHE
- **TLS versions:** TLS 1.0, TLS 1.1 - replaced by TLS 1.2/1.3

When a program involves cryptography, one of the first questions to ask is whether any deprecated algorithms are in use. Many legacy systems still use them because they were never updated.

### Perfect Forward Secrecy (PFS)

A property of key exchange protocols where the compromise of long-term keys doesn't compromise past session keys. TLS 1.3 mandates PFS. TLS 1.2 supports it if configured with ephemeral key exchange (ECDHE cipher suites). If someone is recording encrypted traffic today in hopes of decrypting it later when they get the keys, PFS prevents this. Worth understanding when evaluating TLS configurations.

### Post-Quantum Cryptography

A large enough quantum computer would break the public-key algorithms that TLS and PKI rely on today (RSA and elliptic-curve). Symmetric encryption such as AES-256 is much less exposed. Nobody can say when such a machine will exist, but the risk is already live for one reason: **traffic recorded today can be decrypted later.** Forward secrecy does not help here, because the attack is on the key exchange itself.

NIST approved the first three post-quantum standards on 13 August 2024:
- **FIPS 203 (ML-KEM)** - key establishment, derived from CRYSTALS-Kyber
- **FIPS 204 (ML-DSA)** - digital signatures, derived from CRYSTALS-Dilithium
- **FIPS 205 (SLH-DSA)** - hash-based digital signatures, derived from SPHINCS+

In March 2025 NIST also selected HQC as a backup key-establishment algorithm to ML-KEM ([NIST, 11 March 2025](https://www.nist.gov/news-events/news/2025/03/nist-selects-hqc-fifth-algorithm-post-quantum-encryption)).

The dates a program can plan against come from NIST IR 8547, still an initial public draft (November 2024) as of October 2026. It proposes that quantum-vulnerable public-key algorithms such as RSA and elliptic-curve be deprecated after 2030 at the 112-bit security level (RSA-2048, for example) and disallowed entirely after 2035.

**What this means for TPMs:** a post-quantum migration is an inventory program before it is a cryptography program - the same shape as a TLS modernization. The first questions are where public-key cryptography is used, which data must stay confidential for many years, and which vendors and libraries have a post-quantum roadmap. The ability to swap an algorithm without rebuilding the system (crypto agility) is the property to ask for.

---

## Questions to Ask During Technical Reviews

When your program involves cryptographic decisions, these are the questions worth asking:

**On algorithm choices:**
- Are any deprecated algorithms (MD5, SHA-1, DES, RC4, TLS 1.0/1.1) in use? If so, what is the remediation plan?
- Is the key length appropriate for the sensitivity of the data and the expected lifetime of the protection?

**On key management:**
- Where are keys stored? Are they protected appropriately (HSM, key management service)?
- Who has access to the keys?
- What is the key rotation schedule and is rotation automated?
- What is the process for emergency key rotation if a key is suspected compromised?

**On certificates:**
- What is the certificate expiration schedule?
- Is renewal automated? What is the alert threshold before expiration?
- Is there a certificate inventory? Is it current?

**On implementation:**
- Has the cryptographic implementation been reviewed by a security architect or external auditor?
- Is there a process for staying current as algorithms are deprecated and new vulnerabilities are discovered?

---

## Further Reading

- NIST SP 800-175B: Guideline for Using Cryptographic Standards in the Federal Government - the authoritative US government reference
- NIST SP 800-57: Recommendation for Key Management - key generation, distribution, storage, and rotation
- *Serious Cryptography* by Jean-Philippe Aumasson - the best accessible treatment of modern cryptography for practitioners who aren't cryptographers

---

*Working notes. Last updated September 2026.*
