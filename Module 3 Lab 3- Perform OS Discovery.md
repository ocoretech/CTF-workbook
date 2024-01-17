## **Task 2: Perform OS Discovery using Nmap Script Engine (NSE)**

Steps:

1. Turn on Kali Linux and open the terminal.

2. In the terminal window, type the command nmap -A [Target IP Address] (here, the target machine is Parrot OS [127.0.0.1]) and press Enter.

Note: -A: to perform an aggressive scan. 

3. The scan results appear, displaying the open ports and running services along with their versions and target details.

4. In the terminal window, type the command nmap -O 127.0.0.1 and press Enter.

Note: -O: performs the OS discovery.

5. The scan results appear, displaying information about open ports, respective services running on the open ports, and the name of the OS running on the target system.

6. In the terminal window, type the command nmap --script smb-os-discovery.nse 127.0.0.1 and press Enter.

Note: --script: specifies the customized script and smb-os-discovery.nse: attempts to determine the OS, computer name, domain, workgroup, and current time over the SMB protocol.

7. The scan results appear, displaying the target OS, computer name, NetBIOS computer etc.

