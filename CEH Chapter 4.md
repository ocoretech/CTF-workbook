## **CEH Chapter 4**

### **Page 9**

* Linux user enumeration provides a list of users along with details such as the username, host name, and start date and time of each session.

* rusers:  rusers displays a list of users who are logged in to remote machines.

* rwho:  rwho displays a list of users who are logged in to hosts on the local network.

* finger:  finger displays information about system users .


### **Page 13**

* NetBIOS is considered first for enumeration because it extracts a large amount of sensitive information about the target network.

Attackers use NetBIOS enumeration to obtain: 
* The list of computers that belong to a domain 
* The list of shares on the individual hosts in a network
* Policies and passwords

### **Page 15**

![SNMP](<SNMP Enumeration.png>)

                    Working of SNMP


### **page 18**

LDAP

* It uses DNS for quick lookups and the fast resolution of queries.


### **Page 19**

* LDAP Account Manager


### **Page 21**

* PRTG Network Monitor: PRTG monitors all systems, devices, traffic, and applications of IT infrastructure by using various technologies such as SNMP, WMI, and SSH.


### **Page 22**

NFS Enumeration

* NFS enumeration enables attackers to identify the exported directories, list of clients connected to the NFS server along with their IP addresses.

NFS Enumeration Through Tools

* SuperEnum: SuperEnum includes a script that performs the basic enumeration of any open port.


### **Page 27**

* VoIP uses Internet infrastructure to establish connections for voice calls; data are also transmitted on the same network.

* VoIP is vulnerable to TCP/IP attack vectors.

* Session Initiation Protocol (SIP) is one of the protocols used by VoIP for performing voice calls, video calls, etc.


 **Svmap:** Svmap is an open-source scanner that identifies SIP devices and PBX servers on a target network.


Attackers use Svmap to perform the following: 

* Identify SIP devices and PBX servers on default and non-default ports 

* Scan large ranges of networks

*  Scan one host on different ports for an SIP service on that host or multiple hosts on multiple ports.

* Ring all the phones on a network simultaneously using the INVITE method.



### **Page 28**

* Telnet is a network terminal protocol that allows users to access remote computers or servers over the Internet.

* Telnet enumeration enables attackers to exploit identified vulnerabilities and perform brute-force attacks to gain unauthorized access to the target and launch further attacks.

* If the Telnet port is found open, attackers can access shared information, including the hardware and software information of the target. 


### **Page 34**

* By using this cached record, the attacker can determine the sites recently visited by the user. This information can further reveal important information such as the name of the owner of the DNS server, its service provider, etc.


**Non-recursive Method:**

In this method, to snoop on a DNS server, attackers send a non-recursive query by setting the Recursion Desired (RD) bit in the query header to zero.


**Recursive Method:**

In this method, to snoop on the DNS server, attackers send a recursive query by setting the +recurse option instead of the +norecurse option.



### **Page 38**

Zone Transfer Countermeasures

* Ensure that private hostnames are not referenced to IP addresses within the DNS zone files of publicly accessible DNS servers.


### **Page 40**

* DNSRecon is a command-line tool used for DNS reconnaissance, enumeration, and information gathering.

DNSRecon can be used to perform the following tasks:

1. Enumeration of subdomains
2. Retrieval of DNS records
3. Brute-forcing of subdomains
4. Zone transfers
5. Reverse DNS lookups


### **Page 45**

* Block access to TCP/UDP port 161.

* Do not install the management and monitoring Windows component unless required.

* Encrypt or authenticate using IPsec.

* Upgrade to SNMP3, which encrypts passwords and messages.

* Configure access-control lists (ACLs) for all SNMP connections to allow only legitimate users to access SNMP devices.

* Change the default password and periodically change the current password. 

* Identify all the SNMP devices with read/write permissions and provide read-only permissions to specific devices that do not require read/write permissions.


### **Page 46**

* By default, LDAP traffic is transmitted unsecured; therefore, use Secure Sockets Layer (SSL) or STARTTLS technology to encrypt the traffic.

* Select a username different from the email address and enable account lockout. 

* Block users from accessing certain Active Directories entities by changing the permissions on those objects/attributes.

* Deploy canary accounts, which resemble real accounts, to mislead attackers. 

* Use NT LAN Manager (NTLM), Kerberos, or any basic authentication mechanism to limit access to legitimate users.


### **Page 47**

* Implement proper permissions (read/write must be restricted to specific users) in exported file systems.

* Implement firewall rules to block NFS port 2049.

* Ensure proper configuration of files such as /etc/smb.conf, /etc/exports, and etc/hosts.allow to protect the data stored in the server.

* Keep the root_squash option in the /etc/exports file turned ON so that no requests made as root on the client are trusted.

* Implement NFS tunneling through SSH to encrypt the NFS traffic over the network.

* Log the requests to access the system files on the NFS server. 


### **Page 48**

* Ignore email messages to unknown recipients.

* Exclude sensitive information on mail servers and local hosts in mail responses.

* Disable the open relay feature.

* Limit the number of accepted connections from a source to prevent brute-force attacks.

* Disable the EXPN, VRFY, and RCPT TO commands or restrict them to authentic users.

* Do not share internal IP/host information or mail relay system information.


### **Page 49**

* Implement proper permissions for Common sharing services or other unused services which may provide entry points for attackers to evade network security. 

* Disable SMB protocols by disabling the properties Client for Microsoft Networks and File and Printer Sharing for Microsoft Networks in Network and Dial-up Connections. 

* Ensure that Windows Firewall or similar endpoint protection systems are enabled on the system.

* Install the latest security patches for Windows and third-party software. 

* Implement a proper authentication mechanism with a strong password policy.

* Employ highly robust and secure monitoring systems such as global threat sensors for highly sensitive and top-secret data.


### **Page 50**

* Implement strong passwords or a certification-based authentication policy. 

* Ensure that the unrestricted uploading of files on the FTP server is not allowed.

* Disable anonymous FTP accounts. If this is not possible, monitor anonymous FTP accounts regularly.

* Configure access controls on authenticated FTP accounts using access-control lists (ACLs).

* Do not run regular public services such as mail or the web on a single FTP server.

* Restrict access by IP or domain name to the FTP server.


### **Page 51**

* Ensure that the resolver can be accessed only by the hosts inside the network.

* Audit DNS zones to identify vulnerabilities in domains and subdomains and address DNS-related issues.

* Update and patch nameservers with the most recent versions of software such as BIND and Microsoft DNS.

* Restrict DNS zone transfers to specific slave nameserver IP addresses because the zone transfer may include a master copy of the primary server’s database.

* Use an isolated and dedicated server for DNS services.
