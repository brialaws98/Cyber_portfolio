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
###### The security team has found a rather strange file exiting the network,we're not sure if it's containing any sensitive information. Help us identify what's in it.
### Tools used
* [Computer Fundamentals for Cybersecurity](https://trove.cyberskyline.com/computer-fundamentals-for-cybersecurity/data)
* [binwalk](https://github.com/ReFirmLabs/binwalk) ~ Designed to identify files through reading magic bytes and a number of other file Carving techniques
* [tar archive](https://en.wikipedia.org/wiki/Tar_(computing))
### Introduction
* Files are a sequence of bytes
  * Each byte can store a value between 0-255
* There are two primary ways that programs attempt to determine which format is being used by a file:
  * ***file extension*** *(eg: .png, .mp3, .pdf)* ~ Can be found directly in the name of the file
    1. Often used to determine the file format since checking the filenames is more efficient than opening every file in a folder to look for the magic bytes
  * ***file signature*** *(magic byte)* ~ Unique sequence of bytes values that are directly within the contents of the file itself, usually at the beginning of the file
    1. If modified of changed, can trick some programs into thinking that they cannot open the file
    2. Simple rename can solve this
### Questions
1. This file initially looks like something green, what's the file format of the green file? : ```png```
   * ```file``` ~ Used to view the file's information
     1. This program stores a list of magic bytes and their corresponding file formats
     2. Searched the file provided for those magic bytes and display any that match
2. How many files can be extracted from the binary blob? : ```6```
   * ```mv [old filename] [new filename]``` ~ Change the name of a file
     1. Used to change the *file extension*
    * ```binwalk [filenames]``` ~ Used to identify other files that may be packaged into this file
3. What is the flag? : ```SKY-RWCI-4291```
   * ```binwalk --extract -dd "png:png" [filenames]```
     1. ```-e, --extract``` ~ Automatically extract known file types
     2. ```-D, -dd=<type[:ext[:cmd]]>``` ~ Extract <type> signatures (regular expressions), give the files an extension of <ext>, and execute <cmd>
  * ```ls``` to see a new directory with the name ```_green_file.extracted``` created
  * When looking at CAB (```file CAB```), I see that this is a *tar* archive 
  * After using the ```tar xvf [file]``` command, I was able to see that there are two more files that I can explore to find the answer
   

# Magic Byte (Medium)

# Doctor (Medium)

# The Book (Hard)
