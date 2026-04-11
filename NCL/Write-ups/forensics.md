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

