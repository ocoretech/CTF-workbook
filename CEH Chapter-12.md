## **CEH Chapter - 12**


### **Page 7**

* Network-Based Intrusion Detection Systems (NIDSS) 

    *  Assigns a threat level to each risk after receiving the data packets.



### **Page 13**

* IDS alert Types

    * True Positive: Attack + Alert

        Triggers an alarm and causes the IDS to react as if an attack is in progress. 
    

    *  False Positive: No attack + Alert

        Triggers an alarm when no attack is in progress.

    
    * False Negative: Attack + No Alert

        IDS fails to react to an attack because of no alert.



### **Page 15**

Evading IDS

* IDS evasion is the process of modifying attacks to fool the IDS/IPS into interpreting that the traffic is legitimate and thus prevent the IDS from triggering an alert.


### **Page 23**

![Fragmentation-Attack](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Fragmentation-Attack.png)



### **Page 25**

Session Splicing

* If attackers are aware of a delay in packet reassembly at the IDS, they can add delays between packet transmissions to bypass the reassembly.


### **Page 34**

* Hardware Firewall

    * Advantages:

        * Hardware firewalls initiate faster responses and enable more traffic.

        * It enables better management and allows the firewall to shut down, move, or be reconfigured without much interference.

    
    * Disadvantages:

        * More expensive than a software firewall. 

        * Difficult to implement and configure. 

        * Consumes more space and involves cabling.


* Software Firewalls

    * Advantages:

        * Less expensive than hardware firewalls. 

        * Ideal for personal or home use.

        * Easier to configure and reconfigure.
    

    * Disadvantages:

        * Consumes system resources. 

        * Difficult to uninstall.

        * Not appropriate for environments requiring faster response times.



### **Page 42**

![Circuit-Level-Gateway-Firewall](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Circuit-Level-Gateway-Firewall.png)


                    Circuit Level Gateway Firewall Example



### **Page 45**

Statfull Multilayer Inspection Firewall


* This type of firewall can remember the packets that passed through it earlier and make decisions about future packets accordingly.




### **Page 47**

Virtual Private Network (VPN)


* Advantages:

    * Hides all the traffic that flows over it, ensures encryption, and protects data from snooping.

    * Provides remote access for protocols while avoiding attackers.


* Disadvantages:

    * User will be vulnerable to an attack on the destination network because VPN runs on a public network.



### **Page 49**

Firewall Evasion Techniques

Source routing 

* to avoid the route of the firewall
* Source routing is categorized into two approaches: loose source routing and strict source routing. 
* In loose source routing, the sender specifies one or more stages that the packet must go through, in strict source routing, the sender specifies the exact route the packet must go through. 


### **After Page 58**

IDS Evasion Countermeasures

* Shut down switch ports associated with known attack hosts.
* Perform an in-depth analysis of ambiguous network traffic for all possible threats. 
* Use TCP FIN or Reset (RST) packet to terminate malicious TCP sessions.
* Train users to identify attack patterns and regularly update/patch all the systems and network devices.
* Deploy IDS after a thorough analysis of the network topology
* Harden the security of all communication devices such as modems and routers.
* Ensure that snort rules are perfectly configured to avoid DoS attacks using snort false positives.


Firewall Evasion Countermeasures

* Set the firewall rule set to deny all traffic and enable only the services required. 
* If possible, create a unique user ID to run the firewall services instead of running the services using the administrator or root ID.
* Monitor firewall logs at regular intervals.
* Run regular risk queries to identify vulnerable firewall rules.
* Monitor user access to firewalls and control who can modify the firewall configuration. 
* Use application identification to block malicious applications from any outbound connections.






