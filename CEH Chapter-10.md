## **CEH Chapter - 10**

### **Page 4**

Examples for types of DoS attacks: 

* Flooding a service (e.g., Internet Relay Chat (IRC)) with more events than it can handle
* Crashing a TCP/IP stack by sending corrupt packets
* Crashing a service by interacting with it in an unexpected manner 
* Hanging a system by causing it to go into an infinite loop


![DOS-Attack](DOS-Attack-1.png)

                                Flow of DOS Attack



### **Page 5**

Botnets

* A relatively small botnet of 1,000 bots has a combined bandwidth larger than the bandwidth of most corporate systems.


![Botnet-based-DDOS-Attack](Botnet-based-DDOS-Attack.png)


                        Botnet-based-DDOS-Attack



### **Page 7**

UDP Flood Attack

![UDP-Flood-Attack](UDP-Flood-Attack.png)


                                UDP Flood Attack


ICMP Flood Attack or Ping flood

* These packets signal the victim's system to reply, and the large traffic saturates the bandwidth of the victim's network connection causing it to stop responding to legitimate TCP/IP requests. 

![ICMP-Flood-Attack](ICMP-Flood-Attack.png)

                                ICMP Flood Attack




### **Page 9**

SYN Flood Attack

![SYN-Flood-Attack](SYN-Flood-Attack.png)

                                SYN Flood Attack



### **Page 11**

Fragmentation Attack

* Moreover, the content in the packet fragments will be randomized by the attacker, which make the process consume more resources.


### **Page 15**

* Countermeasures

    * Turn off the Character Generator Protocol (CHARGEN) service to stop this attack method.

    * Download the latest updates and patches for servers .


![DRDOS-Attack](DRDOS-Attack.png)

                                    DRDOS Attack



### **Page 17**

Mobile tools

* LOIC

    * Allows attacker to perform DDos attack on the target.
    * Can perform TCP, UDP flood attacks.


* AnDOSid

    * Allows the attacker to simulate a DoS and DDos attacks on a web server through mobile phones.




### **Page 20**

DOS Prevention Strategies

* Control the rate of outbound or inbound traffic of a network interface controller.
* Use TCP intercept feature  in routers to protect TCP servers from a TCP SYN-flooding attack.


### **Page 21** 

* Packet Traceback

    * Similar to reverse engineering 
    * helps in identifying the true source of attack and taking necessary steps to block further attacks.


* Event Log Analysis

    * helps in identifying the source of DoS traffic
    *  allows network administrators to recognize the type of DDoS attack or a combination of attacks used

