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
## Compliance and Penetration Testing
## Ethics of a Penetration Test
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
