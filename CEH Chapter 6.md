## **CEH Chapter 6**

### **Page 16**

Password Cracking Countermeasures

* Do not use cleartext protocols and protocols with weak encryption.

* Avoid storing passwords in an unsecured location. 

* Make passwords hard to guess by requiring 8-12 alphanumeric characters consisting of a combination of uppercase and lowercase letters, numbers, and symbols.


### **Page 18**

* Security Accounts Manager (SAM) Database

    * The lock does not release until the system throws a blue screen exception, or the OS has shut down. 


### **Page 19**

* NTLM includes three methods of challenge–response authentication 
    
LM, NTLMv1, and NTLMv2, all of which use the same technique for authentication. The only difference between them is the level of encryption.


### **Page 30**

![Kerberos](Kerberos.png)


             Kerberos Authentication Process



### **Page 32**

* Both ticket-granting service (TGS) tickets and ticket-granting tickets (TGT) can be stolen and reused by adversaries.


### **Page 34**

Password-cracking tools allow you to reset unknown or lost Windows local administrator, domain administrator, and other user account passwords. 

In the case of forgotten passwords, it even allows users instant access to their locked computer without reinstalling Windows.


### **Page 40**

* Password recovery tools allow attackers to break complex passwords, recover strong encryption keys, and unlock several documents.

* Passware Kit Forensic

    * Analyzes live memory image and hibernation file and extracts encryption keys for hard disks, logins for Windows & Mac accounts, and passwords for files and websites, all in a single streamlined process.



### **Page 41**

CHNTPW

* It works offline, that is, you have to shutdown your computer and boot off a CD or USB disk to do the password reset.


### **Page 42**

* **pwdump7:** 

    pwdump7 is an application that dumps the password hashes from NT’s SAM database. pwdump extracts LM and NTLM password hashes of local user accounts from the Security Account Manager (SAM) database.


* **mimikatz:** 

    Mimikatz is an open-source application that allows users to view and save authentication credentials such as Kerberos tickets.

    Attackers commonly use Mimikatz to steal credentials and escalate privileges because in most cases, endpoint protection software and antivirus systems will not detect or delete the attack.


* **Powershell Empire:**

    PowerShell Empire is a post-exploitation framework written in PowerShell. It is designed to aid penetration testers in the post-exploitation phase of security testing.

    The framework provides a set of tools and modules that allow operators to maintain control over compromised systems.


* **DSInternals**: 

    DsInternals is a set of PowerShell modules that provides a collection of tools for working with Active Directory environments.


* **Ntdsxtract:**

    Ntdsxtract is a tool designed for extracting data from the Active Directory database file called ntds.dit. 
    
    The ntds.dit file is a crucial component of the Active Directory (AD) on Windows systems, and it stores information about users, groups, and other objects in the directory.





### **Page 49**

**Privilege Escalation:**

 *  The attacker performs a privilege escalation attack that takes advantage of design flaws, programming errors, bugs, and configuration oversights in the OS to gain administrative access to the network and its associated applications. 

 * These privileges allow the attacker to view critical/sensitive information or install malicious programs.



### **Page 51**

* Abusing Accessibility Features
    
    * Accessibility features are activated using key combinations even before a user logs into a system. An attacker can manipulate these features to obtain backdoor access without logging into the system. 


### **Page 52**

* In the pivoting technique, only the systems accessible through the compromised systems are exploited.


### **Page 60**

* Implement multi-factor authentication and authorization.

* Continuously monitor file-system permissions using auditing tools.


### **Page 61**

User Account Control (UAC)



### **Page 75**

* **Runtime Execution Path Profiling:**

    * The runtime execution path profiling technique compares runtime execution path profiling of all system processes and executable files. The rootkit adds a new code near to a routine’s execution path to destabilize it.


* **Analyzing Memory Dumps**:

    * In memory dump analysis, RAM of the suspected system is dumped and analyzed to detect the rootkit in the system.



### **Page 79**

* The first data stream stores the security descriptor for the file to be stored, such as permissions, and the second stores the data within a file.

![NTFS Datastreams](<NTFS Datastreams.png>)

                    NTFS Datastreams



### **Page 82**

![Steganography message](<Steganography message.png>)

            Hiding message using steganography 



### **Page 83**

*  It is an attack on information security in which the attacker, referred to here as a steganalyst, tries to detect the hidden messages embedded in images, text, audio, and video carrier mediums using steganography.

Challenges of Steganalysis

* Suspect information stream may or may not have encoded hidden data.

* Efficient and accurate detection of hidden content within digital images is difficult.

* The message might have been encrypted before being inserted into a file or signal. 

* Some of the suspect signals or files may have irrelevant data or noise encoded into them.



### **Page 84**

* **Chi-square attack** 
    
    * The chi-square method is based on probability analysis to test whether a given stego-object and the original data are the same or not.


* **Distinguishing statistical attack**

    * In the distinguishing statistical method, the steganalyst or attacker analyzes the embedded algorithm used to detect distinguishing statistical changes, along with the length of the embedded data.


* **Blind classifier attack**

    * In the blind classifier method, a blind detector is fed with the original or unmodified data to learn the appearance of the original data from multiple perspectives.



### **Page 89**

* Event logs for Windows are stored in C:\Windows\System32\winevt\Logs

Windows word was missing


### **Page 93**

* **CCleaner:**

    CCleaner is a system optimization, privacy, and cleaning tool. It allows attackers to remove unused files and cleans traces of Internet browsing details from the target PC.
