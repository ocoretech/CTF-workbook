## **Task 1: Scan beyond IDS/Firewall using Various Evasion Techniques**

Steps:

1. Open Kali Linux and Windows 11.

2. Open wireshark on Windows 11 and start scanning for packets.

3. Open terminal in Kali Linux and type nmap -Pn [IP address of Windows 11(192.168.1.186)] and click Enter.

4. Switch to the Windows 11. You can observe the fragmented packets captured by the Wireshark.

5. In Kali Linux terminal, type nmap -g 80 192.168.1.186 and press Enter.

Note: In this command, you can use the -g or --source-port option to perform source port manipulation.

Source port manipulation refers to manipulating actual port numbers with common port numbers to evade IDS/firewall.

6. The results appear, displaying all open TCP ports along with the name of services running on the ports.

7. Switch to the Windows 11. In the Wireshark window, scroll-down and you can observe the TCP packets indicating that the port number 80 is used to scan other ports of the target host.

8. In Kali Linux type nmap -mtu 8 192.168.1.186 and press Enter. 

Note: In this command, -mtu: specifies the number of Maximum Transmission Unit (MTU) (here, 8 bytes of packets).

9. Switch to the virtual Windows 11. In the Wireshark window, scroll-down and you can observe the fragmented packets having maximum length as 8 bytes.

10. In Kali Linux type nmap -D RND:10 192.168.1.186 and press Enter. 

Note: In this command, -D: performs a decoy scan and RND: generates random and non-reserved IP addresses.

11. Now, switch to the Windows 11. In the Wireshark window, scroll-down and you can observe the packets displaying the multiple IP addresses in the source section.

12. In Kali Linux type nmap -sT -Pn --spoof-mac 0 192.168.1.186 and press Enter. 

Note: In this command --spoof-mac 0 represents randomizing the MAC address, -sT: performs the TCP connect/full open scan, -Pn is used to skip the host discovery. 