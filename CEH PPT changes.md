## **Chapter 1**

### **Page 5**
Elements of Information security

Five major elements: Confidentiality, Integrity, Availability, Authenticity, and Non-repudiation. 



### **Page 8**

Vulnerabilities can be classified into six broad categories: Hardware, Software, Network, Personnel, Physical Site and Organizational.

An Image to show how attacks occur because of vulnerabilities.

![Alt text](Vulnerability.png)


### **Page 9**

Exploiting software or hardware vulnerabilities to gain remote access to the target system.

Backend note: exploitation triggers the adversary’s malicious code to exploit a vulnerability in the operating system, application, or server on a target system.

### **Page 10**

Example: 
One of the most common attacks is to send emails with an attached .pdf file containing a malicious payload that will install a backdoor.

Backend Note:
The victim downloads the file and double-clicks to open it, which triggers the code in the background. Note that a payload can remain dormant to be executed later.

And a payload can hide within a non-executable file such as an image and trigger later. Most people will be less reluctant to open .png than .zip or .exe files.
You can even generate payloads with a graphical interface, for example, with the Metasploit framework.

### **Page 11**

Zero-Day attack: Zero-Day attack is an attack that exploits the computer vulnerability before software engineer releases a patch.

Backend Notes:
A zero-day attack is the use of a zero-day exploit to cause damage to or steal data from a system affected by a vulnerability.

A zero-day vulnerability is a software vulnerability discovered by attackers before the vendor has become aware of it. Because the vendors are unaware, no patch exists for zero-day vulnerabilities, making attacks likely to succeed.

### **Page 14**

Daisy chaining: 
Daisy chaining attack involves gaining access to a network and /or computer and then using the same information to gain access to multiple networks and computers that contains desirable information.

### **Page 17**

Example:
A bot can also appear as a warning saying that your computer will get a virus if you do not click on the associated link. Clicking the link subsequently infects your computer with a virus.


### **Page 18**

CIA Triad:

Ideally, when all three standards (Confidentiality, Integrity and Availability) have been met, the security profile of the organization is stronger and better equipped to handle threat incidents.

Confidentiality: example: those who work with an organization’s finances should be able to access the spreadsheets, bank accounts, and other information related to the flow of money. However, the vast majority of other employees may not be granted access. To ensure these policies are followed, strict restrictions have to be in place to limit who can see what.

Integrity: example: if your company provides information about senior managers on your website, this information needs to have integrity. If it is inaccurate, those visiting the website for information may feel your organization is not trustworthy

Availability: example: a natural disaster like a flood may prevent users from getting to the office, which can interrupt the availability of their workstations and other devices that provide business-critical information


### **Page 21**

Integrity:
Measures to maintain data integrity may include a checksum (a number produced by a mathematical function to verify that a given block of data is not changed) and access control (which ensures that only authorized people can update, add, or delete data).


### **Page 25**

The use of a triangle is because an increase or decrease in any one of the factors will have an impact on the presence of the other two.

Functionality: defined as the purpose that something is designed or expected to fulfil.

Security: defined as referring to all the measures that are taken to protect a system, application or a device as well as ensuring that only people with permission to access them are able to.


### **Page 28**

Security threats and attacks are actions or events that can compromise 
the confidentiality, integrity, or availability of data and systems.


### **Page 29**
Threat: 
A Threat is a possible security risk that might exploit the vulnerability of a system or asset. The origin of the threat may be accidental or environmental, human negligence, or human failure.

### **Page 32**
Attack: 
An Attack by definition is an intended action to cause damage to system/asset.

### **Page 37**

Shrink Wrap Code: 
Shrink wrap code attacks refer to security breaches that exploit vulnerabilities in third-party software components, also known as shrink wrap code, that are integrated into applications. Shrink wrap code attacks can be highly effective because they target widely used software components that are trusted by developers and end-users alike, making them an attractive target for attackers.

Common Shrink Wrap Code attacks are: 
Man in the middle attack, Cross-Site Scripting(XSS) attack, Code Injection attack.

### **Page 38**

examples: Botnets, insider attacks, viruses and worms etc.


### **Page 39**

Advanced Persistent Threat: 
An Advanced Persistent Threat (APT) uses continuous and sophisticated hacking techniques to gain access to a system and remain inside for a prolonged period of time, with potentially destructive consequences.

Maybe put the examples as a backend note?

Five stages of an Advanced Persisitent Attack:

Stage One: Gain Access
Stage Two: Establish a Foothold
Stage Three: Deepen Access
Stage Four: Move Laterally
Stage Five: Look, Learn, and Remain


### **Page 40**

Virus: A virus is a malicious executable code attached to another executable file that can be harmless or can modify or delete data.
Eg: ILOVEYOU virus spreads through email attachments

Worms: Worms are similar to a virus but it does not modify the program. It replicates itself more and more to cause slow down the computer system.
Eg: The WannaCry ransomware worm in 2000 exploits the Windows Server Message Block (SMBv1)

See also [Difference between Virus and Worm](https://www.geeksforgeeks.org/difference-between-worms-and-virus/)


### **Page 41**
 
Insider Attacks are carried out by people who are familiar with the computer network system and hold authorised access to all the information. 

### **Page 43**

Phishing: It is an unethical way to trick the user or victim to click on harmful sites. The attacker crafts the harmful site in such a way that the victim feels it to be an authentic site, thus falling prey to it.

Eg: An attackers sends you a hyperlink redirecting you to Youtube, most people believe it’s YouTube just by looking at the red icon. So, thinking of YouTube as a secure platform, the users click on the extension without being suspicious about it and it redirects them to a malicious website.

Types of Phishing attack:
1. Spear Phishing: this type of attacks are not initiated by any random hacker, but these attacks are initiated by someone who seeks information related to financial gain or some important information.

2. Clone Phishing: This attack is actually based on copying the email messages that were sent from a trusted source. Now the hackers alter the information by adding a link that redirects the user to a malicious or fake website.

backend note: Now, this is sent to a large number of users and the person who initiated it watches who clicks on the attachment that was sent as a mail. This spreads through the contacts of the user who has clicked on the attachment.

3. Catphishing: It is a type of social engineering attack that plays with the emotions of a person and exploits them to gain money and information. They target them through dating sites.

4. Voice Phishing: This type of attack is sometimes referred to as vishing. Someone who is using the method of vishing, use modern caller id spoofing to convince the victim that the call is from a trusted source.

Image:
![Phishing](Phishing.png)


### **Page 44**
Information Warfare image, shift to page 44
![Information Warfare](<Information Warfare.png>)


### **Page 45**

* Radio electronic techniques attack the physical means of sending information, whereas cryptographic techniques use bits and bytes to disrupt the means of sending information.

Cyber Warfare Backend note: It is the broadest of all information warfare. It includes information terrorism, semantic attacks (similar to Hacker warfare, but instead of harming a system, it takes over the system while maintaining the perception that it is operating correctly), and simula-warfare (simulated war, for example, acquiring weapons for mere demonstration rather than actual use).


### **Page 50**

Continual/Adaptive Security Strategy:
1. Protection

    **Backend notes** (This includes a set of prior countermeasures taken towards eliminating all the possible vulnerabilities on the network. It includes security measures such as security policies, physical security, host security, firewall, and IDS.)

2. Detection 

    **Backend notes** (Detection involves assessing the network for abnormalities such as attacks, damages, unauthorized access attempts, and modifications, and identifying their locations in the network. It includes the regular monitoring of network traffic using network monitoring and packet sniffing tools.)

3. Responding

    **Backend notes** (Responding to incidents involves actions such as identifying incidents, finding their root causes, and planning a possible course of actions for addressing them. It includes incident response, investigation, containment, impact mitigation, and eradication steps for addressing the incidents.)

4. Prediction

    **Backend notes** (Prediction involves the identification of potential attacks, targets, and methods prior to materialization to a viable attack. Prediction includes actions such as conducting risk and vulnerability assessment, performing attack surface analysis, consuming threat intelligence data to predict future threats on the organization.)


### **Page 55**

* Defense-in-depth helps to prevent direct attacks against an information system and its data because a break in one layer only leads the attacker to the next layer.

![Defence in Depth](<Defense in Depth.png>)

### **Page 60**

Risk Level: Risk level is an assessment of the resulted impact on the network.

### **Page 62**
Risk Assessment: The risk assessment determines the kind of risks present, their likelihood and severity, and the priorities and plans for risk control.

### **Page 64**

2. Assessment 
* Risk assessment is an iterative process
* Assigns priorities for risk mitigation and implementation plans 
* Determines the quantitative and qualitative value of risk.   

3. Treatment 
* purpose of this step is to identify treatments for the risks that fall outside the department’s risk tolerance.

4. Tracking and review
* Performing regular inspections of policies and standards, as well as regularly reviewing them, helps to identify the opportunities for improvement.

### **Page 66**

* Business impact analysis (BIA)
Predicts the consequences of disruption of a business function
Process and gathers information needed to develop recovery strategies
Often includes metrics.
Should be used identifying the potential consequences of a change, or estimating
what needs to be modified to accomplish a change
* Business change impact analysis
Allows you to identify consequences of a change
E.g. a new feature can cause resource load and crash the server

### **Page 68**

From Assest value, shift the info to the next page.
Also don't know if we want this slide of Annual Loss Expectancy.

### **Page 70**

* Threat modeling is a risk assessment approach for analyzing the security of an application by capturing, organizing, and analyzing all the information that affects it. 

* The threat model consists of three major building blocks: understanding the adversary’s perspective, characterizing the security of the system, and determining threats.

    e.g. configure in better way, improve source code, enable encryption or ditch the
    application.


### **Page 82**

SOC Image: ![SOC](SOC.png)


### **Page 83**

Four phases of incident response:

1. Preparation
2. Detection and analysis
3. Containment, Eradication and Recovery
4. Post-incident activity

### **Page 86**

* Network Security Controls are used to ensure the confidentiality, integrity, and availability of the network services. These security controls are either technical or administrative safeguards implemented to minimize the security risk.


* Network security controls include: 

1. Access Control
2. Identification
3. Authentication
4. Authorization
5. Accounting
6. Cryptography
7. Security Policy

### **Page 91**
Change the Heading to Common Security Zones.


### **Page 93**

POLICY TYPES FOR RISK TOLERANCE

**1. Promiscuous:**
* Only good when you have bunch of highly trained & well-informed people with proven
track record working in a team because otherwise policies would slow them down
* No restrictions on system resources.


**2. Permissive:**
* When it knows something is malicious, it'll be blocked

### **Page 94**

**3. Prudent:**
* Provides maximum amount of security
* Allows only safe stuff
* Very restrictive

**4. Paranoid:**
* Something of such high importance, not worth to take smallest of risks, e.g. government data regarding to citizens.
* In Linux firewall there's a command called panic that's equivalent to this, Drops all traffic


### **Page 113**
Turn the difference into a table.


### **Page 122**
Set a strong password, atleast 8 characters in length, should contain bothe upper and lowercase alphabetic characters and should have atleast one numerical character and a special character (#,@,%,$)

### **Page 127**

Risks of Operating Without Data Backup:
hardware issues
ransomware
software failures
loss of power
accidental user error

### **Page 146**

![Threat Intelligence Lifecycle](<Threat Intelligence Lifecycle.png>)

            Threat Intelligence Lifecycle


### **Page 147**

4. Identify threats
* The administrator should identify threats relevant to the control scenario and context using the information obtained in the application overview and decompose application steps.
* Should bring members of the development and test teams together to identify potential threats.

5. Identify Vulnerabilities
* Should identify any weaknesses related to the threats found using the vulnerability categories and fix them beforehand to keep intruders away.

### **Page 148**

* An understanding of cyber kill chain methodology helps security professionals to leverage security controls at different stages of an attack and helps them to prevent the attack before it succeeds.

![Kill Chain](<Cyber Kill Chain.png>)

                Cyber Kill Chain Methodology

### **Page 153**

* Understanding the tactics of an attacker helps to predict and detect evolving threats in the early stages.

* Understanding the techniques used by attackers helps to identify vulnerabilities and implement defensive measures in advance.

* Analyzing the procedures used by the attackers helps to identify what the attacker is looking for within the target organization’s infrastructure.

### **Page 155**

Some of the behaviors of an adversary that can be used to enhance the detection capabilities of security devices: 

1. Internal Reconnaissance
2. Use of Powershell
3. Unspecified Proxy Activities
4. Use of Command-Line Interface
5. HTTP User Agent
6. Command and Control Server
7. Use of DNS Tunneling
8. Use of DNS Tunneling
9. Data Staging


### **Page 156**

* Monitoring IoCs also helps security teams enhance the security controls and policies of the organization to detect and block suspicious traffic.

1. **Email Indicators:** 
* Attackers usually prefer email services to send malicious data to the target organization.
* E.g. sender's email address, subject, attachment, links.

2. **Network Indiacators:**
*  Useful for command and control, malware delivery, and identifying details about the operating system.
* E.g. URLs, domain names, IP addresses, unusual DNS requests.

3. **Host-based Indicators:**
* Host-based indicators are found by performing an analysis of the infected system within the organizational network.
* E.g. filenames, file hashes, registry keys, DDLs, mutex

4. **Behavioral Indiacators:**
* Behavioral IoCs are used to identify specific behavior related to malicious activities.
* E.g. memory code injection, remote command execution, document execution
PowerShell script.

### **Page 157**

* The Diamond Model offers a framework for identifying the clusters of events that are correlated on any of the systems in an organization.
* Controls the vital atomic element occurring in any intrusion activity, known as Diamond event.
* Advanced and efficient mitigation approaches can be developed, and analytic efficiency can be increased.

The Diamond event consists of four basic features:
1. Adversary: Who was behind the attack
2. Victim: Where the attack was performed
3. Capability: How the attack was performed
4. Infrastructure: What the adversary used to reach the victim

![Diamond Model](<Diamond Model.png>)

                    Diamond Model


### **Page 161 & 162**

Change bullets to numbers for Headings and, numbers to bullets for points.

1. Build and maintain a secure network
* Install and maintain a firewall
* Do not use vendor-supplied defaults for any security parameters (e.g. passwords)
2. Protect cardholder data
* Protect stored data
* Storing cardholder data is discouraged, but if stored it must be encrypted or hashed.
* Never store sensitive data on the magnetic stripe or chip including PIN and CAV2 /CVC2 / CVV2 / CID.
* Encrypt transmission of cardholder data across public networks
3. Maintain a vulnerability management program
* Use and regularly update anti-virus software
* Develop and maintain secure systems and applications
4. Implement strong access control measures
* Restrict access to cardholder data by business need-to-know
* Assign a unique ID to each person with computer access
* Restrict physical access to cardholder data
* Store media back-ups in a secure location, preferably off site.
* Review and confirm that back-up media is secure at least annually.
5. Regularly monitor and test networks
* Track and monitor all access to network resources and cardholder data
* Regularly test security systems and processes
* Test presence of wireless access points on a quarterly basis
* Network vulnerability scans at least quarterly and after any significant
change
* Penetration testing at least once a year and after any significant change
6. Maintain an information security policy
* Maintain a policy that addresses information security


### **Page 163**

* It is a series of mutually supporting information security standards that can be combined to provide a globally recognised framework.

### **Page 165**

* ISO 27002 provides guidelines, general principles and control mechanisms for implementing, maintaining and improving information security management in an organization.

### **Page 167**

Healthcare Transaction:
* Under HIPAA, if a covered entity electronically conducts one of the adopted transactions, they must use the adopted standard.

### **Page 171**
* NIST Special Publication 800-53 is part of the Special Publication 800-series that reports on the Information Technology Laboratory's (ITL) research, guidelines, and outreach efforts in information system security.

### **Page 172**

The key requirements and provisions of SOX are organized into 11 titles:

1. Public company accounting oversight board
2. Auditor independence
3. Corporate responsibility
4. Enhanced financial disclosures
5. Analyst conflicts of interest
6. Commission resources and authority
7. Studies and reports
8. Corporate and criminal fraud accountability
9. White-collar-crime penalty enhancement
10. Corporate tax returns
11. Corporate fraud accountability


### **Page 173**

* In order to implement US treaty obligations, the DMCA defines legal prohibitions against circumvention of the technological protection measures employed by copyright owners.


### **Page 174**

* The DPA is an act to make provision in connection with the Information Commissioner's functions under specific regulations relating to the information. 

The DPA protects individuals concerning the processing of personal data, in particular by:

1. Personal data to be processed lawfully
2. Conferring rights to obtain information about the processing of personal data.
3. Giving the holder of that office responsibility to monitor and enforce their provisions.


### **Page 175**

COBIT

* Control Objectives for Information and Related Technology (COBIT). It is a framework created by the Information Systems Audit and Control Association (ISACA).
* Ensures quality, control, and reliability of information systems in an organization.

### **Page 179**

* Seven principles include: 
1. Notice, 
2. Choice (can opt out) 
3. Onward transfer (only share with compliant companies) 
4. Security 
5. Data integrity 
6. Access (can be accessed and deleted by individuals) 
7. Enforcement


### **Page 180**

GDPR includes seven protection and accountability principles:

1. Lawfulness, fairness, and transparency
2. Purpose limitation
3. Data minimization
4. Accuracy
5. Storage limitation
6. Integrity and confidentiality
7. Accountability


### **Page 183-199**

No need to specify each country on a single page, instead adding following images:

![Alt text](Laws.png)
![Alt text](<Laws 1.png>)


### **Page 200**

Ethical Hacking

* Ethical hacking involves the use of hacking tools, tricks, and techniques to identify vulnerabilities and ensure system security.
* Ethical hackers report all vulnerabilities to the system and network owner for remediation, thereby increasing the security of an organization's information system.

### **Page 201**

* For some hackers, hacking is a hobby to see how many computers or networks they can compromise. Their intention can either be to gain knowledge or to poke around to do illegal things.


### **Page 205**

Insider: 
An insider is any employee (trusted person) who has access to critical assets of an organization.

Industrial Spies:
Industrial spies are individuals who perform corporate espionage by illegally spying on competitor organizations.


### **Page 208**

![Hacking Stages](<Hacking Stages.jpg>)



### **Page 209**

* Collects as much information about the target as possible to probe for weak points before actually attacking.


### **Page 210**

* Scanning involves more in-depth probing by the attacker.


### **Page 220**

* Vulnerability assessment is the process of identifying, classifying, and prioritizing security vulnerabilities in IT infrastructure.

* A comprehensive vulnerability assessment evaluates whether an IT system is exposed to known vulnerabilities, assigns severity levels to identified vulnerabilities, and recommends remediation or mitigation steps where required. 















