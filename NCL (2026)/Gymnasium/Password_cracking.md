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
* If I used the ```hashcat [filenames] -m 0 -a 0 rockyou.txt```, these are what the flags mean
  1. ```-m 0```: Use hash mode ``0`` - indicates the hashes are MD5 hashes
  2. ```-a 0```: Use a dictionary attack (this requires a wordlist to be specified)
  3. ```rockyou.txt```: The file location+name of the wordlist
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
###### Our analysts have obtained password dumps storing hacker passwords. After obtaining a few plaintext passwords,  it appears that they are based on Pokemon.
### Introduction
* Questions can be solved using [hashcat](https://hashcat.net/wiki/doku.php?id=dictionary_attack) with a [wordlist of Pokemon](https://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_National_Pok%C3%A9dex_number)
### Guide
* Add all hashes for the challenge to a text document and save it as ``hash.txt``
* Need to create a wordlist
  * Find a wordlist of all of the Pokemon on one page or even look at the developer tools on the webpage
* To create a wordlist from a website, can use ``curl``
  ``curl`` is a general-purpose tool for making HTTP requests
```
curl -s -L \
  -H "User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36" \
  -H "Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8" \
  "https://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_National_Pok%C3%A9dex_number" \
  | grep -oP 'title="\K[^(]+(?=\s\(Pok)' \
  | sort -u > pokemon.txt
```
* Here is a breakdown to the command:
  * The ``s`` flag downloaded the files
  * ``?Limit=2000``: Set the limit to 2000 forces the server to return every single  Pokemon in a single response
  * ``grep -oP "name"=\K[^"]+'``
    * ``-o`` Prints only the specific text that matches the pattern
    * ``P`` Enables advanced regex
    * ``\K``(Keep) is a powerful regex meaning *"drop everything matched up to this point from the final output"* and ensures ``"name:"`` is discarded, leaving only what comes next
    * ``[^"]+`` Matches one or more characters that are not double quotes
### Solution
```hashcat [filenames] -m 0 -a 0 [wordlist]```
* ``-m 0``: uses hash-mode ``0`` - indicates the hashes are MD5 hashes
* ``-a 0``: use a dictionary attack (this requires a wordlist to be specified)
### Questions 
1. a532443f3e04a9e00295a8cd2a75e080 : ```golduck```
2. 54c10b9736b70e75c6e505f340b6e2f1 :  ```basculin```
3. b8a24794813a47521b4be55747e0665a :  ```celebi```
4. 83b020b0a7b3c353e1c11b1647b53cda :  ```rotom```
5. 999cae1e22fe69d89d6f56e3050f18cb :  ```goldeen```

# Law & Order (Hard)

# Kali Linux (Hard)
