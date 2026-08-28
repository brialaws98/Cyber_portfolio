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
3. Which user was targeted in the attack?
   * Discovered that ```harvey``` was the the target
4. From which IP address was the attacker able to successfully log in?
   * By changing Failed to Accept, I was able to find the IP address with the successful login (```30.167.206.91```)
# Login (Easy)
###### Analyze a custom total login attempts to help understand the user behavior
### Steps taken and Solutions
###### Introduction
* Will be analyzing a custom application log format that uses tab-delineated columns
  * This format is well-suited for the ``cut`` tool to extract specific columns from the log
* Use ``ls`` to list the files in the directory
* Use ``head`` or ``tail`` to just see the first or last few lines
  * ```head [filenames]```
* Using ```wc``` command along with the ```-l``` flag will count the lines in the output
* Using ```cut``` command with the ```-f#``` flag to extract a certain column
* The ```sort``` command will sort the usernames alphabetically
* The ```uniq``` command will list unique entries
* The ```-c``` flag will show the number of times an entry occurs in the output
* The ```-n``` flag will sort a list numerically 
###### Questions
1. How many total attempts were made in this log?
2. How many unique usernames appear in this log?
3.  What is the username with the most login attempts
4.  How many attempts were made for the username with the most login attempts?
5.  What is the date with the most login attempts?
6.  What is the username that had logins from the most unique IP addresses?

# VSFTPD (Easy)

# Nginx (Medium)

# History (Medium)

# Squid (Hard)

# Payments (Hard)

# Custom File Format (Hard)
