# Challenge #1
***Name:*** Rockyou (Easy)
### Steps taken
1. Download the [Rockyou file](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt)
2. Create a notebook with the hash text(```hash.txt```)
3. Enter the ```find``` command to find the directory for ```rockyou.txt```
4. Found where the rockyou.txt was located
5. Entered ```hashcat -m 0 -a 0 hash.txt ~/rockyou.txt``` to discover the hashes
   * ```hash.txt``` : the file location + file name that has the hashes ```hashcat``` will try to crack
   * ```-m 0``` : uses hash-mode 0 — indicates the hashes are MD5 hashes
   * ```-a 0``` : use a dictionary attack (this requires a wordlist to be specified)
   * ```/usr/share/wordlists/rockyou.txt``` : the file location +name of the wordlist
### Solution
1. 68a96446a5afb4ab69a2d15091771e39 : ```emilybffl```
2. ec5f0b1826389df8622133014e88afde : ```ryjd1982```
3. 32e5f63b189b78dccf0b97ac41f0d228 : ```joybird1```
4. 2233287f476ba63323e60addca1f6b64 : ```kirkles```
5. 6539bbb84fe2de2628fc5e4f2a31f23a : ```ddmack```
#
# Challenge #2
***Name:*** Mask (Medium)
### Steps taken
1. Edited the ```hash.txt```
2. Entered ```hashcat -m 0 -a 3 ./hash.txt 'SKY-HQNT-?d?d?d?d'```
   * ```-m 0```: Uses hash-mode ```0``` - indicates the hashes are MD5 hashes
   * ```-a 3```: Indicates a brute-force/mask attack
   * ```'SKY-HQNT-?d?d?d?d```: ```hashcat``` should attempt passwords with a different digit in place of each ```?d```
### Solution
1. 71b816fe0b7b763d889ecc227eab400a : ```SKY-HQNT-8765```
2. 674291170dffcf620bda2a604a6820ea : ```SKY-HQNT-7659```
3. 06f03267f31077d2c4b5c728472070ae : ```SKY-HQNT-6598```
4. d866f4b3b34b598375149fb7661113ab : ```SKY-HQNT-5981```
5. d9053951a8d1c15254b46ec9fc974a6b :```SKY-HQNT-9816```
