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

## A04:2025 - Cryptographic Failure

## A05:2025 - Injection

## A06:2025 - Insecure Design

## A07:2025 - Authentication Failures

## A08:2025 - Software or Data Integrity Failures

## A09:2025 - Security Logging and Alerting Failures

## A10:2025 - Mishandling of Exceptional Conditions 
