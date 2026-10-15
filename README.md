# Security-planning-Assets-Threats-and-Vulnerabilities-NOTES-
Personal notes created while learning Security planning, Assets, Threats and Vulnerabilities as part of my cybersecurity journey.

## Contents
1. Security planning and risk basics
2. Assets, inventory, and classification
3. Data, information security, and sensitive information
4. Security plans, policies, standards, and procedures
5. Compliance, regulations, and the NIST Cybersecurity Framework
6. Security controls and defense in depth
7. Data governance and access management
8. Data lifecycle
9. Cryptography, encryption, hashing, and PKI
10. Access control and authentication
11. Vulnerabilities, CVE, CVSS, and assessments
12. Penetration testing, attack surface, and hardening
13. Threats and social engineering
14. Malware
15. Web-based attacks
16. Threat modeling, attack trees, and PASTA
17. Key takeaways
18. Glossary

---

## 1. Security Planning and Risk Basics

### Security planning
**Security planning** is the process of deciding how an organization will protect its assets and information from security risks.

A security plan may describe:
- Which assets need protection.
- Which threats and vulnerabilities could affect them.
- Which security controls should be used.
- Who is responsible for security tasks.
- How incidents, backups, recovery, and reviews will be handled.

**Examples**
- Writing a policy for handling customer information.
- Defining how employees report suspected phishing.
- Planning how important systems will be restored after an outage.

### Asset
An **asset** is something valuable to an organization that needs protection.

Examples:
- Customer records and employee records.
- Computers, servers, phones, and network equipment.
- Applications, databases, and cloud services.
- Money, business plans, intellectual property, and the organization's reputation.

### Threat
A **threat** is a circumstance or event that could cause harm to an asset or organization.

Examples:
- A cybercriminal attempting to steal customer data.
- Malware disrupting a computer.
- An employee accidentally sending a confidential file to the wrong person.
- A flood damaging equipment.

#### Intentional threats
Intentional threats involve deliberate actions intended to cause harm or gain unauthorized access.

Examples:
- A criminal sending a phishing email to steal credentials.
- An insider deliberately copying confidential files.
- An attacker attempting to exploit an unpatched server.

#### Unintentional threats
Unintentional threats arise from accidents, mistakes, or other non-malicious actions.

Examples:
- An employee accidentally sharing a private document publicly.
- Someone holding a secure door open for an unauthorized visitor without checking their identity.
- An administrator misconfiguring a database.

**Key takeaway:** Both intentional and unintentional actions can cause serious damage. Security awareness and good controls help reduce both.

### Vulnerability
A **vulnerability** is a weakness in a system, application, network, configuration, or process that a threat could exploit.

Examples:
- Weak or reused passwords.
- Outdated software with a known security flaw.
- A database configured to allow public access unintentionally.
- An application that builds database queries unsafely.

### Risk
**Risk** is the possibility of harm when a threat exploits a vulnerability, considered together with the likelihood and potential impact.

A simple way to think about it is:

**Risk depends on likelihood and impact.**

Example:
- **Asset:** customer database.
- **Threat:** cybercriminal.
- **Vulnerability:** database server has an unpatched flaw.
- **Risk:** the criminal may exploit the flaw and expose customer records.
- **Possible impact:** financial loss, privacy harm, legal consequences, and reputational damage.

Risk is not the same as a threat or vulnerability: a threat is what could cause harm; a vulnerability is a weakness; risk concerns the chance and consequences of harm.

### Risk factors and types of harm
Risk assessments commonly consider:
- **Damage:** systems or equipment are harmed.
- **Disclosure:** information is exposed to people who are not authorized to see it.
- **Loss:** information or access becomes unavailable or is permanently lost.
- **Disruption:** normal business operations are interrupted.
- **Unauthorized change:** information is modified without permission.

**Key takeaway:** Identify assets first, then consider threats and vulnerabilities, estimate likelihood and impact, and choose suitable controls.

---

## 2. Asset Inventory and Classification

### Asset inventory
An **asset inventory** is an organized record of an organization's assets.

It may record:
- Asset name and type.
- Owner or responsible team.
- Location or system where it is stored.
- What information it contains.
- Its importance or classification.
- Who can access it.
- Relevant software versions or maintenance details.

**Why it matters:** An organization cannot reliably protect assets it does not know it has.

### Asset classification
**Asset classification** means grouping assets or information according to sensitivity, importance, and the level of protection they need.

A wallet-versus-shoes analogy: losing either is inconvenient, but losing a wallet may expose money and identity documents, so it can have a greater impact. Organizations similarly prioritize assets based on potential harm.

### Common information classification levels
Exact labels vary by organization. A common four-level example is:

| Level | Meaning | Example |
|---|---|---|
| **Public** | Approved for anyone to see | Published product brochure |
| **Internal only** | Intended for people within the organization | Internal meeting notes |
| **Confidential** | Sensitive; access should be limited to approved people | Employee records or business plans |
| **Restricted** | Highly sensitive; strict access controls are needed | Highly sensitive credentials or critical security information |

These labels are not universal legal definitions. Follow the organization's own classification policy.

**Key takeaway:** The more harm that unauthorized access, change, or loss could cause, the stronger the protection usually needs to be.

---

## 3. Data, Information Security, and Sensitive Information

### Data
**Data** consists of facts or values that can be collected, processed, transmitted, or stored by a computer. Data can include text, numbers, images, audio, and records.

### Three states of data
- **Data in use:** Data being accessed or processed by a person, application, or system. Example: a spreadsheet open for editing.
- **Data in transit:** Data moving between systems or locations. Example: a browser sending information to a website.
- **Data at rest:** Data stored and not currently moving between systems. Example: a file saved on a disk or in cloud storage.

Different states may need different protections. For example, encryption can protect stored data and data sent over a network; access controls help prevent unauthorized people from viewing or changing it.

### Information security (InfoSec)
**Information security** is the practice of protecting information from unauthorized access, use, disclosure, disruption, modification, or destruction.

Three core goals often used to explain security are:
- **Confidentiality:** Only authorized people or systems can access information.
- **Integrity:** Information remains accurate and is changed only in authorized ways.
- **Availability:** Information and systems are accessible when needed.

These are known as the **CIA triad**.

### Sensitive information categories

#### PII — Personally Identifiable Information
Information that identifies a person directly or can identify them when combined with other information.

Examples:
- Full name combined with a home address.
- National identification number.
- Email address or phone number, depending on context.

#### SPII — Sensitive Personally Identifiable Information
A term used in some materials for especially sensitive personal information. Exact definitions vary by context and organization.

Examples may include:
- Government identification details.
- Financial account credentials.
- Other sensitive information that could cause serious harm if misused.

**Important:** A password is sensitive information, but terminology and formal categories differ across frameworks and jurisdictions.

#### PHI — Protected Health Information
In the context of US HIPAA, PHI is individually identifiable health information handled by covered entities and their business associates, subject to HIPAA's rules.

Example: a medical record linked to a named patient.

### Related laws and standards
- **GDPR:** European Union data-protection regulation governing the processing of personal data within its scope.
- **PCI DSS:** Payment Card Industry Data Security Standard for protecting payment-card account data.
- **HIPAA:** US law that includes protections for certain health information handled by covered entities and business associates.

These have different scopes and requirements. Do not assume that every organization or every kind of data is covered by all three.

**Key takeaway:** Identify what information you have, classify it, know which rules apply, and protect it throughout its lifecycle.

---

## 4. Security Plans, Policies, Standards, and Procedures

### Security plan
A **security plan** is a document describing how an organization protects its assets, manages risks, and responds to security needs.

### Common elements

#### Policy
A **policy** is a high-level rule or statement that establishes expectations and requirements.

Example: “Employees must protect confidential customer information.”

#### Standard
A **standard** defines specific, mandatory requirements that support a policy.

Example: “Passwords must meet the organization's approved length and security requirements.”

#### Procedure
A **procedure** gives step-by-step instructions for carrying out a task.

Example: instructions for disabling an employee's access when they leave the organization.

A useful distinction:
- **Policy:** What must or must not happen.
- **Standard:** The specific requirement to follow.
- **Procedure:** How to carry it out.

Organizations may also use **guidelines**, which are recommendations or best practices rather than mandatory requirements.

---

## 5. Compliance, Regulations, and the NIST Cybersecurity Framework

### Compliance
**Compliance** means following applicable requirements, such as laws, regulations, contracts, standards, or internal policies.

### Regulation
A **regulation** is a rule issued by a government or other authorized regulator. Regulations may create legal obligations.

### NIST Cybersecurity Framework (CSF)
The **NIST Cybersecurity Framework** provides outcomes and guidance that organizations can use to understand, assess, prioritize, and manage cybersecurity risk. It is not itself a law, and whether it is required depends on the organization and applicable obligations.

#### The five functions in CSF 1.1
The earlier version commonly taught in introductory materials has five functions:

1. **Identify:** Understand assets, systems, business context, and cybersecurity risks.
2. **Protect:** Put safeguards in place to reduce the likelihood or impact of incidents.
3. **Detect:** Find possible cybersecurity events.
4. **Respond:** Take action when a cybersecurity incident occurs.
5. **Recover:** Restore affected services and improve recovery capabilities.

**Example:** A company inventories its servers (**Identify**), applies access controls (**Protect**), monitors alerts (**Detect**), investigates an alert (**Respond**), and restores affected systems from verified backups (**Recover**).

#### Version note: CSF 2.0
NIST CSF 2.0, released in 2024, adds a sixth function: **Govern**. It focuses on establishing and monitoring the organization's cybersecurity risk-management strategy, expectations, and responsibilities. If your course teaches five functions, it may be using the earlier version; learn the version your course expects and know that CSF 2.0 has six.

### CSF components
- **Core:** The cybersecurity outcomes and activities organized into functions and more detailed categories/subcategories.
- **Tiers:** Describe the rigor of an organization's cybersecurity risk-governance and management practices. They are not simply a score for whether the organization is “secure.”
- **Profiles:** Describe the cybersecurity outcomes that are relevant to an organization and compare current outcomes with desired outcomes.

**Key takeaway:** The CSF helps organizations structure risk management; it does not replace the need to understand their own assets, risks, and legal obligations.

---

## 6. Security Controls and Defense in Depth

### Security control
A **security control** is a safeguard or countermeasure designed to reduce risk.

Examples:
- Multi-factor authentication.
- Encryption.
- Security-awareness training.
- Access reviews.
- Backups.
- Firewalls and monitoring.

Controls may prevent incidents, detect them, or reduce harm and help recovery.

### Common control categories
Introductory materials often group controls into three categories:

- **Technical controls:** Technology-based safeguards, such as encryption, firewalls, access permissions, and anti-malware tools.
- **Operational controls:** Procedures and human activities, such as training, monitoring, incident handling, and backup testing.
- **Managerial controls:** Governance and risk-management activities, such as policies, risk assessments, and security planning.

Other frameworks use different categories, including administrative, physical, preventive, detective, corrective, deterrent, and recovery controls. The classification depends on the framework being used.

### Defense in depth
**Defense in depth** means using multiple layers of security so that one failed control does not automatically expose the organization.

Common layers include:
1. **Perimeter / boundary:** Controls that regulate traffic entering or leaving a network.
2. **Network:** Network segmentation, firewalls, and network monitoring.
3. **Endpoint:** Protection for laptops, desktops, phones, and servers.
4. **Application:** Secure coding, testing, authentication, and patching.
5. **Data:** Access permissions, encryption, backups, and integrity checks.
6. **People and processes:** Training, policies, approvals, and incident-response procedures.

The exact layer model varies. The central idea is to avoid relying on one safeguard.

**Example:** A phishing email may bypass a mail filter, but MFA, endpoint protection, limited user privileges, and monitoring can still reduce the damage.

**Key takeaway:** No single control is perfect. Multiple complementary controls provide stronger protection.

---

## 7. Data Governance and Access Management

### Information privacy
**Information privacy** concerns how personal information is collected, used, shared, retained, and protected in accordance with people's rights and applicable rules. It is related to information security but is not identical to it.

- **Security** focuses on protecting information and systems.
- **Privacy** focuses on appropriate and lawful handling of personal information.

### Principle of least privilege
The **principle of least privilege** means giving each user, application, or process only the minimum access and permissions needed to perform its task.

Example: A staff member who only needs to view customer orders should not automatically be able to delete the entire customer database.

Why it matters:
- Limits the damage from compromised accounts.
- Reduces accidental changes.
- Makes misuse harder.

Strong passwords and MFA are still important: correctly assigned permissions do not help enough if an attacker takes over the account.

### Data owner
A **data owner** is the person or role accountable for a data asset and its appropriate use. They typically make or approve decisions about classification, access, and protection requirements.

### Data custodian
A **data custodian** handles data according to the owner's requirements. This may include storing, backing up, transporting, or maintaining the systems that hold the data.

### Data steward
A **data steward** helps maintain data quality and implement data-governance rules, definitions, and practices.

Roles can overlap depending on the organization, but the general distinction is:
- **Owner:** Accountable for decisions.
- **Custodian:** Handles and protects the data operationally.
- **Steward:** Helps maintain proper governance and quality.

### Auditing account privileges
An **access or privilege audit** checks whether users have appropriate permissions and whether those permissions are still needed.

Common checks include:
1. **Account/usage review:** Check which accounts exist, how they are used, and whether inactive or unexpected accounts need attention.
2. **Privilege review:** Check whether permissions are appropriate for each person's job.
3. **Account-change audit:** Review changes such as account creation, deletion, role changes, and permission changes.

Directory services and identity-management systems may be configured to alert administrators to suspicious activity, such as unexpected privilege changes or repeated failed logins.

### Separation of duties
**Separation of duties** divides sensitive tasks among more than one person so that one person cannot complete or abuse an entire high-risk process alone.

Example: One employee requests a payment, while another approves it.

**Key takeaway:** Give access based on job needs, review it regularly, and separate high-risk responsibilities where appropriate.

---

## 8. The Data Lifecycle

A common five-stage model of the **data lifecycle** is:

1. **Collect:** Gather data for a defined purpose.
2. **Store:** Save it in an appropriate location with access controls.
3. **Use:** Access, process, or share it as permitted.
4. **Archive:** Retain it for long-term reference or legal/business needs.
5. **Destroy:** Securely dispose of it when retention is no longer required.

Different organizations may use a slightly different lifecycle model.

**Examples of protections across the lifecycle**
- Collect only necessary data.
- Encrypt sensitive stored data and protect data in transit.
- Limit access during use.
- Apply retention rules to archived data.
- Securely delete or destroy data and media when appropriate.

**Key takeaway:** Data needs protection from collection through final disposal—not just while it is stored.

---

## 9. Cryptography, Encryption, Hashing, and PKI

### Cryptography
**Cryptography** uses mathematical techniques to protect information, for example by providing confidentiality, integrity checks, authentication, or digital signatures.

### Algorithm
An **algorithm** is a defined set of steps for solving a problem or performing a computation.

### Cipher
A **cipher** is an algorithm used to encrypt and decrypt information.

### Encryption
**Encryption** transforms readable data (**plaintext**) into unreadable-looking data (**ciphertext**) using an algorithm and key. Decryption converts ciphertext back to plaintext using the appropriate key.

### Cryptographic key
A **cryptographic key** is a value used by a cryptographic algorithm. A key is not necessarily a mechanism itself; it is information used by the algorithm.

### Symmetric encryption
**Symmetric encryption** uses the same secret key to encrypt and decrypt data.

- It is generally efficient for large amounts of data.
- The secret key must be shared or made available securely to the parties that need it.
- If an unauthorized person obtains the key, they may be able to decrypt the protected data.

### Asymmetric encryption
**Asymmetric cryptography** uses a mathematically related public-key/private-key pair.

- The **public key** can be shared.
- The **private key** must be protected.
- Depending on the operation, the pair can support encryption/key establishment or digital signatures.
- It is commonly used with symmetric cryptography rather than encrypting all large data directly.

### Symmetric vs. asymmetric encryption

| Feature | Symmetric | Asymmetric |
|---|---|---|
| Keys | One shared secret key | Public/private key pair |
| Typical strength | Efficient for bulk data | Useful for key establishment and signatures |
| Main key challenge | Securely sharing the secret | Protecting the private key and trusting public-key identity |
| Common use | Encrypting files or data streams | Supporting secure key exchange and digital signatures |

### Public Key Infrastructure (PKI)
**Public Key Infrastructure (PKI)** is a system of technologies, policies, and trusted roles used to manage public keys and digital certificates.

PKI commonly involves:
- **Public/private key pairs.**
- **Digital certificates** that bind a public key to an identity.
- **Certificate authorities (CAs)** that issue and sign certificates.
- **Certificate validation** to check trust, validity dates, identity, and revocation status where applicable.

PKI is not simply a two-step exchange of encrypted information. In a typical secure web connection, certificates help a browser authenticate a website, and cryptographic protocols establish keys used to protect the connection.

### Brute-force attack
A **brute-force attack** systematically tries many possible passwords or keys until one works. Strong passwords, rate limiting, MFA, and appropriate cryptographic key sizes can help defend against different forms of brute-force attack.

### Hash function
A **hash function** maps input data of any supported size to a fixed-length output called a **hash** or **digest**.

Important properties of a cryptographic hash function:
- The same input produces the same digest.
- A small change in input should produce a very different digest.
- It is designed to be computationally infeasible to recover the original input from the digest.
- It helps detect changes when the expected digest is obtained through a trustworthy channel.

**Hashing is not encryption:** hashes are not meant to be decrypted.

### SHA (Secure Hash Algorithm) family
- **SHA-1:** Produces a 160-bit digest; no longer considered secure for collision resistance.
- **SHA-224:** Produces a 224-bit digest.
- **SHA-256:** Produces a 256-bit digest and is widely used.
- **SHA-384:** Produces a 384-bit digest.
- **SHA-512:** Produces a 512-bit digest.

A hash alone does not prove who created a file. An attacker who can change both a file and its untrusted hash could replace both. For stronger verification, use a trusted source, a message authentication code (MAC), or a digital signature, as appropriate.

**Password note:** Passwords should generally be stored using a password-hashing scheme designed for passwords, with salts and suitable work factors—not as plain text and not simply as a fast general-purpose hash such as SHA-256.

### Integrity and non-repudiation
- **Integrity:** Confidence that information has not been altered improperly.
- **Digital signature:** A cryptographic mechanism that can help verify the signer and detect changes.
- **Non-repudiation:** Evidence intended to make it difficult for a party to credibly deny an action or signature. Its strength depends on key protection, identity verification, procedures, and the surrounding legal/technical context.

**Key takeaway:** Encryption protects confidentiality; hashing helps detect changes; digital signatures can support integrity and authenticity. These tools serve different purposes.

---

## 10. Access Control and Authentication

### Access controls
**Access controls** determine who or what can access a resource and what actions they are allowed to perform.

### AAA framework
AAA commonly stands for:

1. **Authentication:** Verify who or what is requesting access.
2. **Authorization:** Determine what the authenticated identity is permitted to do.
3. **Accounting:** Record activity for auditing and accountability.

Example:
- A user signs in with MFA (**authentication**).
- The system permits access only to the user's assigned files (**authorization**).
- The system logs important actions (**accounting**).

### Three authentication factor categories
1. **Knowledge — something you know:** Password or PIN.
2. **Possession — something you have:** Security key or authenticator device.
3. **Inherence — something you are:** Fingerprint or facial characteristic.

Using two passwords is not multi-factor authentication because both are knowledge factors. MFA combines two or more different factor categories.

### Single sign-on (SSO)
**Single sign-on (SSO)** allows a user to sign in through one identity system and access multiple connected applications without entering credentials separately into each one.

SSO can improve usability and centralize access management, but the identity account becomes especially important to protect.

### LDAP and SAML
- **LDAP (Lightweight Directory Access Protocol):** A protocol commonly used to access and manage directory information, such as user and group records.
- **SAML (Security Assertion Markup Language):** A standard for exchanging authentication and authorization-related assertions, commonly used in enterprise SSO.

LDAP is not simply “on-premises only,” and SAML is not simply “cloud only”; both can be used in different architectures. They serve different purposes.

### Separation of duties
Sensitive activities should be divided among people or roles when appropriate, reducing the chance that one individual can misuse a process without oversight.

### Basic Authentication (Basic Auth)
Basic Auth is an HTTP authentication method that sends a username and password in a Base64-encoded form in the `Authorization` header.

- Base64 is **encoding**, not encryption.
- Encoded credentials can be decoded.
- HTTPS is necessary to protect credentials while they travel over the network.
- More modern authentication options may be preferable depending on the application.

### OAuth 2.0
**OAuth 2.0** is an authorization framework that lets an application obtain limited access to a user's resources without needing the user's password directly.

A simplified flow:
1. The user grants permission.
2. An authorization server issues an access token.
3. The application presents the token to access permitted resources.
4. The token's scope and other restrictions limit what can be accessed.

- **Access token:** A credential used to access specified resources.
- **Scope:** The permissions requested or granted.
- Tokens should be protected like sensitive credentials.

**Important distinction:** OAuth 2.0 is primarily about authorization. **OpenID Connect (OIDC)** builds on OAuth 2.0 to provide an identity/authentication layer.

### API and API token
- **API:** Application Programming Interface—a defined way for software components to communicate.
- **API token:** A credential used to authorize requests to an API. A token is not necessarily encrypted code; it may be a random or structured value, and its exact format depends on the system.

Protect tokens, restrict their permissions and lifetime where possible, and revoke them if exposed.

### Sessions, session IDs, and cookies
- **Session:** A period or logical relationship during which a system tracks interactions with a user or client.
- **Session ID:** An identifier used to associate requests with a session. If an attacker steals a valid session ID, they may be able to act as the user.
- **Session cookie:** A cookie stored by the browser that can carry a session identifier or related session data. It helps a website maintain state between requests.

### Session hijacking
**Session hijacking** occurs when an attacker takes control of a legitimate session, for example by obtaining a valid session token.

Defenses can include HTTPS, secure cookie settings, protecting devices, preventing cross-site scripting, rotating session IDs at appropriate points, and invalidating sessions after logout or suspected compromise.

**Key takeaway:** Authentication verifies identity, authorization limits actions, and accounting records activity. Tokens and session identifiers must be protected like credentials.

---

## 11. Vulnerabilities, CVE, CVSS, and Vulnerability Assessments

### Exposure
An **exposure** is a condition that can leave an asset or information open to harm. It is related to vulnerability but may also describe an instance of information or a system being unnecessarily exposed.

### CVE — Common Vulnerabilities and Exposures
**CVE** is a public catalog of identifiers for publicly disclosed cybersecurity vulnerabilities. A CVE ID helps different people and tools refer to the same issue.

### CNA — CVE Numbering Authority
A **CVE Numbering Authority (CNA)** is an organization authorized to assign CVE IDs and publish relevant information for vulnerabilities within its scope.

### CVE eligibility and records
CVE records generally identify specific publicly disclosed vulnerabilities. Exact eligibility rules and workflows can evolve, so do not treat an introductory checklist as an exhaustive current rulebook.

A CVE entry typically helps identify the issue and may include descriptions and references. The presence of a CVE ID does not, by itself, tell you how severe the vulnerability is in your specific environment.

### CVSS — Common Vulnerability Scoring System
**CVSS** is a standardized system for describing the severity of a vulnerability using a score and supporting metrics.

A CVSS score is useful for prioritization, but it is not the same as a complete organizational risk assessment. Real-world risk also depends on factors such as whether the affected system is exposed, whether exploitation is occurring, and how important the asset is.

### OWASP Top 10
The **OWASP Top 10** is an awareness document highlighting important categories of web application security risks. It can help guide education and reviews, but it is not a complete list of all vulnerabilities and is not, by itself, a universal regulatory checklist.

### Vulnerability assessment process
1. **Identification:** Discover potential vulnerabilities through scanning, configuration review, and authorized manual testing.
2. **Analysis:** Verify findings, understand their causes, and determine which systems are affected.
3. **Risk assessment:** Prioritize findings by considering severity, likelihood, exposure, asset importance, and possible impact.
4. **Remediation:** Fix or reduce the issue—for example, by applying a patch, changing a configuration, or correcting code.
5. **Verification and follow-up:** Retest where appropriate to confirm the fix and document any remaining risk.

Some course models use four steps and do not list verification as a separate step. The core idea is to identify issues, understand them, prioritize them, and address them.

**Key takeaway:** A vulnerability scanner's output is not automatically a confirmed vulnerability or a complete risk ranking. Validate and prioritize findings.

---

## 12. Penetration Testing, Attack Surface, and Hardening

### Penetration testing
**Penetration testing** is an authorized, scoped assessment in which testers attempt to demonstrate how security weaknesses could be exploited.

It differs from a vulnerability assessment:
- A **vulnerability assessment** focuses on identifying and prioritizing possible weaknesses.
- A **penetration test** attempts controlled exploitation to demonstrate impact within an agreed scope.

Testing must be explicitly authorized and follow the agreed rules of engagement.

### Attack surface
The **attack surface** is the set of points where a system, service, or organization could be exposed to attacks.

Examples:
- Public-facing websites and APIs.
- Open network services.
- User accounts and login pages.
- Third-party integrations.
- Devices and software connected to a network.

### Attack vector
An **attack vector** is a path or method an attacker could use to reach or exploit a target.

Examples:
- A phishing message that steals a password.
- An exposed service with a vulnerable version.
- A web application flaw.
- A compromised third-party component.

The attack surface is the collection of possible exposure points; an attack vector is a particular route through which an attack may occur.

### Security hardening
**Security hardening** is the process of reducing weaknesses and unnecessary exposure by securely configuring and maintaining systems.

Examples:
- Removing unused applications and services.
- Applying security patches.
- Disabling default or unnecessary accounts.
- Enforcing MFA and least privilege.
- Using secure configuration baselines.
- Reviewing firewall rules and logging.

### Thinking like an attacker—defensively
A security professional can assess:
1. What asset needs protection?
2. What entry points are exposed?
3. What weaknesses might affect those entry points?
4. What controls could prevent or detect misuse?
5. How can the findings be safely verified and fixed?

### Defending against attack vectors
- Educate users and provide a clear way to report suspicious activity.
- Apply least privilege and MFA.
- Keep systems patched and securely configured.
- Use appropriate protective and monitoring tools.
- Coordinate security, IT, development, and business teams.
- Test defenses only with authorization.

---

## 13. Threats and Social Engineering

### Social engineering
**Social engineering** is the use of manipulation to persuade people to reveal information, grant access, or perform actions that may compromise security.

It often exploits trust, urgency, fear, curiosity, or helpfulness rather than a technical flaw.

### Common stages of social engineering
A simplified model is:
1. **Prepare:** Gather context and choose an approach.
2. **Establish trust:** Pretend to be a legitimate person or organization.
3. **Use persuasion:** Encourage the target to disclose information or take an action.
4. **Disconnect:** End the interaction after the desired action.

Not every attack follows these stages exactly.

### Preventing social engineering
- Verify unexpected requests through a separate trusted channel.
- Do not share passwords or one-time codes.
- Be cautious with urgent requests, unexpected attachments, and unfamiliar links.
- Follow identity-verification and approval procedures.
- Keep staff training current and make reporting suspicious messages easy.
- Use technical controls such as email filtering and MFA.

### Phishing
**Phishing** is a social-engineering attack in which an attacker impersonates a trusted source to trick someone into revealing information, opening a malicious attachment, visiting a fraudulent site, or taking another unsafe action.

Common forms:
- **Email phishing:** Messages sent by email.
- **Spear phishing:** A targeted message tailored to a specific person or organization.
- **Smishing:** Phishing through SMS or text messages.
- **Vishing:** Phishing through voice calls or voice communication.
- **Whaling:** Targeted phishing aimed at senior executives or other high-value individuals.

### Phishing kit
A **phishing kit** is a collection of tools or templates used to create and operate phishing pages or campaigns. Such kits may include:
- Fake login pages or data-collection forms.
- Templates that imitate trusted organizations.
- Components that capture submitted information.
- Links or scripts used to manage the campaign.

These are examples of attacker methods, not tools to use against real people. Study them for recognition and defense.

### Phishing defenses
- Anti-phishing policies and employee training.
- Email filtering and attachment/link analysis.
- MFA, preferably resistant to phishing where feasible.
- Reporting and incident-response procedures.
- Monitoring and protective controls on endpoints and networks.

### Intrusion Detection System (IDS)
An **IDS** monitors network traffic or system activity for suspicious patterns and generates alerts. It generally detects and alerts; it does not necessarily block activity automatically.

### Intrusion Prevention System (IPS)
An **IPS** monitors activity and can take action to block or prevent detected malicious traffic, depending on its configuration.

**Key takeaway:** People are part of the security environment. Verification, training, and technical safeguards work best together.

---

## 14. Malware

### Malware
**Malware** is software designed to perform harmful or unauthorized actions, such as stealing data, disrupting systems, or gaining unauthorized access.

### Common malware types
1. **Virus:** Malware that attaches to a file or program and spreads when the infected host is run or shared.
2. **Worm:** Malware that can self-propagate between systems, often across networks, without needing to attach to another program.
3. **Trojan horse:** Malware disguised as legitimate or useful software. Unlike a worm, a Trojan does not necessarily self-replicate.
4. **Ransomware:** Malware that typically encrypts or otherwise makes data unavailable and demands payment. Paying does not guarantee recovery.
5. **Spyware:** Software that secretly monitors activity or collects information without appropriate permission.
6. **Cryptojacking:** Unauthorized use of a device's resources to mine cryptocurrency.

These categories can overlap; one piece of malware may have several capabilities.

### Consent and authorization
**Consent** means permission that is freely and appropriately given. In cybersecurity, an action can be technically possible but still unauthorized or harmful. Accessing, monitoring, or collecting another person's data without proper permission can violate rules or laws.

### General malware defenses
- Keep operating systems and applications updated.
- Use reputable endpoint protection and security settings.
- Avoid untrusted downloads and unexpected attachments.
- Use standard user accounts rather than unnecessary administrator privileges.
- Maintain tested backups.
- Report suspicious activity promptly.

---

## 15. Web-Based Attacks

### Web-based exploit
A **web-based exploit** takes advantage of a weakness in a website, web application, browser, or related component.

### Injection attack
An **injection attack** occurs when an application treats untrusted input as part of a command or query instead of handling it strictly as data.

Defenses depend on the injection type but often include safe APIs, input validation, context-aware output handling, least privilege, and secure coding practices.

### Cross-site scripting (XSS)
**Cross-site scripting (XSS)** is a vulnerability that allows untrusted script content to execute in a user's browser in the context of a vulnerable website.

Potential impacts include actions performed as the user, access to information available to the page, or changes to page content. The exact impact depends on the application and browser protections.

#### Common XSS types
1. **Reflected XSS:** Untrusted input is returned by the server in a response and executes in the browser because it is handled unsafely.
2. **Stored XSS:** Untrusted content is saved by the application and later delivered to users in a way that causes script execution.
3. **DOM-based XSS:** Client-side JavaScript handles untrusted data unsafely and changes the page in a way that causes script execution; the key flaw is in client-side DOM processing.

**General defenses**
- Context-aware output encoding.
- Safe handling of untrusted input.
- Avoiding unsafe DOM APIs and patterns.
- Content Security Policy as an additional layer, not a substitute for fixing the flaw.
- Secure development and testing.

### SQL injection (SQLi)
**SQL injection** occurs when untrusted input is incorporated into a SQL query in a way that changes the query's intended structure or behavior.

Possible impacts depend on permissions and application design and can include unauthorized reading or changing of database information.

#### Prepared statements / parameterized queries
**Prepared statements** separate SQL query structure from user-supplied values. The database treats supplied values as data rather than executable SQL syntax.

Other helpful protections:
- Use safe database APIs and parameterized queries.
- Give the application's database account only the permissions it needs.
- Avoid building SQL by concatenating untrusted input.
- Handle errors safely and test code securely.

**Key takeaway:** Validate and handle untrusted input safely, but do not rely on input filtering alone. Use secure APIs and context-appropriate protections.

---

## 16. Threat Modeling, Attack Trees, and PASTA

### Threat modeling
**Threat modeling** is a structured process for identifying assets, understanding how systems work, considering possible threats, and deciding how to reduce risk.

It is useful during system design and when important changes are made.

### A common threat-modeling workflow
1. **Define the scope:** Decide which system, application, data, and boundaries are included.
2. **Identify threats:** Consider who or what could cause harm and what they might try to do.
3. **Characterize the environment:** Understand architecture, data flows, users, trust boundaries, and dependencies.
4. **Analyze threats:** Evaluate relevant attack paths, weaknesses, likelihood, and impact.
5. **Mitigate risk:** Select controls or changes that reduce the most important risks.
6. **Evaluate findings:** Document decisions, remaining risks, and actions; revisit the model as the system changes.

Different frameworks arrange these activities differently.

### Attack tree
An **attack tree** is a diagram that organizes ways an attacker might achieve a particular goal. The top node represents the goal; branches represent possible subgoals or methods.

Example, at a high level:
- **Goal:** Gain unauthorized access to a business account.
  - Possible branch: steal credentials.
  - Possible branch: abuse a misconfigured recovery process.
  - Possible branch: exploit a software weakness.

Attack trees help defenders identify where controls could interrupt a path. They should be developed and used within authorized security work.

### PASTA
**PASTA** stands for **Process for Attack Simulation and Threat Analysis**. It is a risk-centric threat-modeling framework that connects business objectives with technical analysis and possible attack scenarios.

### Seven stages of PASTA
1. **Define business and security objectives:** Understand what the organization needs to protect and its relevant requirements.
2. **Define the technical scope:** Identify systems, applications, interfaces, infrastructure, and boundaries.
3. **Decompose the application:** Map components, data flows, entry points, and trust boundaries.
4. **Perform a threat analysis:** Identify relevant threat actors, motivations, and threat scenarios.
5. **Perform a vulnerability analysis:** Identify weaknesses that could make threats possible.
6. **Conduct attack modeling:** Examine plausible attack paths and how a system could be affected, within an authorized analysis.
7. **Analyze risk and impact:** Estimate business impact and prioritize mitigations.

**Example (high-level):** For a shopping application, business objectives may include protecting customer accounts and payment data. The technical scope may include the website, API, and database. The team maps data flows, considers account takeover and injection risks, checks for weaknesses, models possible attack paths, and prioritizes controls such as MFA, parameterized queries, access restrictions, and monitoring.

**Key takeaway:** Threat modeling connects technical weaknesses to business consequences so teams can prioritize meaningful protections.

---

## 17. Key Takeaways

- **Asset:** What needs protection.
- **Threat:** What could cause harm.
- **Vulnerability:** A weakness that could be exploited.
- **Risk:** The likelihood and potential impact of harm.
- **Security planning:** Decide how assets and risks will be managed.
- **Classification:** Assign protection levels based on sensitivity and impact.
- **CIA triad:** Confidentiality, integrity, and availability.
- **Policy / standard / procedure:** High-level rule / specific requirement / step-by-step instructions.
- **NIST CSF:** A framework for managing cybersecurity risk. CSF 1.1 has five functions; CSF 2.0 adds Govern.
- **Security controls:** Safeguards that reduce risk; defense in depth uses multiple layers.
- **Least privilege:** Give only the access needed.
- **Data lifecycle:** Collect, store, use, archive, and destroy data securely.
- **Encryption:** Protects confidentiality when correctly implemented and keys are protected.
- **Hashing:** Produces a digest that can help detect changes; it is not encryption.
- **Authentication / authorization / accounting:** Verify identity / determine permissions / record activity.
- **CVE / CVSS:** Identify known vulnerabilities / describe vulnerability severity.
- **Attack surface / attack vector:** Possible exposure points / a route or method of attack.
- **Social engineering:** Manipulates people; verification and training help defend against it.
- **Malware:** Software intended to perform harmful or unauthorized actions.
- **XSS / SQL injection:** Web application weaknesses that can arise from unsafe handling of untrusted input.
- **Threat modeling:** Identify possible threats and prioritize mitigations before or during system development.

---

## 18. Glossary

| Term | Short definition |
|---|---|
| **Access control** | Rules and mechanisms that determine who can access a resource and what they can do. |
| **Accounting (AAA)** | Recording activity for auditing and accountability. |
| **Algorithm** | A defined set of steps for a computation or task. |
| **API** | Application Programming Interface; a defined way for software to communicate. |
| **API token** | A credential used to authorize API requests. |
| **Asset** | Something valuable that needs protection. |
| **Asset classification** | Grouping assets or information by sensitivity and protection needs. |
| **Asset inventory** | An organized record of assets. |
| **Asymmetric cryptography** | Cryptography using a related public-key/private-key pair. |
| **Attack surface** | The possible points of exposure to attacks. |
| **Attack tree** | A diagram of ways an attacker might achieve a goal. |
| **Attack vector** | A path or method used to reach or exploit a target. |
| **Authentication** | Verifying an identity or the source of a request. |
| **Authorization** | Deciding what an identity is allowed to do. |
| **Availability** | Ensuring information and systems are accessible when needed. |
| **Basic Auth** | HTTP authentication that sends Base64-encoded username/password credentials. |
| **Brute-force attack** | Repeatedly trying possible passwords or keys. |
| **CIA triad** | Confidentiality, integrity, and availability. |
| **Cipher** | An algorithm used for encryption and decryption. |
| **Compliance** | Following applicable requirements. |
| **Confidentiality** | Preventing unauthorized access or disclosure. |
| **Cryptographic key** | A value used by a cryptographic algorithm. |
| **Cryptography** | Mathematical techniques used to protect information. |
| **CVE** | Common Vulnerabilities and Exposures; identifiers for publicly disclosed vulnerabilities. |
| **CNA** | CVE Numbering Authority; an authorized organization that assigns CVE IDs within its scope. |
| **CVSS** | Common Vulnerability Scoring System; a way to describe vulnerability severity. |
| **Custodian (data)** | A role that handles and protects data operationally. |
| **Data at rest** | Data stored in a location. |
| **Data in transit** | Data moving between systems or locations. |
| **Data in use** | Data being accessed or processed. |
| **Data lifecycle** | Stages data passes through from collection to disposal. |
| **Data owner** | The role accountable for decisions about a data asset. |
| **Data steward** | A role that helps maintain data governance and quality. |
| **Defense in depth** | Using multiple layers of complementary security controls. |
| **Digital certificate** | An electronic document that binds an identity to a public key. |
| **Digital signature** | A cryptographic mechanism that supports integrity and signer authenticity. |
| **Encryption** | Transforming plaintext into ciphertext using an algorithm and key. |
| **Exposure** | A condition that leaves an asset or information open to potential harm. |
| **Hash / digest** | Fixed-length output produced by a hash function. |
| **Hash function** | A function that maps data to a fixed-length digest. |
| **HIPAA** | US law including protections for certain health information. |
| **IDS** | Intrusion Detection System; monitors and alerts on suspicious activity. |
| **InfoSec** | Information security; protecting information against unauthorized access, use, disclosure, disruption, modification, or destruction. |
| **Integrity** | Protecting information from improper alteration. |
| **IPS** | Intrusion Prevention System; can block detected malicious activity. |
| **Least privilege** | Granting only the access required for a task. |
| **LDAP** | Lightweight Directory Access Protocol; used to access directory information. |
| **Malware** | Software designed for harmful or unauthorized activity. |
| **MFA** | Multi-factor authentication; using two or more different authentication-factor categories. |
| **Non-repudiation** | Evidence intended to make denial of an action or signature difficult. |
| **NIST CSF** | NIST Cybersecurity Framework; guidance for managing cybersecurity risk. |
| **OAuth 2.0** | An authorization framework for limited, token-based access. |
| **OIDC** | OpenID Connect; an identity layer built on OAuth 2.0. |
| **OWASP Top 10** | An awareness document about important web application security risks. |
| **PASTA** | Process for Attack Simulation and Threat Analysis; a threat-modeling framework. |
| **Penetration test** | An authorized test that attempts to demonstrate exploitable weaknesses within a defined scope. |
| **PHI** | Protected Health Information, as defined within the applicable HIPAA context. |
| **Phishing** | Deceptive messages intended to trick people into unsafe actions or disclosures. |
| **Phishing kit** | A collection of tools or templates used to operate phishing campaigns. |
| **PII** | Personally Identifiable Information. |
| **PKI** | Public Key Infrastructure; systems and trust processes for managing public keys and certificates. |
| **Policy** | A high-level rule or requirement. |
| **Prepared statement** | A database query structure that keeps supplied values separate from SQL syntax. |
| **Procedure** | Step-by-step instructions for a task. |
| **Public key** | A key that can be shared publicly in an asymmetric cryptographic system. |
| **Private key** | A key that must be protected in an asymmetric cryptographic system. |
| **Ransomware** | Malware that makes data or systems unavailable and demands payment. |
| **Regulation** | A rule issued by an authorized regulator or government body. |
| **Remediation** | Fixing or reducing a security issue. |
| **Risk** | The possibility and potential impact of harm. |
| **SAML** | Security Assertion Markup Language; a standard often used for enterprise SSO. |
| **Security control** | A safeguard designed to reduce risk. |
| **Security hardening** | Reducing weaknesses and unnecessary exposure through secure configuration and maintenance. |
| **Security plan** | A document describing how security risks and protections will be managed. |
| **Session** | A logical period of interaction tracked by a system. |
| **Session cookie** | Browser-stored data that helps a website maintain a session. |
| **Session hijacking** | Taking control of a legitimate user's session. |
| **Session ID** | An identifier associated with a session. |
| **Smishing** | Phishing through SMS or text messages. |
| **Social engineering** | Manipulating people to disclose information or take unsafe actions. |
| **SPII** | Sensitive Personally Identifiable Information; terminology varies by context. |
| **SQL injection** | An attack that changes a SQL query's intended behavior through unsafe input handling. |
| **SSO** | Single sign-on; one sign-in enables access to multiple connected applications. |
| **Standard** | A specific requirement supporting a policy. |
| **Stored XSS** | XSS caused by unsafe handling of stored content. |
| **Symmetric encryption** | Encryption using the same secret key for encryption and decryption. |
| **Threat** | An event or circumstance that could cause harm. |
| **Threat modeling** | A structured process for identifying threats and choosing mitigations. |
| **Trojan horse** | Malware disguised as legitimate software or a file. |
| **Vulnerability** | A weakness that a threat could exploit. |
| **Vulnerability assessment** | Identifying, validating, and prioritizing potential weaknesses. |
| **Virus** | Malware that attaches to a host file or program. |
| **Vishing** | Phishing through voice communication. |
| **Worm** | Malware capable of self-propagating between systems. |
| **XSS** | Cross-site scripting; a flaw that allows untrusted script execution in a user's browser. |

---

## Review checklist

Use this to guide revision; a checked item should mean you can explain it in your own words, not just that you read it.

- [ ] Explain the difference between an asset, threat, vulnerability, and risk.
- [ ] Give examples of intentional and unintentional threats.
- [ ] Explain why asset inventories and classification matter.
- [ ] Distinguish public, internal, confidential, and restricted information.
- [ ] Explain data in use, in transit, and at rest.
- [ ] Explain the CIA triad.
- [ ] Distinguish a policy, standard, and procedure.
- [ ] Name the NIST CSF functions and explain the CSF 1.1 versus CSF 2.0 difference.
- [ ] Explain technical, operational, and managerial controls.
- [ ] Explain least privilege, separation of duties, and access reviews.
- [ ] Describe the data lifecycle.
- [ ] Distinguish encryption, hashing, and digital signatures.
- [ ] Explain symmetric versus asymmetric cryptography and the purpose of PKI.
- [ ] Distinguish authentication, authorization, and accounting.
- [ ] Explain SSO, LDAP, SAML, OAuth 2.0, and OIDC at a high level.
- [ ] Explain sessions, session IDs, cookies, and session hijacking.
- [ ] Explain CVE, CNA, CVSS, and the steps of a vulnerability assessment.
- [ ] Distinguish attack surface, attack vector, vulnerability assessment, and penetration testing.
- [ ] Recognize phishing, smishing, vishing, and common malware types.
- [ ] Explain XSS types and why prepared statements help prevent SQL injection.
- [ ] Describe threat modeling, attack trees, and the seven PASTA stages.
"""

# Use pypandoc as required for Markdown output.
out = "/mnt/data/Polished_Cybersecurity_Study_Notes.md"
pypandoc.convert_text(output, to="markdown", format="md", outputfile=out, extra_args=["--standalone"])
print(f"Created: {out}\nSize: {Path(out).stat().st_size:,} bytes\nSections: 18, plus review checklist and glossary.")
