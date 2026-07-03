# Dig (Easy)
### Useful links
* [Cloudflare "What is DNS](https://www.cloudflare.com/learning/dns/what-is-dns/)
* [Cloudflare "DNS records"](https://www.cloudflare.com/learning/dns/dns-records/)
### Questions
1. What is te IPv4 address for ``fortaigan.net``? : ``104.231.72.5`` <br>
   [Used the ```dig @resolver A *** ``` to find the IPv4 address]
   
2. How many mail servers does ``fortaigan.net`` have? : ``3`` <br>
   [Use ``dig @ resolver MX ***`` to find the MX record]
3. What is the name of the mail server that takes the first priority? : ``3 maila2.fortaigan.net`` <br>
   [The LOWEST number has the highest priority]
4. what is the IPv4 address of the name server record for ***? : ``103.231.73.10`` <br>
   [
   1. ``dig @resolver NS ***``` will provide the nameserver for the domian
   2. Type in the *dig* command again but this time with the nameserver to get the answer ```ns#.***
   ]
5. What is the full name of the responsible person at ***? : ``Leo Danza`` <br>
   [
   1. Use the ``dig @resolver RP ***``` command to look up information about the ***responsible party***
   2. Use the information provided, the email in this case, to look for the full name in plain text ``dig @resolver *** TXT``
   ]
6. What is the text flag found in the DNS record? : ``SKY-PZUV-5091`` <br>
   [Use the ``dig @resolver TXT ***`` to see any contexts in the TXT record]
7. What is the priority number given to the SIP service usign the TCP protocol? : ``0`` <br>
   [Use the ``dig @resolver SRV ***``` to find information about the service]
8. What is the IPv4 address of the machine that's running the SIP service? :  ``103.231.74.3`` <br>
   [Use the hostname that was found usig the ``_sip._tcp`` to find the IPv4 address of the machine running the SIP service ``dig @resolver ***``]

### Lessons Learned
* SIP service
     * ***SIP (Session Initiation Protocol)*** handles the signaling part of voice, video and other messaging sessions that are needed
     * Has ability to route calls using domain names
     * devices may need help locating the correct servers
     * published usign specific service labels that have particular formatting
     * ```_sip._tcp``` can be used to find information about the service
     * After finding the hostname using ```_sip._tcp``` you can use the hostname fo then find the IPv4 address
# NMAP (Easy)

# Git (Easy)

# Net Track (Medium)

# Metadata (Hard)
