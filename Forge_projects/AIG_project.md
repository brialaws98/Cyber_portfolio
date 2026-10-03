## Introduction
### Name: ***Shields Up***
* As an information Security Analyst, analyze security alerts and respond to a ransomeware attack using Python and stakeholder management skills
###### About Challenge:
* Will learn skills - both non-technical and technical - that are used in the world of cybersecurity
* Notify internal stakeholders that may be at risk from a ransomware attack and then recovers some collaboration with the FBI and the NSA
* Then, apply the Intel to reduce the risk of an attack on AIG

## Task #1
CISA has just released an alert on a new zero-day vulnerability for Apache Log4j. Research the vulnerability and publish an advisory to affect teams to affected teams to alert and prevent exploitation.
###### What you'll learn:
* How to address a vulnerability that may affect Product Development Staging Environment infastructure
###### What you'll do:
* Review some recent publications from the Cybersecurity & Infrastructure Security Agency (CISA)
* Research the reported vulnerability
* Draft an email to affected teams to alert then of the vulnerability, and explain how to remediate
### Background information:
* I am an ***Information Security Analyst*** in the Cyber & Information Security Team
  * Common task include staying on top of emerging vulnerabilities to make sure that the company can remediate them before an attacker can exploit them
* Will be asked to review some recent publications from the CISA, *an Agency that has the goal of reducing the nation's exposure to cyber security threats and risks
* After reviewing publications, will need to draft an email to inform the relevant infrastructure owner at AIG of the seriousness of the vulnerability that has been reported
###### Here are the instructions for the task:
* The CISA  has recently published the following two advisories:
  * The [first advisory (Log4j)](https://www.cisa.gov/uscert/ncas/alerts/aa21-356a), outlines a serious vulnerability in one of the world's most popular logging software
  * The [second advisory](https://www.cisa.gov/news/2022/02/09/cisa-fbi-nsa-and-international-partners-issue-advisory-ransomware-trends-2021) explores how ransomware has been increasing for a large company like AIG
* Task is to respond to the Apache Log4j zero-day vulnerability that was released to the public by advising affected teams of the vulnerability
1. Conduct your research on the vulnerability using the "CISA Advisory" resources provided above as a starting point
2. Analyze the "Infrastructure List" to find out which infrastructure may be affected by the vulnerability, and which team has ownership
   * The *Product Development Staging Environment* infrastructure may be affected by the vulnerability
   * The *Product Development team* has ownership of the affected infrastructure
### Drafting the email:
* ***Affected team (product):*** Product Development (Product Development Staging Environment)
* ***Vulnerability description:*** ***Log4j*** is a common open-source Java-based logging utility used by developers to record system events, errors, Nd operational messages in software applications. You can learn more in the NSIT disclosures: CVE-2021-44228, CVE-2021-45105, and CVE-2021-45046.
* ***Vulnerability risk/impact:*** Critical - An attacker can archive full Remote Code Execution (RCE) without requiring authentication
* ***Vulnerability remediation:***
  * Identify assets by Log4Shell and other Log4j-related vulnerabilities
  * Upgrading Log4j assets and affected Products to the latest version as soon as patches are available and remaining alert to vendor software updates
  * Initiating hunt and incident response procedures to detect possible Log4Shell exploitation
* ***Any assurances to ensure advisory was actioned***
* Tips for email:
  * Make it direct and straight to the point
  * Can assume the infrastructure owner is technical
  * Explain the risk/impact, method of exploitation, and remediation steps
## Task #2
One of our system has been exploited by the Log4j vulnerability and the attacker just tried to load some ransomeware! Write a bruteforcer to break into the ransomware-encrypted files, so we don't have to pay the ransom
###### What you'll learn
* What 'bruteforcing' involves
* How to respond to a ransomware virus using Python
###### What you'll do
* Write a PPython script to bruteforce the decryption key of the encrypted file, to avoid paying a ransom
### Setting the scene for the task
* The advisory email that was put together and sent to the affected team provided context on what the vulnerability was, and how to remediate it
* Unfortunately, an attacker was able to exploit the vulnerability on the affected server and begin installing a ransomware virus
  * The Incident Detection & Response team was able to prevent the ransomware virus from completely installing, so it only managed to encrypt on zip file
* Internally, the Chief Information Security Officer does not want to pay the ransom
  * There isn't any guarantee that the decryption key will be provided or that the attackers won't strike again in the future
* We are Tasked with bruteforcing the decrytionn key
  * Based on the attacker's sloppiness, we don't expect this to be be a complicated key
  * They used copy-pasted payloads and immediately tried to use ransomware instead of moving around laterally on the network
### Background information
* Will write a Python Script to bruteforce the decryption key of the encrypted file
* ***Bruteforcing:*** *The act of repeatedly trying different combinations to break the password encryption
* Ransomware will often encrypt all files on a device, and sometimes give the decryption key after the ransome has been paid (but this is not always the case!)
  * In this task, I will break the encryption without paying the ransom
###### Steps taken to write and execute the brute-force
*  I was provided a fundamental Python 3+ template to download
  * After downloading it, I then unzipped the file and discovered a file called *EncryptedFilePack* that included: Rockyou.txt (list of possible passwords), bruteforce.py (Python Script to decrypt), and enc.zip (The file that needs to have the decrypted password entered to unzip this file)
  * I edited the Python file as shown bellow:
```
# Use a method to attempt to extract the zip file with a given password
# def attempt_extract(zf_handle, password):
def attempt_extract(zf_handle, password):
    try:
        zf_handle.extractall(pwd=password)
        return True
    except:
        return False

def main():
    print("[+] Beginning bruteforce ")
    with ZipFile('enc.zip') as zf:
        with open('rockyou.txt', 'rb') as f:
            # Write your logic here...
            # Iterate through password entries in rockyou.txt
            for p in f:
                password = p.strip()
                # Attempt to extract the zip file using each password
             # Handle correct password extract versus incorrect password attempt)
                if attempt_extract(zf, password):
                    print("[+] Correct password: %s" % password)
                    exit(0)
                else:
                    print("[-]Incorrect password: %s" % password)

    #print("[+] Password not found in list")
    print("[+] Password not found in list")

if __name__ == "__main__":
    main()
```
  * This allowed be to get into the secret file that was affected by the ransomware
