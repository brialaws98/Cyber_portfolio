# Fundamentals
## Introduction
* Legally mimic cyberattacks to spot security holes in a company's digital worlds
* Use real attack methods to test a system's defense
* Involves planning, doing  the test, and reporting back to manage risks smartly
* These tests can involve:
  * Scanning networks
  * Exploiting known issues
  * Seeing how far into a system an attacker could go
### Definition
* ***Penetration test:*** A unique type of security assessment that goes beyond automated scoring and vulnerability identification
  * Involves attempting to exploit discovered vulnerabilities and gain unauthorized access, elevate privileges, or extract sensitive data
  * Allows organizations to understand what vulnerabilities exist in their infrastructure, how they could be leveraged and hardened in a real attack scenarios, and what the impact would be
* Conducted by skilled security professionals
  * Have a deep understanding of systems, networks, and offensive and defensive techniques
* These tests are carried out with the organization's full knowledge and permission, following strict rules of engagement and a defined scope
* Encompasses a wide range of tasks, including:
  1. ***Reconnaissance:***
     * Gather information about the target organization, system or network (Scouting out a building before planning a break-in)
  2. ***Vulnerability Assessment:***
     * Use tools to spot weak points (Checking for unlocked windows or doors)
  3. ***Exploitation:***
     * Try to exploit those weaknesses to gain access or control over the system (theif might test those unlocked door)
  4. ***Post-exploitation:***
     * Explore what else can be accessed, maintain control, and assess the impact of a sucessful attack (Seeing how far an intruder could roam inside a building)
  5. ***Reporting:***
     * Documents everything: Vulnerabilities found, the risks they pose, and clear steps to fix them, so the system can be secured
*Companies use pentests to find and fix holes before the bed unethical hackers do
       
### Goals of Penetration Testing
* Primary goals can be broken down into three categorie:
  * Evaluation of organization's cyber security posture
  * Testing organization's defensive measures
  * Operational & Financial impact risk assessment
* In detail these categories consist of, but are not limited to:
  * ***Identify Security Weakness:***
    * Uncover vulnerabilities in the systems, networks, or appliances that could be exploited by attackers
    * Includes misconfigurations, software flaws, design weaknesses, and human-related vulnerabilities
  * ***Validating Security Controls:***
    * Help organizations to assess the efficiency of existing security measures and secure digital assets
    * When attempt to bypass these controls, can determine if the security mechanisms in place are actually working as intended
  * ***Testing Detection and Response Capabilities:***
    * Helps identify if an organization has the necessary ability to detect and respond to security incidents
    * Helps identify gaps in monitoring systems, incident response procedures, and overall security awareness
  * ***Accessing Real-World Impact:***
    * By simulating real-world attack scenarios, provide with the conducted penetration tests a realistic assessment of the potential impact of a successful breach
    * Includes understanding the extent of possible data loss, system compromise, or business disruption 
  * ***Prioritizing Remediation Efforts:***
    * Results of a pentest can help organizations to prioritize their security efforts and allocate resources more effectively within the company
    * Critical vulnerabilities that pose the greatest risk can be addressed first
  * ***Compliance and Due Diligence:***
    * Regulatory frameworks require from companies frequent security checks like penetration tests and others
    * Reason is to ensure that organizations are actually safeguarding their critical information, customer data, and their systems
    * Helps organizations to prove their commitment to due diligence in cybersecurity
  * ***Enhancing Security Awareness:***
    * Penetration test often reveal security issues that may not be apparent through other means
    * Help to get the awareness about security risks among management, IT staff, and end-users
  * ***Verifying Patch Management:***
    * Pentests can verify whether security patches and updates have been properly applied and are effectively mitigating known vulnerabilities
  * ***Testing New Technologies:***
    * When new systems or applications are implemented within their internal or external infrastructure, penetration tastes help the company to ensure they they are securely configured before being deployed in a production environment
  * ***Providing a Baseline for Security Improvements:***
    * The results of a pentest serve most of the time as a baseline for measuring security improvements over time
    * Subsequent test can demonstrate progress in addressing identified issues
 
## Types of Penetration Tests
* ***Black Box Testing***
  * No prior knowledge of system
  * Can reveal issues
* ***White Box Testing***
  * Full access to system
  * Allows to identify problem
* ***Gray Box Testing***
  * Limited access
* ***External testing***
  * Focus on assets and services that are publicly accessible via the internet
  * Simulates how an attacker might attempt to breach an organization's defenses from the outside
* ***Internal testing***
  * Conducted from within the organization's network infrastructure
  * Simulates attack that could be initiated by malicious insider with legitimate access, or external threat actors who have successfully breached the network perimeter defenses
## Areas of Domains of Testing
* Rather than conducting a broad-spectrum security assessment, this type of testing concentrates exclusively on thoroughly examining and testing the company's infrastructure's environment. Testing includes but not limited to:
###### Network Infrastructure
* Most fundamental areas of penetration testing
* Focus on examining all network-connected devices
* Look for misconfigurations, weak passwords, outdated firmware, and security flaws that could allow unauthorized access
* Common activities include:
  * port scanning
  * service enumeration
  * analyzing network protocols
* Helps identify potential paths that attackers use to move laterally within the network
###### Web Application
* Testing websites, web applications, and we services for security vulnerabilities
* Look for common issues like SQL Injection, cross-site scripting (XSS), broken Authentication, and insecure direct object references
* Testing process includes examining both front-end interface and back-end functionaliy
* Evaluate how application handles user input, manages sessions, and protects sensitive data
* Assess the security of API endpoints and third-party integrations that could potentially exposes vulnerabilities
###### Mobile Application
* Focuses on identifying vulnerabilities in mobile apps
* Examine both Android and iOS applications
* Involves analyzing how apps store sensitive information
* Look for vulnerabilities in the app's runtime environment and evaluate whether the app properly validates certificate and handles secure communications
###### Cloud Infrastructure
* Involves evaluating the security of cloud-based resources
* Check for misconfigurations in cloud services, improper access controls, and vulnerabilities in cloud-native applications
* Requires understanding various cloud service providers and their security models
* Examine identity access management (I AM), configurations, network security groups, and data storage permissions to ensure proper security controls are in place
###### Physical Security Testing and Social Engineering
* Social Engineering testing
  * Assess an organization's human elemant
  * Often considered the weakest link in security
  * Includes testing employees' susceptibility to phishing attacks, pretexting, and other social manipulation techniches
* Physical Security Testing
  * Involvesevaluating the security of physical locations
  * Includes access controls, security cameras, and badge systems
* Help organizations identify gaps in *security awareness* training and physical security measures
* Testers might attempt access to buildings, test the effectiveness of security personnel, or conduct simulated phishing campaigns to evaluate employee awareness 
###### Wireless Network Security
* Focuses on evaluating the security of Wi-Fi networks and other wireless communications
* Look for vulnerabilities that could allow unauthorized access to wireless networks or enable eavesdropping on wireless communication
* Testing process involves analyzing wireless signal coverage, evaluating authentication mechanisms, and checking for proper networking segmentation between wireless and wired networks
* Examine how guest networks are isolated from corporate networks and verify that proper security controls are in place
###### Software Security
* Involves examining applications, operating systems, and firemware for security vulnerabilities
* Focuses on identifying weaknesses in *software code*, architecture, and implementation that could be exploited by attackers
* Analyze both compiled executable and source code to find potential security flaws
* Testing process includes static and dynamic analysis, reverse engineering, and fuzzing to identify buffer overflows, memory leak, and other software vulnerabilities
* Evaluate how the software handles input validation, memory management, and error handling to ensure robust security controls are implemented
## Penetration Test Benefits
* Are up-to-date with the ongoing attack vectors and approaches due to huge community
* Help organizations and businesses improve in several areas:
  * Enhancing the overall security posture
  * Compliance and risk management
  * Improving business continuity and protecting reputation
  * Validation of security controls
### Enhance Security Posture
* A proactive approach improves security posture and demonstrates a commitment to safeguard sensitive information
## Compliance and Penetration Testing
* ###### United States
  * ***PCI DSS*** mandates annual penetration testing for organizations processing card payments
  * ***HIPPS*** indirectly requires penetration testing through its risk assessment stipulations for healthcare entities
  * **SOC 2*** encourages penetration testing to validate the effectiveness of implemented security controls
  * ***GLBA under FTC*** rules, specifically requires financial institutions to conduct penetration test annually
* ###### European Union
  * **GDPR*** necessitates regular testing of security easures, which typically includes penetration testing for data protection compliance
  * ***NIS Diresctive*** implies the need for penetration testing to manage security risks effectively
* ###### United Kindom
  * ***The Data Protection Act 2018*** aligns with GDOR, suggesting penetration testing for assessing security measures
  * ***DSP Toolkit*** in healthcare recommends penetration testing for compliance with data security standards
* ###### India
  * ***RBI-ISMS*** requires banks and financial institutions to perform penetration testing for compliance
* ###### Brazil
  * ***LGPD*** implies the necessity of penetration testing to ensure the security of personal data
* It serves multiple critical purposes:
  * Helps organizations validate their security controls against established standards
  * Demonstrates due diligence to stakeholders and regulators
  * Ensures that security measures meet specific industry requirements
### Regulatory Frameworks and Standards
* Different industries are subject to various frameworks that mandate regular security assessments. Some of the most common frameworks include:
  * ***Payment Card Industry Data Security Standard*** ([PCI DSS](https://www.pcisecuritystandards.org/))
    * Requires organizations that handle credit card information to conduct regular penetration tests
    * Tests must be performed at least annually and after significant infrastructure or application changes
  * ***The Health Insurance Portability and Accountability Act*** ([HIPPA](https://www.hhs.gov/programs/hipaa/index.html))
    * Requires healthcare organizations to perform regular security assessments
  * ***The General Data Protection Regulation*** ([GDPR](https://gdpr-info.eu/))
    * Emphasizes regular testing to protect personal data of EU citizens
    * While not explicitly mandates penetration testing, it's considered a best practice for demonstrating compliance with security requirements
* Failing to comply with *regulatory frameworks* or standards* can have increasingly high and costly consequences for companies because these can include substantial financial penalties
  * Could face legal prosecution, mandatory audits, and temporary suspension of business operations and basically shut down the regulator or government
  * Companies may face increased pressure, which can lead to more frequent audits and oversight
### Compliance-Focused Penetration Testing Methodology
* Testers must follow a structured approach that aligns with regulatory requirements. This typically involves:
  * ***Scoping:***
    * Carefully defining the test boundaries based on compliance requirements
    * Includes identifying systems that fall under regulatory oversight and determining the appropriate testing depth
  * ***Documentation:***
    * Maintaining detailed records of all testing activities, findings, and remediation recommendations
    * Serves as evidence of compile and helps demonstrate due diligence to auditors
  * ***Risk Assessment:***
    * Evaluating findings in the context of compliance requirements and assigning risk levels that reflect both technical severity and regulatory impact
* When company fails to implement proper commpliance-forces penetration testing methodology it exposes companies to significant risks
* Poor testing structure can result in incomplete assessments, insufficient documentation for audits, and inconsistent standards across compliance frameworks
* Can also lead to inefficient resource allocation, as well as difficulties in properly prioritizing vulnerabilities 
### Reporting for Compliance
* Must meet specific requirements beyond standard technical reports. These reports should include:
  * ***Executive Summary:*** A high-level Overview of findings that specify addresses compliance requirements and potential regulatory impacts
  * ***Detailed Findings:*** Technical details of vulnerabilities discovered, including their relationship to specific compliance requirements or controls
  * ***Remediation Guidance:*** Clear, actionable recommendations that help organizations address findings while maintaining compliance
  * ***Attestation:*** Formal statements or certifications required by specific regulations, confirming that testing was performed according to required standards
* Poor compliance reporting can result in severe consequences including
  * Mandatory corrective actions
  * The loss certifications and business opportunities
  * Increased audits and oversight by regulators
* During security incidents, inadequate reporting can increase legal liability and compliance due diligence demonstrations, leading to higher damage in legal insurance matters
#### Common Challenges in Compliance Testing
* Organizations often face challenges when conducting compliance-focused penetration testing. Understanding these challenges helps in better preparation and execution:
  * ***Scope Management:*** Balancing the need for comprehensive testing with compliance requirements while managing time and resource constraints. This often requires careful planning and prioritization
  * ***Testing Limitations:*** Some compliance requirements may restrict certain types of testing activities to prevent disruption to critical systems. Testers must find ways to efficiently assess security security while respecting these limitations.
  * ***Continuous Compliance:*** Many regulations require ongoing testing and monitoring. Organizations must develop sustainable testing programs that can be repeated regularly while maintaining consistency and quality
### Best Practices for Compliance Testing
* To ensure effective compliance-focused penetration testing, organizations should follow these best practices:
  * ***Engage Qualified Tester:*** Work with penetration testers who understand both technical security testing and relevant compliance requirements. This expertise helps ensure that testing activities align with regulatory needs
  * ***Maintain Testing Calendar:*** Develop and maintain a testing schedule that aligns with compliance requirements and organizational changes.This helps ensure that testing is performed at required intervals and after significant modifications.
  * ***Integrate with Governance:*** Align penetration testing activities with broader Governance, risk, and compliance (GRC) programs. This integration helps ensure that testing supports overall compliance subjectives.
 
## Ethics of a Penetration Test
* Breaking ethical rules in penetration testing leads to serious problems
  * Companies risk legal issues from unauthorized testing and system damage
  * Testers can face criminal prosecution and career-endinb reputation damage
* Bad testing practices often cause system failures, major business distribution, and event data breaches
### Core Ethical Principles
* Ethical penetration testing follows key principles that all security professionals must follow
1. ***"Do not Harm"***
   * Testers must not damage systems, corrupt data, or disrupt business operations
   * Every action needs careful evaluation to avoid negative impacts on the target system, both short-term and long-term
3. ***Confidentiality***
   * During an assessment, testers often obtain knowledge of sensitive data such as system vulnerabilities, personal information, business secretes, and proprietary data
   * Must keep information completely confidential during and after the engagement
     * Builds essential trust between security professionals and clients
### Legal Considerations and Authorization
* Obtaining proper *written authorization* is an absolute requirement before initiating any penetration testing activities
* Must secure explicit, documented permission that clearly outlines the scope and parameters of testing engagement
* Contract or statement of work needs to exhaustively detail all authorized activities, specific systems/networks that are to be tested, as well as any limitations or restrictions that apply to the assessment
* Helps to prevent any misunderstandings about the boundaries of work and serves as legal protection for actions
* Crucial to understand that discovering potential attack actors or vulnerabilities does not constitute permission to exploit them
  * Must maintain strict adherence to the agreed-upon boundaries
* Maintaining boundaries builds trust and demonstrates commitment to ethical professional conduct
### Professional Conduct and Responsibility
* Must maintain *clear and consistent communication channels* with clients throughout the engagement
* Professional communication involves promptly reporting any critical security vulnerabilities
* *Professional integrity* demands immediate accountability when issues arise during
* Includes:
  * Providing a full explanation of what happened
  * Implementing immediate mitigation steps where possible
  * Working collaboratively with clients to serve any problems that resulted from the testing activities
### Data Handling and Privacy
* Penetration testers frequently come across sensitive data during assessments, such as personal information, financial records, or intellectual property. Ethically managing this data is critical:
  * ***Data Extraction:*** Only removes data if it's specifically required by the test scope
  * ***Data Security:*** Safeguard any data gathered during the test
  * ***Data Disposal:*** Completely destroy all data once the test is concluded
  * ***Personal Use:*** Never exploit the information for personal benefit
  * ***Legal Compliance:***Adhere to privacy laws like GDPR or HIPA
### Documentation and Reporting
* *Comprehensive documentation* is essential during penetration testing engaements
  * Serves as a critical protective measure for all parties involved by establishing an unambiguous trail of all activities
* Must systematically capture and detail every test executed, tools and configurations utilized, and findings from each phase of testing
* Ensure complete transparency and accountability throughout engagement
* When preparing reports, maintain strict professional objectivity and precise factual accuracy
  * Avoidtemptation to sensatialize or exaggerate the severity of discovered vulnerabilities, or any improper attempts to secure additional business opportunities
  * Concentrate efforts on providing detailed, actionable remediation steps that are properly prioritized and technically feasible for client
* Each recommendation should include clear implementation guidance and specific steps for validation, enabling clients to effectively address identified security gaps
### Social Engineering Considerations
* Social Engineering assessments require strict ethical standards
* Testers must remain professional and respectful to all participants
* Testers must avoid manipulative tactics that could hurt workplace morale, damage relationships, or cause psychological stress
* Keep testing environment positive and constrictive
* Organizations must provide *clear support* for employees in social engineering exercises
  * Focus on positive learning rather than shaming those who fail tests
* Failing to follow ethical guidelines can have severe consequences
  * Organizations may face legal liability for privacy violations, emotional distress claims, or harassment allegations from affected employees
* Unethical Social engineering can create a toxic work environment, destroy employee trust, and cause lasting psychological impact on victims
  * Can result in increased employee turnover, decreased productivity, and breakdown in security awareness culture
### Building Trust and Reputation
* Any deviation from established ethical guidelines has potential to irreparably damage professional reputation and permanently end what could have been a promising career in security testing

## Penetration Texting vs. Vulnerability Assessment
## Vulnerability Assessment
* Functions as broad diagnostic scan of systems
* Assessment process leverages automated scanning tools, designed to detect various types of vulnerabilities and system misconfigurations within the infrastructure
* The fundamental objective remains straightforward yet comprehensive:
  * Identify and document all possible vulnerabilities present within system environment, regardless of immediate exploitability or potential impact level
## Penetration Testing
* Actively attempting to compromise system security through controlled attempts
* Professionals, operating under explicit authorization and strict parameters, assume the role of potential attackers
## Key Difference in Approach and Execution

|Vulnerability Assessment|Penetration Testing|
|:---:|:---:|
|Provides broad coverage through scanning and the identification of known security issues|Conduct targeted, in-depth investigations by actively attempting to exploit discovered or potential vulnerabilities|
|Rely on automated scanning tools primarily that require minimal human intervention to operate effectively|Demands highly skilled security professionals who combine automated testing tools with sophisticated manual testing techniques and create problem-solving approaches to simulate real-world attack scenarios|
|Monthly or quarterly basis, with additional scans performed following any significant system modifications or infrastructure changes to maintain security awareness|Follows an annual schedule, with additional test conducted after major system upgrades or architectural changes. These assessments become critical before deploying neew services or during the process of obtaining various security certifications and compliance validations|

## Complementary Nature of Both Approaches
* Best to incorporate both methodologies in a coordinated manner
* ***Vulnerability Assessment*** Excel at identifying potential security issues
  * Reports provide valuable input for planning routine maintenance and security updates
* ***Penetration test*** provide practical validation of the actual risk levels associated with discovered vulnerabilities
  * Test results often catalyze more significant investments in infrastructure
# Penetrations Test Overview
## Structure of a Penetration Test
1. ###### Pre-Engagement Phase
* Sets foundation for entire penetration test
* Testers work closely with the client to understand their specific needs, concerns, and objectives
  * Define the scope of the test
  * Establish timelines
  * Demand which systems and networks will be tested
* Documentation is creates
  * *Rules of Engagement* (RoE) document ~ Outlines permitted testing activities
  * Contact information for key personnel
  * Emergency procedures
* Testers and clients sign necessary legal documents
  * *Non-Disclosure Agreements (NDAs)*
  * Service contracts to protect both parties   
2. ###### Information Gathering Phase
* A.K.A. ***Reconnaissance***
* Collecting as much relevant information about the target as possible
* ***Passive Reconnaissance**
  * Gathering information without directly interacting with the target systems
  * Might include:
    * Public records
    * Searching social media
    * Reviewing company websites
    * Utilizing OSINT (*Open Source Intelligence*) tools
  * Leaves no trace and poses no risk to the target infrastructure
* ***Active reconnaissance***
  * Involves direct interaction with the target systems
  * Includes:
    * Port scanning
    * Service enumeration
    * Banner grabbing
  * Provides detailed technical information about the target environment 
3. ###### Vulnerability Assessment Phase
* *Analyze the information* gathered to identify potential security weaknesses
* Involves using various automated scanning tools and manual techniques to discover vulnerabilities in the systems, applications, and network infrastructure
* Analyze results, eliminate false positives, and understand how different vulnerabilities might be combined to create more significant security risks
  * Requires deep technical knowledge and experience in understanding how various systems and applications work
4. ###### Exploitation Phase
* Attempt to *actively exploit* the vulnerabilities identified
* Done to demonstrate real-world Impact of security weaknesses
* Establish what an attacker might be able to achieve
* Testers must carefully document activities and maintain a precise record of the systems accessed
* Crucial to follow agreed-upon RoE and avoid causing any damage to production systems
* Skilled testers often create detailed attack chains, showing how multiple vulnerabilities can be combined to achieve deeper access
5. ###### Post-Exploitation Phase
* Once initial access is gained, this phase begins
* Involves activities such as privilege escalation, lateral Movement through the network, data ex filtration testing, and maintaining persistence
* Goal is to understand the full extent of what an attacker could accomplish after breaching defenses
6. ###### Lateral Movement Phase
* Involves navigating through the network after initial access to discover additional systems, resources, and potential targets
* Focus on identifying and exploiting trust within the network
* Tester employ various techniques:
  * Credential harvesting
  * Pass-h=the-hash attacks
  * Exploiting network protocols to move between systems
* Helps demonstrate how an attacker could potentially spread through the organization's network infrastructure and access sensitive resources
7. ###### Proof of Concept
* Involves creating *detailed documentation and evidence* that demonstrates how vulnerabilities were exploited
* Includes developing reliable and repeatable methods to reproduce the identified security issues
  * Helps validate the findings and assists the client's technical team in understanding and fixing the vulnerabilities
* Testers create specific examples, scripts, or code that showcase the exploitation process
  * Resulting documentation includes
    * Step-by-step procedures
    * Required tools or configurations
    * Any specific conditions necessary for the exploit to work
 * This information is crucial for verifying the vulnerability and ensuring that the client's security testers can effectively test their fixes
8. ###### Post-Engagement Phase
* The reporting phase is crucial as it *transforms* the technical findings into *actionable information for the client*
* Well-written report includes
  * An executive summary for management
  * Detailed technical findings for the IT team
  * Clear recommendations for remediation
* Each vulnerability should be clearly described, including it potential impact, steps to reproduce, and specific recommendations for the issue
* Report should include evidence like screenshots and logs to support the findings
* Risk ratings should be assigned to help the client prioritize their remediattion efforts
9. ###### Remediation Supporting and Retesting
* After delivering the report, engagements include a period of remediation support
* Testers make themselves available to answer questions about findings and provide additional guidance on implementing fixes
* Once client has addressed the identified vulnerabilities, a retest is often performed to verify that the fixes were implemented correctly and that no new vulnerabilities were introduced during the remediation process
  * Helps ensure that the client's security posture has genuinely improved as a result of the penetration test
## Prerequesites for a Penetration Test
1. ###### Legal Authorization & Documentation ~
* Begins with a formal written agreement, called *Statement of Work (SoW)* or *Master Services Argreement (MSA*
  * ***MSA:***
    * Often used when there's an ongoing relationship between the client and the penetration testing service provider
    * Outlines the overall terms and conditions of the business relationship
  * ***SoW:***
    * More specific to penetration testing engagement
    * Needs to clearly outline the scope, limitations, and objectives of the penetration test
* Crucial to obtain explicit written permission from the organization that owns the systems you'll be testing
  * Verbal approval is not enough

|Aspect|Master services Agreement|Statement of Work|
|:---|:---|:---|
|Purpose|Establishes the overall terms of the business relationship between the client and the service providers|Defines the specifics of a particular engagement|
|Scope|Broad, covering general terms like payment terms, confidentiality, liability, and dispute resolution for all services|Narrow, detailing project-specific details like objectives,scope, deliverables, timeline, and testing parameters for one engagement.|
|Use Case|Used for ongoing or multiple engagements; it reduces the need to renegotiate terms for each new project.|Used for each new project or when specifics of the engagement change, even if under an existing MSA.|
|Content|Includes general clauses about service delivery, intellectual property, termination, etc.|Includes detailed information on what will be tested, how, when, and any limitations or exclusions.|
|Duration|Generally long-term, converting the duration of the business relationship.|Short-term, specific to the duration of the project or engagement.|
|Legal Authorization|Provides the framework for legal Authorization to conduct services.|Provides explicit, written permission for the specific penetration testing activities.|
|Amendment|If a company regularly hires a security firm, the MSA could cover all security services over time.|The SoW for one of those engagements would detail the exact penetration testing activities for a specific network.|
|Example|If a company regularly hire a security firm, the MSA could cover all security services over time.|The SoW for one of those engagements would detail the exact penetration testing activities for a specific network.|
* Additional penetration testers must secure a *"Get Out of Jail Free"* letter
  * A.K.A. *Rules of Engagement* (RoE) document
  * Serves as proof of authorization to perform potentially suspicious activities on the target systems
  * Should include:
    * Contact information for key stakeholders
    * Emergency procedures
    * The defined testing windows
 
2. ###### Scope Definition and Boundaries ~
* Well defined scope is essential for any penetration testing engagement
* Should comprehensively document *all systems and assets* that are authorized for testing, including:
  * IP ranges
  * Domain names
  * Web applications
  * Network segments
  * Individual systems
* Documentation must explicitly outline what is strictly off-limits during the assessment, including:
  * Critical infrastructure
  * Medical devices
  * Production databases
  * Backup systems
* Should clearly specify whether social engineering attampts or physical security assessments are permitted
  * These require special considerations and often additional authorizations
* Crucial to establish and document the *exact testing windows*, many organizations restrict testing to certain time periods
  * These timing restrictions help minimize potential disruption to business operations and ensure adequate support staff are available if issue arise
* Testing schedule should account for any planned system maintenance, backup operations, or other technical activities that could interfere with or be affected by the penetration test
   
3. ###### Information Gathering
* Depending on the type and scope of the penetration test, a *comprehensive collection of technical information* about the target environment must be gathered before initiating any testing activities
* This preparatory phase involves acquiring and analyzing various forms of documentation and intelligence
* Understanding completed technology stack is paramount for effective testing preparation. The typically means obtaining detailed knowledge of:
  * The target environment's operating systems and their versions
  * All deployed applications and their configurations
  * The various security controls implemented throughout the infrastructure
* Involves *identification and documentation of sensitive systems or data* that require consideration during testing
* Proper identification and documentation of these sensitive assets helps ensure that testing activities do not inadvertently cause disruption to critical services or compromise regulated data
 
4. ###### Communication Channels & Emergency Procedures
* Establish clear communication channels
* Should have *contact information for key personnel*, including:
  * Technical staff
  * Project managers
  * *emergency contacts*
* Define escalation procedures for various scenarios
* Create *incident response plans* that outline what to do if something goes wrong
  * Should include immediate points of contact and procedures for halting testing if necessary
   
5. ###### Testing Environment Preparation
* Ensure testing environment is properly configured before beginning, includes:
  * Setting up isolated networks if required
  * Preparing testing tools and platforms
  * Configuring logging systems to document activities
* Testing environment should be secure and separate from any personal or unrelated work to prevent cross-contamination
* Verify testing tools are properly licensed
   
7. ###### Backup and Recovery Considerations
* Confirm that the target organization has recent *backups of all system in scope*
* Essential to have recovery options available
* Discuss the organization's backup and recovery capabilities and ensure they're adequate for the planned testing activities
 
8. ###### Documentation & Reporting
* Establish documentation requirements *upfront*
* Know what kind of reporting the client expects, including:
  * Format
  * Level of detail
  * Any specific compliance requirements
* Some organizations may require evidence of findings to be documented in particular ways for regulatory compliance
* Plan how to maintain detailed logs of all testing activities
  * These logs are crucial for writing the final report and can be essential if any issues arise during testing
   
9. ###### Professional Liability & Insurance
* This type of specialized insurance protects against potential claims arising from testing activities, including:
  * Accidental system damage
  * Data Breaches
  * Business interruption
* Many clients have strict requirements regarding minimum insurance coverage levels
  * Some may require specific riders or endorsements related to Cybersecurity testing
* Crucial to regularly review and update coverage to ensure it remains adequate as testing activities evolve and expand
    
10. ###### Confidentiality & Data Handling
* Establish clear *procedures for handling sensitive data* discovered during testing, including:
  * How findings will be communicated
  * How data will be stored and transformed
  * When/how data will be destroyed after the engagement ends
* Many organizations have specific requirements for handling their data, especially in regulated industries
* Taking time to address prerequisites thoroughly will set the foundation for successful penetratio test
  * One that provides value to the client while protecting all parties involved
* *Non-Disclosure Agreement (NDA)* should be signed before any penetration testing engagement begins.
* The NDA should clearly outline:
  * The type of confidential information that will be protected
  * Duration of confidential obligations
  * Permitted uses of confidential information
  * Data destruction requirements after project completion
  * Consequences of unauthorized disclosure
* Protect both the testing organization and the client by establishing clear legal boundaries around information handling and creating mutual understanding about confidentiality expectations
## Required Skills
* Penetration testing is a *complex and multifaceted* profession that requires a diverse skill set for several key resasons:
  * First, modern *IT environments* are incredibly complex, combining various technologies, systems, and architectures
    * What matters is having the *ability to learn quickly* by understanding how these elements work together
    * Requires fundamental knowledge spanning networking, operating systems, web technologies,and more
  *  Second, successful penetration testing involves more than just technical skills
    * Testers must be able to *think creatively and outside the box*, similar to an attacker, while at the same time maintaining ethical boundaries
    * Must be able to communicate *professionally*0
    * Combining technical and soft skills is essential for delivering value to clients 
  *  Third,the Cybersecurity landscape is constantly evolving
    * New technologies emerge, *new vulnerabilities* are discovered almost daily, and attack methods* become more sophisticated
    * Requires lifelong leaarners who can adapt and expand skill set continuously
  * Finally, penetration testing often involves high-stakes situations where mistakes *could potentially damage* critical systems or expose sensitive data
    * Broad skill set required helps ensure tester can work competently and safely while providing meaningful security insight to clients

## Methodologies & Frameworks
### Core Penetration Testing Methodolodies
* ***Penetration Testing Execution Standard ([PTES](http://www.pentest-standard.org/index.php/Main_Page))*** ~ Provides a framework that divides the penetration testing process into seven distinct phases
* ***Technical Guide to Information Security Testing and Assessment ([NIST](https://www.nist.gov/privacy-framework/nist-sp-800-115))*** represents a more formal approach
  * Provides valuable guidance on security assessment planning
  * This framework is relevant when working with government agencies or organizations that follow NIST guidelines
* ***Open Web Application Security Project ([OWASP](https://owasp.org/www-project-web-security-testing-guide/stable/))*** is a widely adapted methodology that offers guidance for Web application security testing
  * Provides a structured approach through four main phases:
    * Information Gathering
    * Configuration and Deployment Management Testing
    * Identity Management Testing
    * Authentication Testing
  * The guide contains distinct testing procedures, along with practical examples, for nearly every vulnerability seen in web applications
  * Updated continuously by the community to address emerging threats, making it tremendously valuable resource for anyone interested in web application security
* The [MITRE ATT&CK](https://attack.mitre.org/) framework has become increasingly important
  * Provides a comprehensive knowledge base of adversary tactics and techniques observed in real-world attacks
  * Used to simulate realistic threat scenarios and ensure their testing covers the full spectrum of potential attack vectors
### Choosing the Right Approach
* Most professional pentesters *don't strictly adhere* to a single methodology but combine elements from various frameworks together
  * Allows for flexibility while maintaining structure and thoroughness
#### Developing Your Personal Methodology
* Experienced pentesters often incorporate their unique experiences and lessons learned from previous engagements
* Can be tailored to specific types of assessments or industries that a pentesters frequently encounter
#### Steps to Develop Your Methodology
* Start with established frameworks as foundation
* Learn and practice to take notes properly for yourself
* Learn and improve your problem solving approach
* Document successful techniques and approaches from each box, Lab, and engagement
* Incorporate tools and scripts that have proven effective, rewrite them, and write your own
* Create custom checklists for different testing cases (web testing, network testing, information gathering, etc.)
* Regularly update your methodology based on the experience you gain

# Domains of Testing
## Web App Penetesting
* Typically follow a three-tier architecture:
  * Presentation tier (front-end)
  * Applications tier (backend)
  * Database tier
### Common Web Application Vulnerabilities
* Here are some of the most critical ones:
  * Injection Vulnerabilities
  * Authentication & Session Management
  * Cross-Site Scripting
### Essential Tools and Skills
* Proxy tools like [Burp Suite Professional](https://portswigger.net/burp/pro) and [OWASP ZAP](https://www.zaproxy.org/) are essential for intercepting and analyzing web traffic
### Legal and Ethical Considerations
* Must always be conducted within legal and ethical boundaries
* Understand and follow disclosure procedures
* Remember web application penetration testing is not just about finding vulnerabilities
  * It's about helping organizations improve their security postures
## Netowrk Security Testing
* A systematic process of evaluating network infrastructure security by simulating real-world attack
* Networks typically consist of various components
  * Routers
  * Switches
  * Firewalls
  * Servers
  * Endpoints
* Each component potentially harbor vulnerabilities that could compromise the entire network security
* Understanding how these components interact and communicate is fundamental to conducting effective network penetration tests
### Common Network Security Vulnerabilities

|Vulnerability|Desctiption|
|:---|:---|
|***Misconfigured Services***|Improperly configured network services, default credentials, and unnecessary open ports that could provide unauthorized access|
|***Unpatched Systems***|Systems and applications running outdated software versions with known security vulnerabilities|
|***Weak Authentication***|Poor password policies, lack of multi-factor authentication, and insecure password storage mechanisms|
|***Insecure Protocols***|Use of deprecated or unencrypted protocols like FTP, Telnet, or HTTP instead of their secure alternatives|
|***Network Segmentation Issues***|Inadequate network segmentation allowing lateral movement between different security zones|
|***Exposed Management Interfaces***|Administrative interface accessible from unauthorized networks or the internet|
|***Missing Security Controls***|Absence of essential security measures like firewalls, IDS/IPS systems, or proper access controls|
* Tools like [Nmap](https://nmap.org/) helps to map out the network and spot potential weak points by looking at which ports are open or closed, and what services are running
* May use automated scanners like nmap, [Nessus](https://www.tenable.com/products/nessus), or [OpenVAS](https://openvas.org/)
  * Still want to always double-check findings by hand to make sure they're real
* In testing phase, try to use these weak spot to access systems or get sensitive data
  * Must be careful not to cause damage
  * If an old/unpatched version of a services is discovered, might test for something like a buffer overflow
  * If an open FTP service could check and see if anonymous login is enabled
* When using tools like [Metasploit](https://www.metasploit.com/) , knowing how vulnerabilities work is key
* Keep detailed notes of everything accomplished
### Essential Tool and Technologies
* Requires proficiency with various tools. Some fundamental tools include:
  * ***Network Mapping Tools:*** Tools like Nmap for network discovery and security auditing
  * ***Vulnerability Scanners:*** Nessus, OpenVAS, and similar tools for identifying known vulnerabilities
  * ***Exploitation Frameworks:*** Metasploit Framework for developing and executing exploit code
  * ***Packet Analysis Tools:*** Wireshark for analyzing network traffic and identity potential security issues
  * ***Password Cracking Tools:*** John the Ripper and Hashcat for testing password security
* Understanding network protocols is crucial for effective penetration testing
  * Key protocols include TCP/IP, UDP, IMCP, and application-layer protocols like HTTP, FTP, and SSH
* Wireless network testing is a specialized aspect of network penetration testing
  * Involves assessing the security of WiFi networks, including testing excryption protocols (WEP, WPA, WPA2, WPA3), analyzing authentication mechanisms, and identifying rogue access points
### Common Pitfalls
* *rushing* through the critical Reconnaissance phase without proper attention to detail
* Placing excessive *reliance on automated scanning tools* without understanding their limitations
* Neglecting to manually validated and verity findings through hands-on investigation
## Cloud Security Testing
* A specialized security assessment aimed at uncovering vulnerabilities and weaknesses within *cloud-based infrastructures*
* Understand the basic cloud services models:
  * Infrastructure as a Service (IaaS)
  * Platform as a Service (PaaS)
  * Software as a Service (SaaS)
### Key Differences from Traditional Penetration Testing
* Shared Responsibility Model, where security responsibilities are divided between the cloud services provider and the customer
* Resources can be created, modified, or destroyed automatically, making it essential to adapt testing approach accordingly
* Cloud environments often implement complex access controls and identify management systems that require specialized testing methodologies
### Essential Skills for Cloud Penetration Testing
* To be proficient need to develop expertise in several areas
* Strong understanding of cloud platforms like AWS, Azure, or Google Cloud Platform is essential
* Here are the common components of a cloud penetration test:
  * The assessment begins with *Reconnaissance* and enumeration of cloud resources
    * Involves identifying all services, storage buckets, databases, and other cloud components
    * Utilizing tools like cloud-specific scanners and enumeration scripts can significantly aid this process
  * *Access control* testing, where you access the implementation of *Identify and Access Management (IAM)* policies
    * Includes Examining for overly permissive roles, misconfigured security groups, and weak authentication mechanisms
  * Configuration Assessment is crucial, where you scrutinize cloud services in search of *security misconfigurations*
    * Look out for issues like publicly accessible storage buckets or unencrypted databases
  * Must forget network security testing
    * Involves reviewing *virtual network configurations*, security groups, and network access controls to ensure they are set up correctly to mitigate risks
  * *Data security testing*
    * Evaluating the implementation of encryption, data loss prevention (DLP), and key management practices designed to safeguard sensitive information
  * *Application security testing examine the security posture of cloud-native applications
    * Includes checking for vulnerabilities in application code and API's, ensuring that they interact safely and securely with other cloud services
### Common Vulnerabilities in Cloud Environment
* Misconfigured storage buckets that expose sensitive data are common findings
* Excessive permissions and inadequate I AM policies can lead to *privilege escalation opportunities*
* Insecure API monitoring can make it difficult to detect and respond to security incidents
* Container security issues are frequently encountered
* Inadequate network segmentation and overly permissive security groups can expose services to unauthorized access
* Lack of encryption for data at rest and it transit remains a significant concern
### Tools and Technologies
* AWS or Azure Security Center
* Thrid-party tools: Cloudsploit, Scout Suite, and Prowler
## Social Engineering
## Mobile Security Testing
## Reverse Engineering

# Daily Life
## Utilizing Penetration Testing Results
## Daily Routine of a Penetration Tester
## Penetration Testing as a Profession
