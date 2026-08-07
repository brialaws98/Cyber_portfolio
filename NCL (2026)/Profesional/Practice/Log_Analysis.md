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
# History (Medium)
# Nginx (Medium)
# Squid (Hard)
# Payments (Hard)
# Custom File Format (Hard)
