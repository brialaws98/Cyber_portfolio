#
# Challenge #2
***Name:*** Compressed Analysis(Medium)
### Wireshark filters
1. IP address of host receiving POST message from the attackers? <br>
     ```http.request.method == POST``` <br>
     ***Result:*** 172.26.0.5
2. Layer 2 protocol abused allowing hackers to intercept traffic? <br>
     ```arp``` <br>
   ***Result:*** arp
3. IP address of the compromised host? <br>
     ```# The same as the POST command``` <br>
     * Look on the "Internet Protocol Version 4 line
       ***Result:*** 172.26.0.3```
4. What IP address did the compromised host impersonate? <br>
     ```arp```
    * Labeled as "Duplicated IP address detected..."
      ***Result:*** 172.26.0.4, 172.26.0.5
