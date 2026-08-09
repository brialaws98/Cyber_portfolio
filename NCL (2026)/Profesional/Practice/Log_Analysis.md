# Login (Easy)
Need to Analyze a custom application login event to understand the behavior.
### Questions
1. How many total login attempts were made in this log? : ```6063``` <br>
      {Used ```cat login.log |wc -l``` to get a an accurate count of each line}
2. How many unique usernames appear in this log? : ```1879``` <br>
{```cat login.log | cut -f 1 | cut -d " " -f 1 | sort | uniq -c | sort -n``` <br>
  * ```cut -f 3``` ~ Extract the third field of the log
  * ```sort```~ Used to sort the ussernames
  * ```uniq```~ Used to get unique usernames
}
3. What is the username with the most login attempts? : ```ntory``` <br>
{```cat login.log | cut -f 1 | cut -d " " -f 1 | sort | uniq -c | sort -n``` <br>
  * ```uniq -c``` ~ Used to get a frequency count of each unique username
  * ```sort -n``` Used to sort the unique usernames by frequency}
4. How many attempts were made for the user with the most login attempts? : ```124```
5. What is the date with the most login attempts? : ```2011-03-23``` <br>
{```cat login.log | cut -f 1 | cut -d " " -f 1 | sort | uniq -c | sort -n``` <br>
* ```cut -d" " f 1```
}
6. What is the username that had logins from the most unique IP addresses? : ```wlfla0190``` <br>
{```cat login.log | cut -f 2,3 | sort | uniq | cut -f 2 | sort | uniq -c | sort -n```}

# VSFTPD (Easy)
Analyze a VSFTPD log fie that was obtained
### Queations
1. What IP address did "ftpuser" first log in from? :```10.0.0.123``` <br>
   {```cat vsftpd.log | grep ftpuser | head```
   * ```grep``` ~ Used to grab a specific entries
   * ```head``` ~ Used to grab only the first few labs
   }
2. What is the first directory that ftpuser created? : ```TreeeSizeFree``` <br>
   {```cat vsftpd.log | grep ftpuser | grep -i mkdir | head -n 1``` ~ Used to find the account that was created running the ```mkdir``` command}
3. What is the last directory that ftpuser created? : ```110D300S``` <br>
{```cat vsftpd.log | grep ftpuser | grep -i mkdir | tail -n 1```
4. What file extension was the most used by ftpuser? : ```jpg``` <br> {```cat vsftpd.log | grep ftpuser | grep 'OK UPLOAD' | awk -F ',' '{print $2 }' | awk -F "." '{print $2}' | sort | uniq -c | sort```}
5. What is the username of the other user in the log? : ```jpg``` <br>
{```cat vsftpd.log | awk '{print $8}' | sort | uniq```
      * ```awk``` ~ Used to filter all log entries for a specific field
}
6. What IP address did the other user log in from? : ```10.0.0.214``` <br> {```cat vsftpd.log | grep jimmy```}
7. How many total bytes did the other user upload? : ```105750628``` <br> {```cat vsftpd.log | grep jimmy | grep 'OK UPLOAD' | awk -F ',' '{print  $3 }' | awk '{s+=$1} END {print s}'```}
8. How many total bytes did ftpuser upload? : ```13980839165```
11. How many total bytes did ftpuser download? : ```6008032```
12. Identify the  IP address of the suspicious login (the login with no subsequent activity): ```10.3.0.6```

# History (Medium)
# Nginx (Medium)
# Squid (Hard)
# Payments (Hard)
# Custom File Format (Hard)
