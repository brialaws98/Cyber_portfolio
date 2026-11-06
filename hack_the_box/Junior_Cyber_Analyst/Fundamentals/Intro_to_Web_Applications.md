# Introduction to Web Applications
## Introduction
### 1. What are web applications?
* A [web application](https://en.wikipedia.org/wiki/Web_application) is an interactive application that runs inside a web browser.
* Web applications commonly use a [client-server architecture](https://cio-wiki.org/wiki/Client_Server_Architecture).
[stratoflow.com](https://stratoflow.com/web-application-development/?utm_source=chatgpt.com)
* There are two main components:
  * ***Front end (client-side)***	What the user sees and interacts with.
  * ***Back end (server-side)***	Processes requests, runs application code, and communicates with databases.
* Examples of web applications:
  * Gmail – Email services.
  * Amazon – Online shopping.
  * Google Docs – Online document editing.
* Important concept: The browser communicates with the web server to request and receive information.
### 2. Web applications vs. websites
* Understanding the difference is important when performing penetration tests.
  * Traditional website (Web 1.0)	Web application (Web 2.0)
  * Mostly static content	Dynamic content
  * Same information for everyone	Content can change based on users
  * Limited interaction	Interactive functionality
  * Changes require developers to edit pages	Can update content in real time
* Key characteristics of modern web applications:
  * Modular design.
  * Adapt to different display sizes.
  * Can run across different platforms.
  * Support interactive functionality.
* Resources:
  * [Web 1.0](https://en.wikipedia.org/wiki/Web_2.0#Web_1.0)
  * [Web 2.0](https://en.wikipedia.org/wiki/Web_2.0)
### 3. Web applications vs. native applications
* A ***native application*** is software designed for a particular operating system.
* Examples include desktop applications installed on Windows, macOS, or Linux.
  * Web applications
    * Run inside a browser
    * Usually don't require installation
    * Platform-independent
    * Updates happen on the server
    * Limited by browser capabilities
  * Native applications
    * Run directly on an operating system
    * Usually require installation
    * Often platform-specific
    * Updates may need to be installed
    * Can access OS libraries and hardware
* Important terms:
  * *Platform-independent*: Can run on different operating systems through a browser.
  * *Version unity*: Users access the same application version.
  * *Hybrid applications*: Combine web application technology with native operating system capabilities.
  * *Progressive Web Applications (PWA)*: Web applications that provide additional app-like functionality.
### 4. Web application distribution
* There are two main categories.
  * *Open-source applications:* Source code is available for inspection and modification under the applicable license.
  * Examples:
    * [WordPress](https://wordpress.com/) – Website
    * [OpenCart](https://www.opencart.com/) – Website
    * [Joomla](https://www.joomla.org/) – Website
* *Proprietary (closed-source) applications:* Software developed and controlled by an organization.
  * Examples:
    * [Wix](https://www.wix.com/) – Website
    * [Shopify](https://www.shopify.com/) – Website
    * [DotNetNuke](https://www.dnnsoftware.com/) – Website
### 5. Security risks of web applications
* Web applications are attractive targets because:
  * They are accessible over the internet.
  * They may contain sensitive user information.
  * They frequently communicate with databases.
  * They have many interactive components.
  * Application updates can introduce new vulnerabilities.
* What can happen if a web application is compromised?
1. Sensitive information may be exposed.
2. User accounts may be compromised.
3. Attackers may gain unauthorized access.
4. Database information may be stolen or modified.
5. Attackers may achieve remote code execution.
6. Organizations may experience financial losses and service interruptions.
* Why penetration testing matters:
  * Penetration testing helps identify vulnerabilities before malicious attackers exploit them
* Organizations should:
  * Regularly test their applications.
  * Patch vulnerabilities.
  * Use secure coding practices.
  * Retest applications after fixes.
### 6. The front-end trinity
* One of the first things to examine during a web application penetration test is the front end.
## Web Application Layout
## Front End vs. Back End

# Front End Components
## HTML
## Cascading Style SHeets (CSS)
## JavaScript

# Front End Vulnerabilities
## [Sensitive Data Exposure](https://owasp.org/www-project-top-ten/2017/A3_2017-Sensitive_Data_Exposure)
* Refers to availability of sensitive data in clear-text to the end-user
  * Usually found in *source code* of the web page or page source
### Prevent
* Frontend source code should only contain the code necessary to run all of the web applications functions
  * No extra code or comments
  * Important ton review code that will be visible to end-users through the page source or run it through tools to check for exposed information
 * Classify data types within the source code and apply controls on what can or cannot be exposed to the client-side
 * Developers should review client-side code to ensure that no unnecessary comments or hidden links are left behind

## [HTML Injection](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/11-Client-side_Testing/03-Testing_for_HTML_Injection)
* Occurs when unfiltered user input is displayed on page
## Cross-Site Scripting (XSS)
## Cross-Site Request Forgery (CSRF)

# Back End Components
## Back End Servers
## Web Servers
## Databases
## Developmental Frameworks & APIs

# Back End Vulnerabilities
## Common Web Vulneraboolties
## Public Vulnerabilities
