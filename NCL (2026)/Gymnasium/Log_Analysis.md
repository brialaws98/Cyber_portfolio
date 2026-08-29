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
1. Find the hostname of the ssh server that was compromised
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
1. How many total attempts were made in this log? : ```6063```
   * ```cat [filenames] | wc -l``` ~ Get the line count of the log
2. How many unique usernames appear in this log? : ```1679```
   * ```cat [filename] | cut -f # | sort | uniq | wc -l```
     1. Extract the third field (with the usernames) of the log (``cut -f 3``)
     2. Sort the usernames (``sort``)
     3. Get a line count of the number of unique usernames (``uniq | wc -l``)
3.  What is the username with the most login attempts : ```ntory```
   * ```cat [filenames] | cut -f# | sort | unique -c | sort -n```
     1. Extract the third field (with the usernames) of the log (```cut -f 3```)
     2. Sort the usernames (```sort```)
     3. Get a frequency count of each unique username (```uniq -c```)
     4. Sort the unique usernames by frequency (```sort -n```)
4.  How many attempts were made for the username with the most login attempts? : ```124```
5.  What is the date with the most login attempts? : ```2011-03-23```
   * ```cat [filenames] | cut -f # | cut -d " " -f # | sort | uniq -c | sort -n```
     1. Extract the first field (with the date+time) of the log (```cut -f 1```)
     2. Extract just the date (```-d " "```)
     3. Get a frequency count of each unique date (```uniq -c```)
     4. Sort the unique date by frequency (```sort -n```)
6.  What is the username that had logins from the most unique IP addresses : ```wlfla0190```
   * ```cat [filenames] | cut -f #, #| sort | uniq | cut -f # | sort | uniq -c | sort -n```
     1. Extract the second field (with the IP address) and third field (with the username) of the log (```cut -f 2,3```)
     2. Sort the IP/username pairs (```sort```)
     4. Get the unique IP/username pairs (```uniq```)
     5. Extract just the usernames from each pair (```cut -f 2```)
     6. Sort the usernames (```sort```)
     7. Get a frequency count of how many unique pairs each username has (```uniq -c```)
     8. Sort by frequency (```sort -n```)

# VSFTPD (Easy)
###### Analyze the VSFTPD log file that we obtained
### Introduction
* ***VSFTPD***(*Very Secure FTP Daemon*) is used on Linux servers to create a secure way to users to upload and download files
* This server is implemented for different purposes
  * The logs created form its use convey similar information like:
    1. Timestamps
    2. process IDs (PID)
    3. Event types
    4. Client IP addresses
    5. Usernames
* ```awk``` has additional capabilities involving formatting and conditional logic
### Questions
1. What IP address did "ftpuser" first log in from? : ```10.0.0.123```
   * ```cat vsftpd.log | grep ftpuser | head```
     1. Search for the first entry that include "ftpuser" (```grep```)
2. What is the first directory that ftpuser created? : ```TreeSizeFree```
   * ```cat vsftpd.log | grep ftpuser| grep -i mkdir | head```
3. What is the last directory that ftpuser created? : ```110D300S```
   * Same command as the question #2 but changed head to tail
4. What file extension was the most used by ftpuser? : ```jpg```
   * ```cat vsftpd.log | grep ftpuser | grep 'OK UPLOAD' | awk -F ',' '{print $2 }' | awk -F "." '{print $#}' | sort | uniq -c | sort```
     1. Search for successful file upload (```grep```)
     2. Extract the file extension for those uploads (```awk -F ',' '{print $2}' | awk -F "." {print $2}'```)
     3. Get frequency count for each unique file extension
5. What is the username of the other user in this log? : ```jimmy```
   * ```cat vsftpd.log | awk '{print $#}' | sort | uniq```
6. What IP address did this other user log in from? : ```10.0.0.214```
   * ```cat vsftpd.log | grep jimmy```
     1. Search for any entries that include jimmy
7. How many total bytes did this other user upload? : ```105750628```
   * ```cat vsftpd.log | grep jimmy | grep 'OK UPLOAD' | awk -F ',' '{print  $3 }' | awk '{s+=$1} END {print s}'```
     1. Search for successful file upload entries from jimmy
     2. Extract the number of bytes transferred (```awk -F ',' {print $3}'```)
     3. Sum the bytes (```awk s+=$1} END {print s}```)
8. How many total bytes did ftpuser upload? : ```13980839165```
   * Same as question #7 but replaced *jimmy* with *ftpuser*
9. How many total bytes did ftpuser download? ```6008032```
    * Same as question #7 but changed *UPLOAD* to *DOWNLOAD* for ftpuser
10. Identify the IP address of the suspicious login (the login with no subsequent activity) : ```10.3.0.6```
    * ```cat vsftpd.log | grep 'OK LOGIN' | awk -F '"' '{print $2 }' | sort | uniq```
      1. Go through each IP address to look for suspicious activity


# Nginx (Medium)

# History (Medium)

# Squid (Hard)

# Payments (Hard)

# Custom File Format (Hard)
