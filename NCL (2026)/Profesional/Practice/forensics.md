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
### Tools
* Downdloaded a PDF file that has redacted information on it
* [Metadata2go](https://www.metadata2go.com/) ~ Used to view information on documentations and images
* [Adobe PDF editor](https://acrobat.adobe.com/blob/JTdCJTIyc291cmNlJTIyJTNBJTIyc2lnbmVkLXVyaSUyMiUyQyUyMml0ZW1OYW1lJTIyJTNBJTIyYXBpLnBkZiUyMiUyQyUyMml0ZW1UeXBlJTIyJTNBJTIyYXBwbGljYXRpb24lMkZwZGYlMjIlMkMlMjJpdGVtSWQlMjIlM0ElMjJjNmI3YjMwYi0zZWJlLTRjOGMtOTcwYS1kY2E5ZTg3YzYzNzAlMjIlN0Q?redirectTime=1783708329199&x_api_client_id=unity&x_api_client_location=add_comment&x_api_user_experience=variant1_us&viewer%21megaVerb=group-edit&locale=en-US&asset_count=1&pdfNowAssetUri=https%3A%2F%2Fpdfnow.adobe.io%2F1784313134%2Fassets%2Furn%3Aaaid%3Asc%3AUS%3Ae72d2924-4a9f-407a-ad22-013da1b7f31e) ~ Used to edit the PDF file 
### Questions
1. What is the name of the program that exported this PDF file? : ```Photoshop```
2. What PDF version if this file? : ```1.7```
3. What software was used to redact hte file and insert a watermark? : ```pdftron```
4. What is the flag? ```SKY-PDRD-2390```

# File Carving (Medium)
The security team found a strange file exiting the network. Help identify what's in the file.
### Tools
* Downloaded a file
* [Computer Fundamentals for Cybersecurity](https://trove.cyberskyline.com/ff55c18374c84109b32b95252309185d)
* The [mv](https://www.geeksforgeeks.org/linux-unix/mv-command-linux-examples/) command to change a file name
* The [binwalk](https://linuxcommandlibrary.com/man/binwalk) command to find additional hidden files
* [tar archive](https://en.wikipedia.org/wiki/Tar_(computing))
### Questions
1. This file initially look like something green, what's the file format of this green file? : ```png``` <br>
[Use the ```file --fileName--``` to view general information about the file]
2. How many files can be extracted from the binary blob? ```6``` <br>
[There are 6 files within the original png file. This is seen using the ```biwalk command]
3. What is the hidden flag in the file? : ```SKY-RWCI-4291``` <br>
[
* Use ```--extract``` to get additional information
* Change directory to the extractedd file
* Use ```cat``` command in to view the flag
]
   
# Magic Bytes (Medium)
# Doctor (Medium)
# The Book (Hard)
