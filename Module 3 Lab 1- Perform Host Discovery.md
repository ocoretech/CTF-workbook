## **Task 1 : Perform Host Discovery using Nmap**

Here, we will use Nmap to discover a list of live hosts in the target network. We can use Nmap to scan the active hosts in the target network using various host discovery techniques such as ARP ping scan, UDP ping scan, ICMP ECHO ping scan, ICMP ECHO ping sweep, etc.

Steps: 

1. Turn on Kali linux and open the terminal. We are going to target the parrot machine.

2. In the terminal window, type the command nmap -sn -PR [Target IP Address] (here, the target IP address is 127.0.0.1) and press Enter. 

Note: -sn: disables port scan and -PR: performs ARP ping scan.

3. The scan results indicates that the target Host is up.

4. In the terminal window, type nmap -sn -PU [Target IP Address], (here, the target IP address is 127.0.0.1) and press Enter. 

5. The scan results indicates the target Host is up.

Note: -PU: performs the UDP ping scan. 
      The UDP ping scan sends UDP packets to the target host; a UDP response means that the host is active.


6. Now, we will perform the ICMP ECHO ping scan. In the terminal window, type nmap -sn -PE [Target IP Address], (here, the target IP address is 127.0.0.1) and press Enter. 

7. The scan results indicates that the target Host is up.

Note: -PE: performs the ICMP ECHO ping scan. The ICMP ECHO ping scan involves sending ICMP ECHO requests to a host. If the target host is alive, it will return an ICMP ECHO reply.

8. Now, we will perform an ICMP ECHO ping sweep to discover live hosts from a range of target IP addresses. In the terminal window, type nmap -sn -PE 127.0.0.1 and press Enter. 

9. The scan results indicates the target Host is up.

Note: The ICMP ECHO ping sweep is used to determine the live hosts from a range of IP addresses by sending ICMP ECHO requests to multiple hosts.

10.  In the terminal window, type nmap -sn -PP 127.0.0.1 and press Enter. 

11. The scan results appear indicates the target Host is up as shown in the screenshot.

Note: -PP: performs the ICMP timestamp ping scan.
        
ICMP timestamp ping is an optional and additional type of ICMP ping whereby the attackers query a timestamp message to acquire the information related to the current time from the target host machine.
