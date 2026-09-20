# Top 10 Overview
[OWASP top 10 2025](https://owasp.org/Top10/2025/)
##  A01:2025 - Broken Access Control
### Description
* ***Core Purpose:*** Access control ensures users only perform actions within their authorized permissions to prevent unauthorized data access, modification, or destruction
* ***Privilege & Identify Failures:*** System flaws allow users to gain elevated access, act without logging in, or violate the "deny by default" principle of least privilege
* ***URL & Parameter Manipulation:*** Attackers can bypass checks, force browse to restricted pages, or access other users' accounts by altering parameters, URLs, cookies, or unique identifiers (IDOR)
* ***API & Token Vulnerabilities:*** Insecure APIs missing HTTP method controls, improper CORS settings, and tampered access tokens (like JWTs) allow untrusted origins or unauthorized users to perform restricted actions
* ***Impacts:*** Uncontrolled access Failures expose sensitive application data, compromise system functionality, and allow execution of restricted business processes

### How to prevent
Access control is only effective when implemented in trusted server-side code or serverless APIs, where the attacker cannot modify the access control check or metadata.
* Except for public resources, deny by default.
* Implement access control mechanisms once and reuse them throughout the application, including minimizing Cross-Origin Resource Sharing (CORS) usage.
* Model access controls should enforce record ownership rather than allowing users to create, read, update, or delete any record.
* Unique application business limit requirements should be enforced by domain models.
* Disable web server directory listing and ensure file metadata (e.g., .git) and backup files are not present within web roots.
* Log access control failures, alert admins when appropriate (e.g., repeated failures).
* Implement rate limits on API and controller access to minimize the harm from automated attack tooling.
* Stateful session identifiers should be invalidated on the server after logout. Stateless JWT tokens should be short-lived to minimize the window of opportunity for an attacker. For longer-lived JWTs, consider using refresh tokens and following OAuth standards to revoke access.
* Use well-established toolkits or patterns that provide simple, declarative access controls.
Developers and QA staff should include functional access control in their unit and integration tests.

### Example attack scenarios
1. The application uses unverified data in SQL call that is accessing account information:
   ```
   pstmt.setString(1, request.getParameter("acct"));
   ResultSet results = pstmt.executeQuery( );
   ```
   * An attacker can simply modify the browser's 'acct' parameter to send any desired account number
   * If not correctly verified,  the attacker can access any user's account
2. An attacker simply forces the browsers target URLs. Admin rights are required for access to the admin page
```
https://example.com/app/getappInfo
https://example.com/app/admin_getappInfo
```
  * If an unauthorized users can access either page, it's a flaw
  * If a non-admin can access the admin page, this is a flaw
3. An application puts all of their controls in their front-end. While the attacker cannot get to ```https://example.com/app/admin_getappInfo``` due to JavaScript code running in the browser, they can simply execute:
```$ curl https://example.com/app/admin_getappInfo```
    * Can be executed from the command line 

## A02:2025 - Security Misconfiguration
### Desccription
* ***Insecure Defaults & Features:*** Default accounts/passwords remain unchanged, and unnecessary ports, services, pages, or privileges are left enabled
* ***Lack of System Hardening:*** Security settings accross servers, frameworks, and cloud permissions are not properly configured or updated to secure values
* ***Excessive Information Exposure:*** Improper error handling exposes detailed stack traces and system information to end users
* ***Legacy & Compatibility Risks:*** Security features are disabled during upgrades, or backward compatibility is prioritized ove safe configuration
* ***Missing Security Controls:*** Critical security headers/directives are absent, and a repeatable configuration Hardening process is lacking

### How to prevent
Secure installation processes should be implemented, including:
* A repeatable hardening process enabling the fast and easy deployment of another environment that is appropriately locked down. Development, QA, and production environments should all be configured identically, with different credentials used in each environment.
* This process should be automated to minimize the effort required to set up a new secure environment.
* A minimal platform without any unnecessary features, components, documentation, or samples. Remove or do not install unused features and frameworks.
* A task to review and update the configurations appropriate to all security notes, updates, and patches as part of the patch management process (see A03 Software Supply Chain Failures). Review cloud storage permissions (e.g., S3 bucket permissions).
* A segmented application architecture provides effective and secure separation between components or tenants, with segmentation, containerization, or cloud security groups (ACLs).
* Sending security directives to clients, e.g., Security Headers.
* An automated process to verify the effectiveness of the configurations and settings in all environments.
* Proactively add a central configuration to intercept excessive error messages as a backup.
* If these verifications are not automated, they should be manually verified annually at a minimum.
* Use identity federation, short-lived credentials, or role-based access mechanisms provided by the underlying platform instead of embedding static keys or secrets in code, configuration files, or pipelines

### Example attack scenarios
###### Scenario #1:
* The application server comes with sample applications not removed from the production server
* These sample applications have known security flaws that attackers use to compromise the server
* Suppose one of these applications is the admin console, and default accounts weren't changed
  * The attacker logs in with the default password and takes over
###### Scenario #2:
* Directory listing is not disabled on the server
* An attacker discovers they can simply list directories
* The attacker finds and downloads the compiled Java classes, which they decompile and reverse engineer to view the code
* The attacker then finds a severe access control flaw in the application
###### Scenario #3:
* The application serves' configuration allows detailed error messages, such as stack traces to return to users
* This potentially exposes sensitive information or underlying flaws
###### Scenario #4:
* A cloud service provider (CSP) Defaults to having sharing permissions open to the internet
* This allows sensitive data stored within cloud storage to be accessed

## A03:2025 - Software Supply Chain Failures
### Description
* ***Definition:*** Occur when third-party code, dependencies, or build tools introduces security vulnerabilities or malicious code into your system
* ***Unmonitored Dependencies:*** You are at risk if you fail to track, audit =, or regularly scan every direct and nested component, library, and framework across your tech stack
* ***Weak Access & Controls:*** Risk increases significantly when systems lack least-privilege access, separation of duties, or mandatory multi-person oversight for code promotion
*  ***Outdated Components & Slow Patching:*** Relying on unpatched, out-of-date, or unsupported components - or delaying fixes due to slow change - control schedules - leaves system paths
*  ***Pipeline & Configuration Flaws:*** Insecure configurations, using untrusted sources, or running a CI/CD pipeline with weaker security then the production environment creates Easy exploitation paths

### How to prevent
* There should be a patch management in place to:
  * ***Maintain a Complete Inventory:*** Continuously generate and track a Software Bill of Materials (SBOM) that covers both direct and nested (transitive) dependencies for all client-and-server-side components
  * ***Automate Vulnerability Monitoring:*** Use automated tools to scan dependencies continuously and monitor databases like CVE, NVD, and [OSV](https://osv.dev/) for real-time security alerts
  * ***Reduce Attack Surface & Sourced Risks:*** Pull packages exclusively from trusted, signed sources over secure links, and strip out unused dependencies, unnecessary features, or unneeded files
  * ***Manage Updates & Dependencies Intentionally:*** Choose dependency versions deliberately, updated developer tooling regularly, and plan migrations or virtual patches for unmaintained, unpatchable components
  * ***Minimize Deployment Blast Radius:*** Deploy software updates using staged or canary rollouts rather than updating all systems at once to limit impact if a vendor is compromised
* There should be a change management process or tracking system in place to track changes to:
  * CI/CD settings (all build tools and pipelines)
  * Code repositories
  * Sandbox areas
  * Developer IDEs
  * SBOM tooling, and created artifacts
  * Logging systems and logs
  * Third-party integrations, such as SaaS
  * Artifact repositories
  * Container registries
* Harden the following systems, which includes enabling MFA and locking down IAM:
  * Your code repository (which includes not checking in secrets. protecting branches, backups)
  * Developer workstations ( regular patching, MFA, Monitoring, and more)
  * Your build server & CI/CD (separation of duties, access control, signed builds, environment-scoped secrets, tampered-evident logs, more)
  * Your artifacts (ensure integrity via provenance, signing, and time stamping, promote artifacts rather then rebuilding for each environment, ensure builds are immutable)
  * Infrastructure as codes (managed like all code, including use of PRs and version control)
* Every organization must ensure an ongoing plan for monitoring, triaging, and applying updates or configuration changes for the lifetime of the application or portfolio
### Example attack scenarios
###### Secnario #1:
* A trusted vendor is compromised with malware, leading to your computer systems being compromised when you upgrade
  * The most famous example of this is probably:
    * [The 2019 SolarWinds compromise that led to ~ 18,000 organizations being compromised](https://www.npr.org/2021/04/16/985439655/a-worst-nightmare-cyberattack-the-untold-story-of-the-solarwinds-hack)
###### Scenario #2: 
* A trusted vendor is compromised such that it behaves maliciously only under a specific confidition
  * The 2025 Bybit theft of $1.5 billion was created by [a supply chain in wallet software](https://www.sygnia.co/blog/sygnia-investigation-bybit-hack/) that only executed when the target wallet was being used
###### Scenario #3:
* The [```Shai-Hulud``` supply chain attack](https://www.cisa.gov/news-events/alerts/2025/09/23/widespread-supply-chain-compromise-impacting-npm-ecosystem) in 20025 was the first successful self-prpagating npm worm
* Attacks seeded malicious versions of poular packages, which used a post-install script to harvest and exfiltrate sensitive data to public Github repositories
* The malware would detect Nmap tokens in the victim environment, and automatically use them to push malicious versions of any accessible package
* The worm reached over 500 package versions before being distributed by npm
* This supply chain attack was advanced, fast-spreading, and damaging, and targeting developer machines it demonstrated developer themselves are now prime targets for supply chain attacks
###### Scenario #4:
* Components typically run with the  same privileges as the application itself
  * This means that flaws in any component can result in serious inpact
* Such flaws can be accidental (e.g., coding error) or intentional (e.g., a backdoor in a component)
* Some example exploitable component vulnerabilities discovered are:
  * CVE 2017-5638 ~ a Struts 2 remote code execution vulnerability that enables the execution of arbitrary code on the server
    * Has been blamed for significant breaches
  * CVE 2021-44228 ("Log4Shell) ~ an Apache Log4j remote code execution zero-day vulnerability
    * Has been blamed for ransomware, cryptomining, and other attack campaigns

## A04:2025 - Cryptographic Failure
* [LLM01:2025 Prompt Injection](https://genai.owasp.org/llmrisk/llm01-prompt-injection/) is an [OWASP LLM Top 10](https://genai.owasp.org/llm-top-10/) 
### Description
* ***Universal Transport Encryption:*** All data in transit should be encrypted at [OSI Layer 4](https://en.wikipedia.org/wiki/Transport_layer), made easier today by hardware-accelerated CPUs and automated certificate management like [LetsEncrypt](https://letsencrypt.org/)
   * ***Sensitive Data Protection:*** High value data -such as password, health records, credit cards, and trade secrets- requires additional encryption at rest and the [application layer](https://en.wikipedia.org/wiki/Application_layer) (OSI Layer 7), especially to meet compliance standards like GDPR (General Data Protection Regulation) or PCI DSS (PCI Data Security Standard)
* ***Key Management & Storage:*** Organizations must avoid weak, default, or reused keys, enforce regular key rotation, and strictly prevent committing cryptographic keys into source code repositories
* ***Modern Cryptography & Protocols:*** Legaby algorithms, deprecated hashes (e.g., MD5, SHA1), insecure operational modes (e.g., ECB),  and weak pr predictable pseudo-random number generators must be replaced with strong, modern cryptographic standards
* ***Implementation Integrity:*** Systems must enforce strict HTTPS headers, properly validate certificate trust chains, generate secure initialization vectors, use password-based key deviation functions, and prevent side-channel leaks or protocol downgrade attacks
### How to prevent
* ***Data Classification & Retention:*** Identify sensitive data according to legal and business standards, enforce specific controls per class, and discard or tokenize data immediately so unneeded data cannot be stolen
* ***Encryption at Rest & Key Management:*** Securrly encrypt sensitive data using modern, authenticated cryptographic algorithms, and protect your highest-level keys using standard key deviation, proper random IVs, and cloud or hardware HSMs
* ***Encryption in Transit & Secure Protocols:*** Mandate Protocols like TLS 1.2+ with forward secrecy, enforce HSTS, disable response caching for sensitive data, and completely block unencrypted transit mechanisms like FTP or plain SMTP
* ***Password Security & Randomness:*** Hash passwords using adaptive, sated functions (e.g., Argon2, sccrypt, or PBKDF2), use CSPTINGs for high-entropy randomness, and store keys safely memory as Byte arrays
* ***Future-Proofing & Quality Assurance:*** Regularly review configurations with security experts or automated tools, retire deprecated algotithms (such as MD4, SHA1, and CBC mode), and prepare systems for post-quantum cryptography standards
### Example attack scenarios
###### Scenario #1: 
* A site doesn't use or enforce TLS for all pages or support encryption
* An attacker
  * Monitors network traffic downgrades connections from HTTPS to HTTP
  *  Intercepts requests
  *  Steals the user's session cookie
* The attacker then
  * Replays this cookie and hijack's the user's (authenticated session
  * Accessing or modifying the user's private key
* Instead, they can alter all transported data
  * *Example:* the recipient of a money transfer
###### Scenario #2:
* The password database uses unsalted or simple hashes to store everyone's passwords
* A  file upload flaw allows an attacker to retrieve the password database
* All the unsalted hashes can be exposed with a rainbow table of pre-calculated hashes
  * Hashes generated by simple or fast hash functions may be cracked by GPUs, even if they were salted

## A05:2025 - Injection
### Description
* ***Definition:*** Occurs when an application sends untrusted user input directly to an interpreter, tricking it into executing malicious commands
* ***Unsanitized Inputs:*** Applications are exposed whenever user-suppliedd data is directly used or concatenated without proper validation, filtering, or context-aware escaping
* ***Flawed Query Patterns:*** Vulnerabilities happen when developers rely on dynamic queries, non-parameterized calls, or unvalidated parameters in ORMs (Object Relatable Mapping), databases, or shell commands
* ***Common Types:*** Injection techniques exist across many interpreters, with SQL, No SQL, OS command, LDAP, ORM, and Expression Language (EL) Injections being the most frequent
* ***Detections & Testing:*** Identifying flaws requires source code reviews, input fuzzing, and interigating automated testing tools (SAST, DAST, IAST) directly into the CI/CD pipeline
### How to prevent
* Requires keeping data separated from commands and queries:
  * Preferred to use a safe API
    1. Avoids using the interpreter entirely
    2. Provides a parameterized interface
    3. Migrates to ORMMs
  * ***Note:*** Even when parameterized, stored procedures can still introduce SQL Injection if PL/SQL or T-SQL concatenates queries and data or executes hostile data with EXECUTE IMMEDIATE or exec()
* When it is not possible to separate the date from commands, you can reduce threats using the following techniques
  * Use positive server-side input validation
    1. Not a complete defense as many applications require special characters, suhc as text areas or APIs for mobile applications
    2. For any residual; dynamic queries, escape special characters using the specific escape syntax for that interpreter
   * ***Note:*** SQL structures such  as table names, column names, and so on cannot be escaped, and thus user-structure names are dangerous
     1. This is a common issue in report-writing software
### Example attack scenarios
### Scenario #1:
* An application uses untrusted data in the construction of the following vulnerable SQL call:
  ```
  String query  = "SELECT * FROM accounts WHERE custID='" + request.getParameter("I'd") + "'";
  ```
* An attacker modifies the 'id' parameter value in their browser to send: ``' OR '1'='1``. For example:
```
http://example.com/app/accountView?I'd='OR '1'='1
```
* This changes the meaning of the query to return all records from the account table. More dangerous attacks could modify or delete data or even invoke stored procedures
### Scenario #2:
* An application's blind trust in frameworks may result in queries that are still vulnerable. For example, Hibernate Query Language (HQL):
```
Query HQLQuery = session.createQuery("FROM accounts WHERE custID='" + request.getParameter("id") + "'");
```
*  An attacker supplies: ``'OR custID IS NOT NULL OR custID='``
  * This bypasses the filter and returns all accounts
  * While HQL has fewer dangerous functions than raw SQL, it still allows unauthorized data access when user input is concatenated into queries
### Scenario #3:
* An application passes user input directly to an OS command:
```
String cmd = "nslookup " + request.getParameter("domain");
Runtime.getRunTime().exec(cmd);
```
* An attacker supplies ``example.com; cat  /etc/passwd`` to execute arcitrary commands on the server

## A06:2025 - Insecure Design
### Description
* ***Definition:*** Refers to missing, inadequate, or ineffective security controls planned into the system architecture
* ***Designed vs. Implementation:*** Design flaws happen in the blueprint stage, while implementation defects occur when writing code -a secure design can still contain coding bugs
* ***Flawed Foundations:*** A perfect, bug-free implementation cannot fix an insecure design, because the necessary defenses were never built into the plan
* ***Not the Root Cause:*** Insecure design is a distinct category of risk and is not the underlying source of every other security vulnerability
* ***Risk Profiling Required:*** Skipping business risk Profiling during development leads to insecure design, as teams fail to identify the specific security controls required
* Three key parts of having a secure design are:
  * ###### Gathering Requirements and Resource Management
    * ***Gather & Negotiate:*** Define business and technical security needs early, fracturing in data protection (CIS/authenticity), tenant isolation, and expected exposure
    * ***Cover All Bases:*** Document both functional and non-functional security requirements alongside standard feature specifications
    * ***Budget Entirely:*** Plan and negotiate funding for security activities across all stages: design, build, testing, and ongoing operations
  * ###### Creating a Secure Design
    * ***Integrate Threat Modeling:*** Continuously evaluate threats, changes in data flows, and access controls during regular refinement sessions
    * ***Define Failure Status:*** Map out expected flows and error handling in user stories, documenting validated assumptions and conditions
    * ***Build Culture Over Tools:*** Treat secure design as an ongoing mindset and methodology rather than a tool or an add-on, using incentives and lessons learned to improve
  * ###### Having a secure Development Lifecycle
    * ***Establish Core Practices:*** Adopt a structured development life-cycle using Threat Modeling, paved-road patterns, secure component libraries, and post-mortems
    * ***Engage Security Early:*** Involve security experts from the start of a project, during build phases, and throughout ongoing maintenance
    * ***Empower Developers:*** Cultivate developer self-responsibility and security awareness through regular discussions so security informs every design decision
### How to prevent 
* ***Secure Lifecycle & Experts:*** Build secure development lifecycle guided by AppSec professionals to evaluate, design, and enforce security and privacy controls
* ***Pre-Built Security Assets:*** Standardized development using a library of secure design patterns and "paved-road" components
* ***Threat Modeling & Mindset:*** Apply Threat Modeling to critical application flows (like author  and business logic) and use it to build a team-wide security scenarios
* ***Architecture & Segregation:*** Implement multi-tier validation checks, separation system/network layers by exposure, and isolate tenants robustly across all tiers
### Example attack scenarios
* ###### Scenario #1:
  * A credential recovery workflow might include "questions and answers"
    * Is prohibited by NIST 800-63b, the OWASP ASVS, and the OWASP Top 10
  *  Questions and answers cannot be trusted as evidence of identity, as more than one person can know the answers
  *  Such functionality should be removed and replaced with a more secure design
* ###### Scenarion #2:
  * A cinema chain allows group booking discounts and has maximum of 15 attendees before requiring a deposit
  * Attackers could treat model this flow and test if they can find an attack vector in the business logic of applications causing a massive loss of income
    1. *Example:* Booking 600 seats and all cinemas at once in a few requests
* ###### Scenario #3:
  * A retail chain's e-commerce website does not have protection against bots run by scrapers buying high-end video cards to resell on auction websites
    * This creates terrible publicity for the video card makers and retail chain owners, and enduring bad blood with enthusiasts who cannot obtain these cards at any price
   * Careful anti-bot design and domain logic rules might identify inauthentic purchases and reject such transactions
   * *Example:* purchases made within a few seconds of availability

## A07:2025 - Authentication Failures
### Description
* ***Definition:*** Authentication weaknesses allow attackers to trick a system into recognizing an invalid or unauthorized user as legitimate
* ***Weak Passwords & Storage:*** Risk arises when systems allow weak/default passwords, permit already-breached credentials, or store password data insecurely (like plain text or weak hashes)
* ***Automated & Brute-Force Attacks:*** Systems are vulnerable if they fail to block credentials stuffing, password spraying, or rapid brute-force login attempts
* ***MFA Flaws & Poor Recovery:*** Failing to enforce storing multi-factor authentication, allowing weak fallbacks, or Relying on insecure password recovery exposes accounts
* ***Insecure Sessions Management:*** Leaking session IDs in URLs, reusing IDs post-login, or failing to properly invalidate token/sessions upon logout leaves user access exposed
### How to prevent
* ***Enforce MFA & Password Managers:*** Require multi-factor authentication to stop credential attacks and encourage password managers so users can generate strong, unique passwords
* ***Block Weak & Breached Credentials:*** Disable default passwords, check new passwords against [common lists](https://haveibeenpwned.com/), and validate them against known breach
* ***Follow NIST Guidelines & Stop Forced Resets:*** Align length and complex policies with [NIST (800-63b's guidelines in section 5.1.1)](https://pages.nist.gov/800-63-3/sp800-63b.html#:~:text=5.1.1%20Memorized%20Secrets) standards, and never force periodic password rotation unless a breach is suspected
* ***Harden Authentication Endpoints:*** Prevent account enumeration with generic error messages ("Invalid username or password"), rate-limit failed logins, and log potential attacks
* ***Use Secure Session Management:*** Rely on established identity providers or secure, built-in session managers that issue high-entropy session IDs stored safely in cookies
### Example attack scenarios
###### Scenario #1:
* Credential stuffing, the use of lists of known username and password combinations, is now a very common attack
* More recently attackers have been found to 'increment' or otherwise adjust passwords, based on common human behavior
  * Making slight changes to a password
* Adjusting of password attempts is called a hybrid credential stuffing attack or password spray attack
  * Can be even more effective than the traditional version
* If an application can be used as a password oracle to determine if the credentials are valid and gain unauthorized access
###### Scenario #2:
* Most successful authentication attacks occur due to the continued use of passwords as the sole authentication factor
* Once considered best practices, password rotation and complexity requirements encourage users to both reuse passwords and use weak passwords
* Organizations are recommended to stop these practices per NSIT 800-63 and enforce use of multi-factor authentication on all important systems
###### Scenario #3:
* Applications session timeouts aren't implemented correctly
  * A user uses a public computer to access an application and instead of selecting "logout". the user simply closes the browser tab and walks away
  * If a [Single Sign on (SSO)](https://www.cloudflare.com/learning/access-management/what-is-sso/) session can not be closed by a [Single Logout (SLO)](https://fusionauth.io/blog/single-sign-on-vs-single-log-out)
    1. A single login logs you into your, for example, your mail reader, your document system, and your chat system
    2. Logging out happens only to the current system
* If an attacker uses the same browser after the victim thinks they have successfully logged out, but with the user still authenticated to some of the applications, then can access the vitim's account
  * Same issue can happen in offices and enterprises when a sensitive application has not been properly exited and a colleague has (temporary) access to the unlocked computer

## A08:2025 - Software or Data Integrity Failures
### Description
* ***Core Definition:*** These failures happen when software or infrastructure trusts invalid, unverified, or malicious code and data
* ***Untrusted Sources:*** Using unverified plugins, libraries, modules, or CDNs allows malicious code to enter your application
* ***Insecure CI/CD Pipelines:*** Pulling  code or artifacts without verifying their digital signatures or source integrity exposes pipelines to unauthorized access and compromise
* ***Unverified Auto-Updates:*** Distributing automatic application updates without strict integrity checks lets attackers deploy malicious patches directly to users
* ***Insecure Deserialization:*** Exposing encoded or serialized objects allow attackers to tamper with data structure and manipulate app execution
### How to prevent 
* ***Verify source integrity:*** Use digital signatures to confirm code and data originate from trusted sources and haven't been tampered with
* ***Control dependencies:*** Pull libraries only from vetted, trusted repositories, or host an internal trusted mirror if risk is high
* ***Require change reviews:*** Implement through peer reviews for all code and configuration update to block malicious code
* ***Secure the CI/CD pipeline:*** Restrict access, enforce strict controls, and maintain proper segregation across build and deployment systems
* ***Validate incoming data:*** Protect serialized data from untrusted clients by enforcing encryption, signatures, or integrity checks before processing
### Examples
###### Scenario #1: *Inclusion of Web Functionality from an Untrusted Source*
* A company uses an external service to provide support functionality
  * It has a DNS mapping for ``myCompany.SupportProvider.com`` to ``support.myCompany.com``
  * All cookies, including authentication cookies, set on the ``myCompany.com`` domain will now be sent to the support provider
* Anyone with access to the support provider's infestructure can steal the cookies of all your users that have visited ``support.myCompanny.com`` and perform a session hijacking attack
###### Scenario #2: *Update without signing*
* Many home routers, set-top boxes, device firmware, and others do not verify updates via signed firmware
* Unsigned firmware is a growing target for attackers and is expected to get worse
  * Major concern because many times there is no mechanism to remediate other than to fix in a future version and wait for previous versions to age out
###### Scenario #3: *Use of Package from an Untrusted Source*
* A developer has trouble finding the updated version of a package they are looking for, so they download it not from the regular, trusted package manager, but from a website online
* The package is not signed
  * There is no opportunity to ensure integrity
* Package includes malicious code
###### Scenario #4: *Insecure Deserialization*
* A React application calls a set of Spring Boot microservices
* Being functional programmers, they tried to ensure that their code is immutable
* The solution they came up with is serializing the user state and passing it back and fourth with each request
* An attacker notices the "rO0" Java object signature (in base64) and use the [Java Deserialization Scanner](https://github.com/federicodotta/Java-Deserialization-Scanner) to gain code execution on the application server

## A09:2025 - Security Logging and Alerting Failures
### Description
* ***Inadequate Log Capture & Integrity:*** Critical actions (like failed logins or errors) aren't logged consistently, logs aren't secured against tampering, and local-only logs lack proper backups
* ***Lack of Continuous Monitoring:*** System, application, and API logs aren't proactively monitored for suspicious behavior or dynamic security scan activities
* ***Ineffective Alerting & Response:*** Alert thresholds, playbooks, or escalation paths are missing, outdated, or delayed, preventing real-time response to active attacks
* ***Alert Fatigue & SOC Overload:*** High volumes of false positives hide critical warnings, leading to missed or delayed incident detection
* ***Data Exposure & Logging Vulnerabilities:*** Unencoded log data exposes systems to injection attacks, while logging sensitive information (like PII/PHI) or exposing log views risks data leaks
### How to prevent
* ***Log comprehensive & context-rich security data:*** Record both successful and failed access attempts, security control checks, and validation failures in a standard format, keeping context long enough for forensic analysis while encoding data to prevent log injection attacks
* ***Protect log and transaction integrity:*** Maintain tamper-proof audit trails for all transactions, and ensure system errors automatically trigger rollbacks that "fail closed"
* ***Set up intelligent alerting & traps:*** Deploy automated alerts for suspicious behaviors and place hidden decoy assets ("honeytokens") in databases or user accounts to catch malicious activity with virtually no false positives
* ***Standardize monitoring & SOC playbooks:*** Define clear detection rules, playbooks, and developer guidance so DevSecOps and SOC teams can respond swiftly to threats - optionally using AI/behavioral analysis for accuracy
* ***Adopt response plans & leverage specialized security tools:*** Implement an established incident response framework (like NIST SP 800-61), train developers to recognize attacks, and utilize logging/protection software
### Example attack scenarios
###### Scenario #1:
* A children's health plan provides website operator couldn't detect a breach due to a lack of monitoring and logging
  * An external party informed the health records of more than 3.5 million children
* A post-incident review found that the website developers had not addressed significant vulnerabilities
  * There was no logging or monitoring of the system, the data breach could have been in progress since 2013, a period of more than 7 years
###### Scenario #2:
* A major indian airline had a data breach involving more than 10 years' worth of personal data of millions of passengers
* The data breach occurred at a third-party cloud hosting provider, who notified the airline of the breach after some time
###### Scenario #3:
* A major European airline suffered a GDPR reportable breach
* The breach was reportedly caused by payment application security vulnerabilities exploited by attackers, who harvested more than 400,000 customer payment records
* The airline was fined 20 million pounds as a result by the  privacy regulator

## A10:2025 - Mishandling of Exceptional Conditions 
