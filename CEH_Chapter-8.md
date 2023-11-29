## **CEH Chapter 8**

### **Page 8**

![Passive Sniffing](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Passive%20Sniffing.png)

                                Passive Sniffing


### **Page 9**

Active Sniffing

The following is a list of different active sniffing techniques:
1. MAC flooding: Technique used to compromise the security of network switches that connect network segments or devices.
2. DNS poisoning
3. ARP poisoning
4. DHCP attacks
5. Switch port stealing: The attacker floods the switch with forged gratuitous ARP packets with the target MAC address as the source and his/her own MAC address as the destination.
6. Spoofing attack



### **Page 23**

Display Filters

Some of the display filters in Wireshark are listed below:

* Display Filtering by Protocol 
    Example: Type the protocol in the filter box: arp, http, tcp, udp, dns, ip

* Monitoring the Specific Ports 
    
    * tcp.port==23 
    
    * ip.addr==192.168.1.100 machine 
    
      ip.addr==192.168.1.100 && tcp.port==23


* Filtering by Multiple IP Addresses

    * ip.addr == 10.0.0.4 or ip.addr == 10.0.0.5


* Filtering by IP Address 

    * ip.addr == 10.0.0.4


* Other Filters
    * ip.dst == 10.0.1.50 && frame.pkt_len > 400

    * ip.addr == 10.0.1.12 && icmp && frame.number > 15 && frame.number < 30

    * ip.src==205.153.63.30 or ip.dst==205.153.63.30


### **Page 27**

1. Wicap

    * This tool is a mobile network packet sniffer for ROOT ARM droids. It works on rooted Android mobile devices. 
    
    * Captures packets for various types of connections, e.g. 3G,4G,Wi-Fi.


        ![Wicap](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Wicap.png)

                    Wicap


2. FaceNiff

    * Android app that can sniff and intercept web session profiles over a Wi-Fi connection to a mobile. This app works on rooted Android devices.
    
    *  Wi-Fi connection should be over open, WEP, WPA-PSK, or WPA2-PSK networks.


3. Packet Capture

    * It is a powerful debugging tool, especially when developing an app. 

    * Captures network packets and record them, perform SSL decryption.


### **Page 31**

![MAC Flooding Attack](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/MAC%20Flooding%20Attack.png)

                                MAC Flooding Attack



### **Page 34**

DHCP Starvation

* Tools

    * yersinia
        * Start UI using yersinia -G then click on "Start attack"
    * DHCPstarv
    * mitm6 
    * DHCPwn 
    * DHCPig 
    

![Working of DHCP](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Working%20of%20DHCP.png)

                             Working of DHCP




### **Page 38**


DNS Poisoning Attack

* DNS Poisoning Techniques

1. Intranet DNS Spoofing:

    * In this technique, the attacker’s system must be connected to the local area network (LAN) and be able to sniff packets.
    * It works well against switches with ARP Poison Routing.


* Flow:

    *  The attacker poisons the router by running arpspoof/dnsspoof to redirect DNS requests of clients to the attacker’s machine.
    * Client sends a DNS request the poisoned router which sends the DNS request packet to the attacker’s machine.
    * The attacker sends a fake DNS response that redirects the client to a fake website set up by the attacker.
    


2. Internet DNS Spoofing:

    * This is an MITM attack in which the attacker changes the primary DNS entries of the victim’s computer.
    *  Attackers can perform DNS spoofing attacks on a single victim or on multiple victims anywhere in the world.
    * To perform this attack, the attacker sets up a rogue DNS server with a static IP address. 



3. DNS Cache Poisoning:

    * DNS cache poisoning refers to altering or adding forged DNS records into the DNS resolver cache so that a DNS query is redirected to a malicious site.



### **Page 44-45**

Slide 45 should be before slide 44



### **Page 55**

* Also known as STP manipulation attack, STP attack or STP root role attack and Spanning Tree Protocol.

* The root bridge is selected with the help of Bridge Protocol Data Units (BPDUs). BPDUs each have an identification number known as a BID or ID.


![STP Attack](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/STP%20Attack.png)

                STP Attack

Maybe include this image instead of the image included in the slides.



### **Page 59**

* The process of obtaining the MAC address using ARP :

    * Source machine generates an ARP request packet containing the source MAC address, and sends it to the switch.

    * On receiving switch reads the MAC address of the source and searches for this address in its CAM table.

    * If entry not found in table, switch add MAC address and it's port to CAM table. Broadcasts the ARP request packet into the network.

    * Each device receives ARP request packet and compares the destination IP address in the packet with its own IP address.

    * Only the system with an IP address that matches the destination IP address replies with an ARP reply packet.

    * The ARP reply message is then read by the switch, which adds the entry to its MAC table and forwards the message to the destination machine, i.e., the machine that sent the ARP request.



### **Page 63**

* Use an ARP Spoofing tool e.g.

    * Habu
        * Habu is a hacking toolkit that provides various commands to perform, ARP poisoning and sniffing, Certificate cloning, TCP analysis, Web technology identification.



### **Page 66**

* ARP spoofing detection and prevention
    * The implementation of cryptographic protocols such as HTTP Secure (HTTPS), Secure Shell (SSH), Transport Layer Security (TLS), and various other networking cryptographic protocols prevents ARP spoofing attacks.


