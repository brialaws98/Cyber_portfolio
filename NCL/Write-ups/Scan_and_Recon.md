# Challenge #1
***Name***: Dig it up!(Easy)
* Liber8tion spun up new services
* Explore the DNS records
### Commands
1. ```dig @resolver lige8.cityinthe.cloud NS```
2. ```dig @resolver liber8.cityinthe.cloud SOA```
3. ```dig @resolver liber8.cityinthe.cloud CAA```
4. ```dig @resolver -x 10.0.0.20```

### Solutions
1. The FQDN of the authoritative name server is under the ***Answer Section***: ```ns1.liber8.cityinthe.cloud```
2. The ***Start Of Authority*** serial number is ```2025011701```
3. The domain name of the ***Certificate Authority*** that is allowed to issue TLS certificates is ```\letsencrypt.org'''
4. The full hostname (FQDN) that maps to the IP address is ```web.liber8.cityinthe.cloud```
