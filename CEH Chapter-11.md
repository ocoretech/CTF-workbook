## **CEH Chapter - 11**

### **Page 4**

Session Hijacking

* Attacker steals a valid session ID and uses it to authenticate himself with the server.


![Session-Hijacking](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Session-Hijacking.png)


                    Session Hijacking



### **Page 5** 

Steps of Session Hijacking

![Session-Hijacking-Process](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Session-Hijacking-Process.png)


                        Session Hijacking Process


### **Page 8**

Crime Attack

* To perform a CRIME attack, an attacker must use social engineering techniques to trick the victim into clicking on a malicious link.
* If the victim has already established an HTTPS connection with a secured web application, the attacker sniffs the victim's HTTPS traffic using techniques such as ARP spoofing. 


### **Page 12**

RST Hijacking

* Involves injecting an authentic-looking reset (RST) packet using a spoofed source address and predicting the acknowledgment number.


![RST-Hijacking-Process](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/RST-Hijacking-Process.png)

                    RST Hijacking Process



Blind Hijacking


![Blind-Hijacking-Process](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Blind-Hijacking-Process.png)

                            Blind Hijacking Process



### **Page 14**

Session Hijacking Tools

* Hetty

    * It provides Machine-in-the-middle (MITM) HTTP proxy with logs.
    * HTTP client for manually creating/editing requests and replaying proxied requests.
    * Intercepting requests and responses for a manual review.



* Bettercap

    * Allows you to perform reconnaissance and various attacks on Wi-Fi networks, Bluetooth low energy devices, wireless HID devices, and IPv4/IPv6 networks.



Session Hijacking tools for mobile

* DroidSheep

    * It obtains the session ID of active users on the Wi-Fi network and uses it to access a website as an authorized user on the mobile.


* DroidSniff

    * This tool is used for testing the security of user accounts, e.g. Facebook, Twitter, LinkedIn etc.

    * Identifies the poor security properties of network connections without encryption.


* FaceNiff

    * Can hijack sessions only when the WiFi network does not use the Extensible Authentication Protocol (EAP).

    
