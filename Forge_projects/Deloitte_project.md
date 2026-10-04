# Cyber
###### Work with Cyber team to deliver Deloitte expertise to clients
-------------
###### Identify the security issue that led to a leak of private company information
### Task: *Cyberseucirty*
###### What you'll learn
* How to support a client in a cyber security breach
* How to  read web activity logs
###### What you'll do
* Help a client determine the source of a data breach
* Answer questions to identify suspicious user activity
### Background Information
* A major publication has revealed sensitive private information about Daikibo Industrials, our client
* A production problem has caused this assembly lines to stop
  * Threatens the smooth operation of supply chains relying on Daikibo's products
* The client suspects the security of their new status board may have been breached
### The Task
* You will be joining the cyber security team. Your job is to:
1. Determine if the alleged breach could have happened from an attacker on the internet directly (I.e. no Daikibo's VPN)
2. Inspect a *```web_request,log```* file (listing only data from a period when the alleged attack has to have happened):
  * Try to spot suspicious requests
  * If you've identified such requests make sure to write down the ID of the user (it's part of the requests)
* Here is how the *```web_request.log```* file is structured:
  * There is a sequence of blocks of text divided by empty lines
  * Each block represents the activity of a unique IP address (no 2 blocks have the same IP)
  * The block starts with IP address followed by a table of the requests made to Daikibo's telemetry dashboard (the dashboard lives in Daikibo's intranet) by the device with this IP address, sorted by time
  * The IP addresses are from the internal Dikibo network and are static
  * 1 block can represent 1 or multiple browsing sessions
  * Sessions made on different dates require new logs
  * There is **no continuous pulling/pushing of data** between client and server
    * The users need to refresh the page to get the latest data
### Quiz lesson
1. The attacker has no direct access to the status dashboard
2. The user with the ID mdB7yD2dp1BFZPontHBQ1Z is has the most suspicious activity
   * Starts off with regular login -> browsing of the dashboard
   * It then turns into a regular, once-per-hour automated check of the statuses in all 4 factories with no page resources being loaded with an obviously non-human punctuality
