## **CEH Chapter 3**

### **Page 5**

* Port Scanning: 
    * Involves connecting to or probing TCP and UDP ports of the target system to determine whether the services are running.

* Vulnerability Scanning:
    * Method for checking whether a system is exploitable by identifying its vulnerabilities.

![Network Scanning](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Network%20Scanning%20.png)

                    Network Scanning


### **Page 6**

* Increases the size of the IP address space from 32 bits to 128 bits.


![IPv6 Scan](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/IPv6%20scan.png)


                    IPv6 Scanning


### **Page 10**

* It is a three-step process that requires both the client and server to exchange synchronization and acknowledgment packets before the real data communication process starts.


![Three way handshake](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Three%20way%20handshake.png)


                   Three-Way Handshake


Backend note to explain the steps: 

Step 1: In the first step, the client establishes a connection with a server. It sends a segment with SYN and informs the server about the client should start communication, and with what should be its sequence number.

Step 2: In this step server responds to the client request with SYN-ACK signal set. ACK helps you to signify the response of segment that is received and SYN signifies what sequence number it should able to start with the segments.

Step 3: In this final step, the client acknowledges the response of the Server, and they both create a stable connection will begin the actual data transfer process.


### **Page 12**

1. Unicast
    * Acted on by a single recipient
    * Enables one to-one communication.

2. Multicast
    * Acted on only by members of a specific group
    * Enables one-to-many communication.

3. 3. Broadcast
    * Acted on by everyone in the network
    * Enables one-to-everyone communication. 


### **Page 15**

* Six TCP control flags manage the connection between hosts and give instructions to the system.
* Four of these flags (SYN, ACK, FIN, and RST) govern the establishment, maintenance, and termination of a connection. 
* The other two flags (PSH and URG) provide instructions to the system.


### **Page 16**

* Acknowledgement (ACK)
    * Confirms successful packet retrieval.
    * Identifies the next expected sequence number.


### **Page 20**

1. Physical (bits) 
    * Physical connection between the devices.

2. Data Link (frames)
    * Responsible for the node-to-node delivery of the message.

4. Transport (segments)
    * Provides the acknowledgment of the successful data transmission and re-transmits the data if an error is found.

![OSI Model](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/OSI%20model.png)


                        OSI Model


### **Page 21**

Backend Note:
1. Link Layer: 
    * The packet’s network protocol type is identified by the data-link layer.
    * Error prevention and “framing” are also provided by the data-link layer.


2. Internet Layer: 
    * Defines the protocols which are responsible for the logical transmission of data over the entire network.


3. Transport layer: 
    * Exchange data receipt acknowledgments and retransmit missing packets to ensure that packets arrive in order and without error.

4. Application layer: 
    * Responsible for end-to-end communication and error-free delivery of data.

 
![TCP IP Model](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/TCP%20IP%20model.png)


                    TCP IP Model


### **Page 24**

 
![Nmap Scan](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/nmap%20scan.png)


                        Nmap scan


### **Page 32**

* It can send custom TCP/IP packets and display target replies similarly to a ping program with ICMP replies. 
* It also supports idle host scanning.
* Using Hping, an attacker can study the behavior of an idle host and gain information about the target.


### **Page 33**

* Nmap provides detailed and organized output, including service/version detection, OS fingerprinting, and more.
* Emphasizes on raw packet data and low-level details.

### **Page 35**
* IP Scanner for IOS
    * Scans your local area network to determine the identity of all its active machines and Internet devices.

* Fing for IOS and Android
    * It allows attackers to discover all devices connected to a Wi-Fi network along with their IP and MAC address as well as the name of the vendor/device manufacturer.


### **Page 40**

Here's how a typical ICMP ping sweep works:

1. Range Selection: The person conducting the ping sweep selects a range of IP addresses that they want to investigate. This range could cover a specific subnet, an entire network, or a set of IP addresses.

2. ICMP Echo Request: ICMP Echo Request messages (ping) are then sent to each IP address in the selected range.

3. Response Analysis: If a host is active and reachable, it will respond to the ICMP Echo Request with an ICMP Echo Reply. The absence of a response indicates that the host is either not active or is configured not to respond to ICMP Echo Requests.

4. Results Compilation: The results of the ping sweep are then analyzed to identify active hosts. This information can be valuable for network administrators to understand the layout of their network, identify potential issues, or detect unauthorized devices.


### **Page 42**

* Pros
    * Scan never gets the time-out error while waiting for the response.


### **Page 44**

*  Attackers use the TCP Xmas scan to determine if ports are closed on the target machine via the RST packet. 


### **Page 46**

* ACK scanning is often used for different purposes:

    1. Firewall Detection: ACK scanning can help identify the presence of stateful firewalls. If the firewall allows ACK packets through, it might suggest the presence of a stateful inspection firewall.

    2. Filtering Detection: It can be used to detect packet filtering devices or configurations on the network. Some filtering devices may allow or block specific types of TCP packets.

    3. Bypassing Intrusion Detection Systems: ACK scanning can be used as a stealthy scanning technique that may bypass certain types of intrusion detection or prevention systems.



### **Page 50**

 
![UDP Scan](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/UDP%20Scanning.png)


                       UDP Scanning


* UDP Packets
    * When you send a packet to a closed UDP port, most of the hosts send an ICMP_PORT_UNREACH error. Thus, you can determine whether a port is open if UDP packets or ICMP errors are not guaranteed to arrive.

    * Thus, UDP scanners of this type must implement retransmission of packets that appear lost.



### **Page 52**

*  The list scan shows all IP addresses as “not scanned” (0 hosts up).



### **Page 53**

* Vulnerabilities in UPnP may allow attackers to launch Buffer overflow or DoS attacks.


### **Page 54**

* ARP ping scans are used to discover active devices in the IPv4 range, even if they are hidden by firewalls.
* ARP scans show the MAC address of the network interface on the device and all devices sharing the same IPv4 address on the LAN.


### **Page 57**

* Attackers use packet fragmentation tools such as Nmap and fragroute to split the probe packet into smaller packets that circumvent the port-scanning techniques employed by IDS. 


### **Page 58**

* When attackers send malformed packets to a target, these packets hop through various routers and gateways to reach the destination.

### **Page 59**

* This technique makes it difficult for the IDS/firewall to determine which IP address is actually scanning the network and which IP addresses are decoys.

* These decoys can be generated in both initial ping scans such as ICMP, SYN, ACK, etc., and during the actual port scanning phase.


### **Page 60**

*  When spoofing a nonexistent address, the target replies to a nonexistent system and then hangs until the session times out, thus consuming a significant amount of its own resources.

![IP Spoofing](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/IP%20Spoofing.png)


                       IP Spoofing


### **Page 66**

Proxy Chaining

The proxy chaining process is described below: 
* The user requests a resource from the destination. 

* A proxy client in the user’s system connects to a proxy server and passes the request to the proxy server.

* The proxy server strips the user’s identification information and passes the request to the next proxy server.

* This process is repeated by all the proxy servers in the chain. 

* Finally, the unencrypted request is passed to the web server.


### **Page 67**

Why use an Anonymizer?

1. Ensuring Privacy
2. Accessing government-restricted content
3. Protection against online attacks
4. Bypassing IDS and firewall rules


### **Page 70**

![Active and Passive Banner Grabbing](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Active%20and%20Passive%20Banner%20Grabbing.png)


            Active and Passive Banner Grabbing


### **Page 74**

* Users connect remotely to a machine using Telnet, sometimes referred to as Telnetting into the system. They are prompted to enter their username and password combination to access the remote computer.
