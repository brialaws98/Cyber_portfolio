# SSH (Easy)
###### Analyze an ssh log file
### Tools used 
* [How SSH works](https://bytebytego.com/guides/how-does-ssh-work/)
### Steps taken and Solution
###### Introduction
* ***SSH***(*Secure Shell Protocol*) ~ A service that allows a device to provide remote terminal access
* The message field will often include warnings or errors
* The event details field will include when sessions initiate or authentications attempts      
###### Questions
1. Find the hostname of the ssh server that was compromised.
   * ```cat [filenames] | head``` ~ Used to find the first few lines of the log
2. Find the IP addresses that attacked the server
   *```cat auth.log | grep Failed | head``` ~ Grab the first few servers with "Failed" attempts
   1. ```169.139.243.218```
   2. ```56.13.188.38```
   3. ```30.167.206.91```
4. Which user was targeted in the attack?
   * Discovered that ```harvey``` was the the target
6. From which IP address was the attacker able to successfully log in?
   * By changing Failed to Accept, I was able to find the IP address with the successful login (```30.167.206.91```)
# Login (Easy)

# VSFTPD (Easy)

# Nginx (Medium)

# History (Medium)

# Squid (Hard)

# Payments (Hard)

# Custom File Format (Hard)
