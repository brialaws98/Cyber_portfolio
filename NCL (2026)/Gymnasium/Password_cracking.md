# Rockyou (Easy)
###### Our analysts have obtained password dumps storing hacker passwords. After obtaining a few plaintext passwords, it appears that they overlap with the passwords from the Rockyou breach
### Tools used
* [hashcat](https://hashcat.net/wiki/doku.php?id=hashcat)
* [Rockyou wordlist](https://github.com/josuamarcelc/common-password-list/tree/main/rockyou.txt)
* [Hash analyzer](https://www.tunnelsup.com/hash-analyzer/) ~ Used to identify hash types
* [Identify Hash types](https://hashes.com/en/tools/hash_identifier)
* [crackstation](https://crackstation.net/) ~ Used to crack specific type of hashes
### Introduction
* Make sure ```hashcat``` is installed in Linux
* Download and extract the ```rockyou.txt``` file
  1. tar -xvzf [zipped file]
     * ```-x```: Extracts all files
     * ```-v```: Enable verbose output to see the files be extracted
     * ```-z```: Decomposs using ``gzip``
     * ```-f```: Specify the filenames of the archive
* I ended up using a website called ***crack station*** to decode the passwords
### Questions 
1. 68a96446a5afb4ab69a2d15091771e39 : ```emilybffl```
2. ec5f0b1826389df8622133014e88afde : ```ryjd1982```
3. 32e5f63b189b78dccf0b97ac41f0d228 : ```joybird1```
4. 2233287f476ba63323e60addca1f6b64 : ```kirkles```
5. 6539bbb84fe2de2628fc5e4f2a31f23a : ```ddmack```

# Mask (Medium)
###### Our analysts have obtained passwords dumps storing hacker passwords. After obtaining a few plaintext passwords, it appears that they are all in the format: ``SKY-HQNT-``` followed by 4 digits. Can you crack them?
### Tools used
* [Mask attack](https://hashcat.net/wiki/doku.php?id=mask_attack)
### Introduction
* Added all hashes to a document called ``hash.txt``
* Used an online tool to identify the hashes
* Tool time to learn a little more about *mask attacks*
* Used ```hashcat -m 0 -a 3 ./hash.txt 'SKY-HQNT-?d?d?d?d'```
  1. ```-m``` : Uses hash-mode ``0`` - indicates the hashes are MD5 hashes
  2. ```-a 3``` : Indicates a brute-force/mask attack
  3. ```'SKY-HQNT-?d?d?d?d'``` : ```hashcat``` should attempt passwords with a different digit in the place of each ``?d``
### Questions
1. 71b816fe0b7b763d889ecc227eab400a : ```-8765```
2. 674291170dffcf620bda2a604a6820ea : ```-7659```
3. 06f03267f31077d2c4b5c728472070ae : ```-6598```
4. d866f4b3b34b598375149fb7661113ab : ```-5981```
5. d9053951a8d1c15254b46ec9fc974a6b : ```-9816```

# Pokemon (Medium)

# Law & Order (Hard)

# Kali Linux (Hard)
