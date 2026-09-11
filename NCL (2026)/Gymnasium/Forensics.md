# Version Control (Easy)
###### One of our employee's computers was compromised and we saw this backup file leave the network,but we couldn't find anything other than a simple README.md file in it. Help us find out what information the hackers got.
### Tools used
* [Git](https://en.wikipedia.org/wiki/Git)
* [Getting Started with Git](https://docs.github.com/en/get-started/git-basics/set-up-git)
### Introduction
* Make sure ```unzip``` is installed onto Linux
* Unzip the Git file with a Linux command (```unzip [filename].zip```)
* ```cd git_backup``` to change to the *git_backup directory
* ```ls -a``` to show all of the files and directories 
### Questions
1. What is the email address of the employee who was compromised? : ```gpeterson@mpd.hacknet.cityinthe.cloud```
   * ```git log``` ~ See what commits have been committed into the repository and view aby users that are active
2. Each employee is assigned a flag. What is the flag that was compromised? : ```SKY-LRHX-4910```
   * ```git show [SHA1 hash]``` ~ Used to view each commit
3. Greg thinks that he may have had additional account credentials that were compromised. What's the name of the service provider for that other compromised account? : ```Facebook```
   * ```git branch``` ~ Find other branches that are available
   * ```git checkout [branch name]``` ~ Switch to other available branch
4. What was the password on that compromised account? : ```waffles85```

# File Carving (Medium)

# Magic Byte (Medium)

# Doctor (Medium)

# The Book (Hard)
