# Version Control (Easy)
An emplloyee's computers was compromised.Now we need to find out what information the hackers got.
### Tools 
* Downloaded a git zip file with the information
* Used the ```unzip``` command to reveal contents of the file
    * We are then able to access the file and ```cd``` to see wat is inside with the ```ls -a``` command
* [Resource to learn Git](https://docs.github.com/en/get-started/git-basics/set-up-git)
* [Git Wikipedia](https://en.wikipedia.org/wiki/Git)
### Questions and steps
1. What is the email address of the employee who was commpromised? : ```gpeterson@mpd.hacknet.cityinthe.cloud``` <br>
[Used the ```git log``` command to view information about each log0]
2. Each employee is assigned a flag. What is the flag that was compromised? : ```SKY-LRHX-4910``` <br>
[Use ```git show --SHA1 hash--``` command to inspect the chsnges of the commits]
3. Greg thinks that he may have had additional account credentials that were compromised. What's the name of the service provider for that other copromised account? : ```Facebook``` <br>
[
* Use the ```git branch``` command to view other available branches
* Can switch to those branches by using the ```git checkout --branch--``` command 
]
5. What was the password on that compromised account? : ```waffles85```
  
# PDF Examination (Easy)
# File Carving (Medium
# Magic Bytes (Medium)
# Doctor (Medium)
# The Book (Hard)
