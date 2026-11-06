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

## [Cross-Site Scripting (XSS)](https://owasp.org/www-community/attacks/xss/)
* Attacks by injecting *JavaScript* code to be executed on the client-side
  * Once execute code on victim's machine, can potentially gain access to victim's account or even their machine
* There are three main types of XSS:

| Type | Description |
| :--- | :--- |
| Reflected XSS | Occurs when user input is displayed on the page after processing (e.g., search result or error message |
| Stored XSS | Occurs when user output is stored in the backend database and then displayed upon retrieval (e.g., posts or comments |
| DOM XSS | Occurs when input is directly shown in the browser and is written to an HTML DOM object (e.g., vulnerable username or page title)

## [Cross-Site Request Forgery (CSRF)](https://owasp.org/www-community/attacks/csrf)
* Attacks may utilize XSS vulnerabilities to perform certain queries and API calls on a Web application that the victim is currently authenticated to
  * Would allow attackers to perform actions as the authenticated user
  * May utilize other vulnerabilities to perform same functions
* Can be leveraged to attack admins and gain access to their accounts
### Prevention
* Important to filter and sanitize user input on the frontend before it reaches the backend
* Two main controls must be applied when accepting user input:

| Type | Description |
|:---|:---|
| Sanitization | Removing special characters and non-standard characters from user input before displaying it or storing it |
| Validation | Ensuring that submitted user matches the expected format (I.e., submitted email matched email format) |

* Important to sanitize displayed output and clear any special/non-standard characters
  * Once sanitize and/or validate user input and displayed output, should be able to prevent attacks
* Implement [Web application firewall](https://en.wikipedia.org/wiki/Web_application_firewall), which can help prevent injection attempts automatically
  * Can be potentially bypassed
* The [Cross-Site Request Forgery Prevention Cheat SHeet](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html) from OWASP discusses the attack and prevention measure in great detail

# Back End Components
## Back End Servers
* The hardware and OS on the backend that hosts all of the applications necessary to run the web application
* Fit in the [Data access layer](https://en.wikipedia.org/wiki/Data_access_layer)
### Software
* Contains 3 backend components:
  * *Web Server*
  * *Database*
  * *Development Framework*
* Many popular combinations of "stacks" for back-end servers. Some common examples include:

|Combinations | Components |
|:---|:---|
|LAMP | Linux, Apache, MySQL, PHP |
| WAMP | Windows, Apache, MySQL, PHP |
| WINS | Windows, ITS, .NET, SQL Server |
| MAMP | macOS, Apache, MySQL, PHP |
| XAMPP | Cross-Platform, Apache, MySQL, PHP/PERL |
* Can find a comprehensive list of Web Solution Stacks in this [article](https://en.wikipedia.org/wiki/Solution_stack)

### Hardware
* Contains all necessary hardwware

## [Web Servers](https://en.wikipedia.org/wiki/Web_server)
* An application that runs on the back-end serer, which handles all of the HTTP traffic from the client-side browser, routes it to the requested pages, and finally responds to the client-side browser
* Usually run on TCP [ports](https://en.wikipedia.org/wiki/Port_(computer_networking)) ``80`` or ``443``
  * Responsible for connecting end-users to various parts of the web application
### Workflow
 * The following are some of the most common [HTTP response code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status):

| Code | Description |
|:---|:---|
|***Successful responses*** |
| ```200 OK``` | The request has succeeded |
|***Redirection messages*** |
| ```301 Moved Permanently``` | The URL of the requested resource has been changed permanently |
| ```302 Found``` | The URL of the requested resource has been changed temporarily |
|***Client error responses***|
|```400 Bad Request``` | The server could not understand the request due to invalid syntax |
| ```401 Unauthorized``` | Unauthorized attempt to access page |
|```403 Forbidden```` | The client does not have access rights to the content |
|```404 Not Found``` | Ther server can not find the requested resource |
|```405 Request Timeout``` | This response is sent on an idle connection by some servers, even without any previous request by the client |
| ***Server error***| 
|```500 Internal Server Error``` | The server has encountered a situation it doesn't know how to handle |
| ```502 Bad Gateway``` | The server, while working as a gateway to get a response needed to handle the request, received an invalid response |
| ```504 Gateway Timeout``` | The server is acting as a gateway and cannot get a response in time |
* [JSON](https://www.w3schools.com/js/js_json_intro.asp)
* [cURL](https://en.wikipedia.org/wiki/CURL)
### [Apache](https://www.apache.org/)
* *https* is the most common web server on the internet
* Host more than 40% of all internet websites
* Usually come pre-installed in most *Linux* distributions
  * Can be installed on Windows and macOS servers
 * Usually used with *PHP* for web application development
 * Users can install a variety of Apache modules to extend its functionality and support more languages
 * An open-source project
   * Community users can access its source code to fix issues and look for vulnerabilities
 * Well-maintained and regularly patched against vulnerabilities to keep safe against exploitation
 * Commonly used by startups and smaller commpanies
 * Some big companies utilize this, including:
   * *Apple*
   * *Adobe*
   * *Baidu*
### [NGINX](https://www.nginx.com/)
* The second most common web server on the internet
  * Host roughly 30% of all internet websites
* Focuses observing concurrent web requests with relatively low memory and CPU load by utilizing an async architecture to do so
  * Makes it very reliable web server for popular web applications and top businesses worldwide
* Free and open-source
  * Gives all the same benefits like security and reliability
* Some popular websites that utilize this include:
  * *Google*
  * *Facebook*
  * *Twitter*
  * *Cisco*
  * *Intel*
  * *Netflix*
  * HackTheBox*
### [IIS (Internet Information Services)](https://en.wikipedia.org/wiki/Internet_Information_Services)
* Third most common web server on the internet
  * Host around 15% of all web sites
* Is developed and maintained by Microsoft and mainly runs on Microsoft Windows Servers
* Usually host web applications developed for the Microsoft .NET framework
* Very well optimized for Active Directory integration
  * Includes features like *Windows Auth* for authenticating users using Active Directory, allowing them to automatically sign in to Web applications
* Some popular websites that utilize this includes:
  * *Microsoft*
  * *Office365*
  * *Skype*
  * *Stack Overflow*
  * *Dell*
### Other Commonly used web servers
* [Apache Tomcat](https://tomcat.apache.org/) for ```Java``` web applications
* [NodeJS](https://nodejs.org/en/) for web applications developed using ``JavaScript``` on the back-end

## [Databases](https://en.wikipedia.org/wiki/Database)
* Web applications utilize back-end databases to store various content and information related to the web application
  * Allows web applications to easily and quickly store and retrieve data and enable dynamic content that is different for each user
* There are many different types of database, each of which fits a certain type of use
* Most developers look for certain characteristics in a database:
  * *speed* in storing and retrieving data
  * *size* when storing large amounts of data
  * *scalability* as the web application grows
  * *cost*
### [Relational](https://en.wikipedia.org/wiki/Relational_database)(SQL)
* Store data in tables, rows,and columns
  * Each table can have unique keys, which can link tables together and create relationships between tables
* Relationship between tables within a database is called a **Schema**
* Some of the most common relational databases include:

| Type | Description |
|:---|:---|
| [MySQL](https://en.wikipedia.org/wiki/MySQL) | The most commonly used database around the internet. It is an open-source database and can be completely free of charge. |
| [MSSQL](https://en.wikipedia.org/wiki/Microsoft_SQL_Server) | Microsoft's implementation of a relational database. Widely used with Windows Servers and IIS web servers | 
| [Oracle](https://en.wikipedia.org/wiki/Oracle_Database) | A very reliable database for big businesses, and is frequently updated with innovative Database solutions to make it faster and more reliable. It can be costly, even for big businesses |
| [PostgresSQL](https://en.wikipedia.org/wiki/PostgreSQL) | Another free and open-source relational database. It is designed to be easily Extensible, enabling adding advanced new features without needing a major change to the initial database design |

### [Non-relational database](https://en.wikipedia.org/wiki/NoSQL)
* Does not use tables, rows, columns, primary keys, relationships, or schemas
* Instead stores data using various storage models
* Very scalabe and flexible
* There are 4 common storage models for this:
  * Key-Value
    * Usually stores data in *JSON* or *XML*
    * Has a key for each pair, storing all of its data as its value
    * Here is an example of JSON
```
{
  "100001": {                                         <--#This is the key
    "date": "01-01-2021",                             <--#These are the values
    "content": "Welcome to this web application."
  },
  "100002": {
    "date": "02-01-2021",
    "content": "This is the first post on this web app."
  },
  "100003": {
    "date": "02-01-2021",
    "content": "Reminder: Tomorrow is the ..."
  }
}
```
  * Document-Based
    * Stores complex JSON objects
    * Each object has certain meta-data while storing the rest of the data 
  * Wide-Column
  * Graph
* Some of the most common NoSQL databases include:

| Type | Description |
|:---|:---|
| [MongoDB](https://en.wikipedia.org/wiki/MongoDB) | The most common *NoSQL database. It is free and open-source, uses the *Document-Based* model, and stores data in *JSON* objects |
| [ElasticSearch](https://en.wikipedia.org/wiki/Elasticsearch) | Another free and open-source *No SQL* database. It is optimized for storing and analyzing huge datasets. Searching for data within this database is very fast and effective |
| [Apache Cassandra](https://en.wikipedia.org/wiki/Apache_Cassandra) | Free and open-source. It is very scalable and is optimized for gracefully handling faulty values |

### Use in Web Applications
* First, the database has to installed and set up on the back-end server
  * Once up and running, the web application can start utilizing it to store and retrieve data

## Developmental Frameworks & APIs
* Some common web development frameworks include:
  * [Larvel(https://laravel.com/)(```PHP```): Usually used by startup and smaller companies, as it is powerful yet easy to develop for
  * [Express](https://expressjs.com/){```NODE.JS```): Used by *PayPal*, *Yahoo*, *Uber*, *IBM*, and *MySpace*
  * [Django](https://www.djangoproject.com/)(```Python```): Used by *Google*, *YouTube*, *Instagram*, *Mozilla*, and *Pintrest*
  * [Rails](https://rubyonrails.org/)(```Ruby```): Used by *Github*, *Hulu*, *Twitch*, *Airbnb*, and even *zTwitter* in the past
### [APIs](https://en.wikipedia.org/wiki/API)
* An important aspect is the use of Web APIs and HTTP Request parameters to connect the front-end to be able to send data back and fourth between them and carry out various functions within the web application
* Utilized for front-end to ask the back-end for a specific task with specific input
  * Back-end components process these requests, perform the necessary functions, and return a certain response to the front-end components
  * Will render the end-user's output on the client-side
### [SOAP](https://en.wikipedia.org/wiki/SOAP)(Simple Objects Access)
* Shares data through XML
* Useful for transferring structured data, or even binary data, and is often used with serialized objects
  * Useful for sharing *stateful* objects
* May be difficult to use for beginners or require long and complicated requests even for smaller queries
### [REST](https://en.wikipedia.org/wiki/Representational_state_transfer)(Representional State Transfer)
* Shares data through the URL path
  * Usually returns the output in JSON format
* Usually focus on pages that expect one type of input passed directly through the URL path
* Responses to REST API requests are usually made in JSON format
* Uses various HTTP methods to perform different actions on the web application:
  * ``GET``: request to retrieve data
  * ``POST``: request to create data (non-idempotent)
  * ``PUT``: request to create or replace existing data (idempotent)
  * ``DELETE``: request to remove data

# Back End Vulnerabilities
## Common Web Vulneraboolties
### Broken Authentication / Access Control
* Among the most common and most dangerous vulnerabilities for web applications
* ***Broken Authentication:*** Allows attackers to bypass authentication functions
  * *Example:* May allow an attacker to login without having a valid set of credentials for allow a normal user to become an administrator without having the privileges to do so
* ***Broken Access Control:*** Allow attackers to access pages and features they should not have access to
  * *Example:* A normal user gaining access to the admin panel
* An [Auth Bypass](https://www.exploit-db.com/exploits/47388) vulnerability allows user to login without having an account
### Malicious File Upload
* Way to gain control over web applications is through uploading malicious scripts
* If the web application has a file upload feature and does not properly validate the uploaded filed, may upload a malicious script, which will all to execute commands on the remote server
* There is a [Metasploit Module](https://www.rapid7.com/db/modules/exploit/multi/http/wp_responsive_thumbnail_slider_upload/) that allows to exploit this vulnerability easily

### [Command Injection](https://owasp.org/www-community/attacks/Command_Injection)
* If not properly filtered and sanitized, attackers may be able to inject another command to be executed alongside the originally intended command
  * Allows them to directly execute commands on the back-end servers and gain control over it

### [SQL Injection](https://owasp.org/www-community/attacks/SQL_Injection) (SQLi)
* May occur when the web application executed a SQL query

## Public Vulnerabilities
* These vulnerabilities are usually caused by coding mistakes made during the development of a web application's back-end components
### Public [CVE](https://en.wikipedia.org/wiki/Common_Vulnerabilities_and_Exposures)
* Many penetration tester make proof of concept exploits to test whether a certain public vulnerability can be exploited and usually make these exploits available for public use, for testing and educational purposes
~~~~~~~~~
Tips: 
* First step is to identify the version of the web application
  * Can be found in many locations, like the source code of the web application
  * For open-source web applications, can check the repository of the web application and identify where the version numbers is shown
* Then, check the same page on target web page application to confirm
~~~~~~~~~~
* Once web application is identified, can search Google for public exploits for this version of the web application
* Can utilize online exploit databases, like:
  * [Exploit](https://www.exploit-db.com/)
  * [Rapid7DB](https://www.rapid7.com/db/)
  * [Vulnerability Lab](https://www.vulnerability-lab.com/)

### [Common Vulnerability Scoring System](https://en.wikipedia.org/wiki/Common_Vulnerability_Scoring_System) (CVSS)
###### * An open-source industry standard for assessing the severity of a security vulnerability
* Often used as a standard measurement for organizations and governments that need to produce accurate and consistent severity scores for their systems' vulnerabilities
  * Helps with the prioritization of resources and the response to a given threat
* Scores are based on a formula that uses several metrics:
  * ***Base:*** produce a score ranging from 0 to 10
  * ***Temporal:*** modifies the Base
  * ***Environmental:*** Also modifies the Base
* The [National Zvulnerability Database (NVD)](https://nvd.nist.gov/) provides CVSS scores for almost all known, publicly disclosed vulnerabilities
* [Here](https://safe.security/resources/insights/cvss-v2-vs-cvss-v3/) is more information about differences between the two scoring systems
* CVSS scoring [ratings different slightly](https://safe.security/resources/insights/cvss-v2-vs-cvss-v3/) between V2 and V3
* The NVD does not facotr in Temporal and Environmental metrics
  * The former can change over time due to external events
  * The latter is a customized metric based on the potential impact of the vulnerability on a given organization
* NVD provides a [CVSS v2 calculator](https://nvd.nist.gov/vuln-metrics/cvss/v2-calculator) and a [CVSS v3 calculator](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator) that organizations can use to factor additional risk from Temporal and Environmental data unique to them
  * Calculators are very interactive and can be used to fine-tune the CVSS score to environment
* Here is a [guide](https://www.first.org/cvss/user-guide) to understand V2 and V3 and how to use the calculators to arrive at a given score

### Back-end Server Vulnerabilities
* Most critical vulnerabilities are found in web servers
  * They are publicly accessible over the TCP protocol
* Usually utilized after gaining local Access to the back-end servers or back-end network
  * May be gained through external vulnerabilities or during internal penetration testing
* Usually used to gain high privileged access on the back-end servers or the back-end network or gain control over other servers within the same network
  

