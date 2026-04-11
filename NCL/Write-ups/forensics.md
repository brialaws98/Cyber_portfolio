# Challenge #1 
***Name:*** Fly High(Easy)
* Revcovered an Liber8tion device
* Analyze the files
### Tool(s) Used
* stat ~ Display file or file system status
* strings ~ Display printable strings in [file(s)]
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
4. 
### Solutions
1. The name of the original binary: ```apt```
2. 
