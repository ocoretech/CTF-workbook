## **CEH Chapter - 18

### **Page 29**

IOT Attack Types

* BlueBorne Attack

    * BlueBorne is compatible with all software versions and does not require any user interaction, except that the Bluetooth should be activated. 


![BlueBorne-Attack](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/BlueBorne-Attack.png)



### **Page 32**

Rolling Code Attack

Given below are the steps followed by an attacker to perform a rolling-code attack: 

* Victim presses car remote button and tries to unlock the car,

* Attacker uses a jammer that jams the car's reception of the rolling code sent by the victim and simultaneously sniffs the first code.

* The car does not unlock; victim tries again by sending a second code.

* Attacker sniffs the second code.

* On the second attempt by the victim, the attacker forwards the first 
code, which unlocks the car.

* The recorded second code is used later by the attacker to unlock and steal the vehicle.


![Rolling-Code-Attack](https://raw.githubusercontent.com/ocoretech/CTF-workbook/main/images/Rolling-Code-Attack.png)



### **Page 33**

SDR-Based Attacks

* Replay Attack

    * The attacker segregates the command sequence and injects it into the IoT network.


Replay attack Steps:

* Attacker targets the specified frequency that is required to share information between devices.

* After obtaining the frequency, the attacker can capture the original data when the commands are initiated by the connected devices.

* Once the original data is collected, the attacker uses free tools such as URH (Universal Radio Hacker) to segregate the command sequence.

* Attacker then injects the segregated command sequence on the same frequency into the IoT network, which replays the commands or captured signals of the devices.

