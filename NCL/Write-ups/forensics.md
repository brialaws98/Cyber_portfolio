# Challenge #1 
***Name:*** Fly High(Easy)
* Revcovered an Liber8tion device
* Analyze the files
### Tool(s) Used
* stat ~ Display file or file system status
* strings ~ Display printable strings in [file(s)]
* binwalk
* file
### Steps taken / Commands used
1. ```strings original_binary```
   {
   * Noticed the word "apt being used
   * Grepped "apt"(```...| grep "apt"```)
   }
2. ```stat -c $s [FileName]```
   {
   * I wanted to find to total size, in byte,of the file
   * ```$s``` ~ Total file nodes in file system
   * ```-c``` ~ Use the specified FORMAT instead of the default; output a newline after each use of FORMAT
   }
4. binwalk [FileName]{}
6. file -b mime-type [FileName]{}
### Solutions
1. The name of the original binary: ```apt```
2. The total size, in bytes, of the original binary?: ```18752```
3. The total size, in bytes, of the modified binary?: ```97869```
4. The file extension of the hidden file(Modified binary)?: ```jpeg```
### What I am stuck on and steps that I have taken so far (And possible refelction)
* Q5 is tricky
* Below is the steps that I took and what I was able to accomplish:
     1. When I used the ```binwalk modified_binary``` command, I was able to discover the hidden JPEG file
     2. Had to use the ```binwalk --dd=".*" modified_binary``` command to export the hidden file
     3. I discovered the ***_modified_binary.extracted*** file and use ```cd``` to enter that dierctory
     4. Once inside that directory, I was able to view the files with the ```ls``` command and discovered 3 different files
     5. Renamed the ***4940*** with ```mv 4940 hidden_file``` command
     6. The hidden file contains a message on an image "No flag here?....Or is there?" 

