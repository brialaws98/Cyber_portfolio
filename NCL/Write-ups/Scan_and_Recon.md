# Challenge #1
***Name***: Dig it up!(Easy)
* Liber8tion spun up new services
* Explore the DNS records
### Commands
1. ```dig @resolver lige8.cityinthe.cloud NS``` {Scan for FQDN of the authoratative name server}
2. ```dig @resolver liber8.cityinthe.cloud SOA``` {Scan for the Start Of Authority serial number}
3. ```dig @resolver liber8.cityinthe.cloud CAA``` {Scan for the domain name for the Certificate Authority}
4. ```dig @resolver -x 10.0.0.20``` {Scan for full hostname IP address}
5. ```dig @resolver _minecraft._tcp.liber8.cityinthe.cloud SRV``` {Scan for server running the minecraft server}

### Solutions
1. The FQDN of the authoritative name server is under the ***Answer Section***: ```ns1.liber8.cityinthe.cloud```
2. The ***Start Of Authority*** serial number is ```2025011701```
3. The domain name of the ***Certificate Authority*** that is allowed to issue TLS certificates is ```\letsencrypt.org'''
4. The full hostname (FQDN) that maps to the IP address is ```web.liber8.cityinthe.cloud```
5. The full hostname(FQDN) of the server running microsoft server is ```mc2.liber8.cityinthe.cloud```
#
# Challenge #2
***Name:*** Scandiego (Medium)
### Tool(s) Used
* [Nmap](https://www.kali.org/tools/nmap/) ~ Used for network discovery, security auditing, and inventorying devices

### Command {Function/description}
1. ```nmap -sC -sV manager```
   {
   * ```-sC```
   * ```-sV```
   }
4. ```nmap -sU --min-rate=1000 -p3000-65535 <target>```{}
5. ```nmap -sU -p5353 --script=dns-service-discovery <target-ip>```
{
* ***Will help to answer questions 5-7***
}
### Solutions
1. The language is set to use(*language_region.encoding*)?: ```en_AU.UTF-8```
2. The city it claims to be running in? ```Sydney```
3. The lowest UDP port that is running?: ```5353```
4. The ***service*** running on the lowest open UDP port?: ```mdns```
5. What name does the service group for group of this service advertise on the network: ```Globetrotter```
6. Two service types that are advertised in the service group? ```ssh, http```
7. The service is advertising a flag. What is it? ```SKY-VILE-8610```
#
