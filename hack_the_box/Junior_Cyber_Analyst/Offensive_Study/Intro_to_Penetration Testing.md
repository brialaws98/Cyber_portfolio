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

# Penetrations Test Overview
## Structure of a Penetration Test
## Prerequesites for a Penetration Test
## Required Skills
## Methodologies & Frameworks

# Domains of Testing
## Web App Penetesting
## Netowrk Security Testing
## Cloud Security Testing
## Social Engineering
## Mobile Security Testing
## Reverse Engineering

# Daily Life
## Utilizing Penetration Testing Results
## Daily Routine of a Penetration Tester
## Penetration Testing as a Profession
