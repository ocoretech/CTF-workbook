## **CEH Chapter - 20**

### **Page 8**

Classical Ciphers

* These ciphers are easily deciphered, they are generally unreliable.


### **Page 9**

Substitution Cipher

* It performs inverse substitution to decipher the text.


### **Page 12**

Modern Ciphers

* They provide message secrecy, integrity, and authentication of the sender. 

* A user can calculate a modern cipher using a one-way mathematical function that is capable of factoring large prime numbers.

### **Page 22**

DES (Data Encryptions Standard)

* DES provides 72 quadrillion or more possible encryption keys and chooses a random key for the encryption of each message.


### **Page 24**

AES (Advanced Encryption Standard)

AES Pseudocode

* The system copies the cipher input into the internal state and then adds an initial round key.

* The system transforms the state by iterating a round function in a number of cycles.

* After completing rounding, the system copies the final state into the cipher output. 



### **Page 25**

RC (Rivest Cipher)

RC4

* Uses 8 to 16 system operations.
* Can run fast when used in software.


RC6

* Uses 4-bit registers because the Block size of the AES  is 128 bits.



### **Page 26**

Blowfish

* Designed to replace DEA or IDEA algorithms.

* The algorithm has two parts, the first part handles expansion of the key and the second part encrypts the data.



### **Page 28**

Serpent

* Designed by Ross Anderson, Eli Biham, and Lars Knudsen.

* Uses a 128-bit symmetric block cipher with key sizes of 128, 192, or 256 bits.

* It involves 32 rounds of computational operations that include substitution and permutation operations on four 32-bit word blocks using 8-variable S-boxes with 4-bit entry and 4-bit exit.

* Moderate encryption speed.




### **Page 29**

Tiny Encryption Algorithm (TEA)

* Created by David Wheeler and Roger Needham

* Presented for the first time in 1994.

* Simple and easy to implement in code.

* Uses 64 rounds. Number of rounds should be even because they are implemented in pairs. Uses a 128-bit key operating.

* Also uses a constant that is defined as 232/the golden ratio. This constant is also referred as Delta. 

* 128-bit key is split into four different 32-bit subkeys labeled K[0], K[1], K[2], and K[3]. 



### **Page 30**

CAST-128

* CAST-128 or CAST5 is a symmetric-keyblock cipher.

* Has a 12 or 16 round Feistel network with 64-bit block size.

* Uses a key size varying from 40 to 128 bits in 8-bit increments.

* The round function consists of three alternating types for performing addition, subtraction, or XOR operations at different stages.


### **Page 31**

GOST Block Cipher (Government Standard)

* Also called as Magma, is a symmetric key block cipher.

* It is a 32-round Feistel network working on 64-bit blocks with 256-bit key length.

* It consists of an S-box that can be kept secret, and it contains approximately 354 bits of secret information.

* Kuznyechik is the latest extension of GOST, which uses 128-bit blocks



#### **Page 32**

Camellia

* Symmetric key block cipher with either 18 rounds (for 128-bit keys) or 24 rounds (for 256-bit keys).

* Working with 128-bit blocks and has key sizes of 128, 192, and 256-bits.

* Used as part of the Transport Layer Security (TLS) protocol.

* Camellia cannot be brute-forced even with the latest technology.
  It uses a smaller key size of 128 bits, thus making it a safe cipher.

* Provides high security and its processing skills are equivalent to those of AES.



### **Page 37**

YAK

The YAK protocol can accomplish the following objectives: 

* Private key security
* Full forward secrecy
* Session key security


### **Page 38**

DSA (Digital Signature Algorithm)

Benefits of DSA:

* Less chances of forgery compared with a written signature

* Quick and easy method of business transactions

* Fake currency problem can be mitigated considerably




### **Page 45**

RIPEMD

* There exist 128-, 256-, and 320-bit versions of this algorithm, which are called RIPEMD-128, RIPEMD-256, and RIPEMD-320.



### **Page 46**

GOST

* Produces a fixed-length output of 256 bits.

* Input message is broken up into chunks of 256-bit blocks.

* If a block is less than 256 bits, then the message is padded by appending as many zeros to it as are required to make the length of the message 256 bits.


### **Page 49**

CHAP (Challenge-Handshake Authentication Protocol)

* It is an authentication mechanism used by Point-to-Point Protocol (PPP) servers to authenticate or validate the identity of remote clients or network hosts.

* More secure and effective compared to Password Authentication Procedure (PAP).

* Provides protection against replay attacks.



### **Page 50***

Extensible Authentication Protocol (EAP)

* Originally designed for point-to-point connections.

* Utilised as an alternative to the CHAP and PAP authentication protocols, as it is more secure and supports different authentication mechanisms.




### **Page 51**

Hash function Attacks

1. Collision

    * Performed by finding two different input messages that result in the same hash output. 

    * Allows the attacker to perform cryptanalysis by exploiting the digital signature used to generate a different message with same hash value.

    * Once the attacker is able to detect any collisions in the hash, they try to identify more collisions by concatenating data to the matching messages.



2. Birthday Attack

    * A birthday attack is the name used to refer to a class of brute-force attacks against cryptographic hashes that makes the brute forcing easier.




3. Rainbow Table

    * Type of cryptography attack where an attacker uses a rainbow table to reverse cryptographic hash functions.

    * Rainbow table is a precomputed table that contains word lists like dictionary files and brute force lists and their hash values.

    * It uses the cryptanalytic time-memory trade-off technique to crack the cryptography, which requires less time than some other techniques.




4. Brute-force Attack

    * Brute-force attack is a high-resource and time intensive process, but it is more guaranteed to achieve results.

    * To find the key in a brute-force attack depends on the length of the key.

    * A brute-force attack will be successful if and only if the attacker has enough time to discover the key.


The difficulty of a brute-force attack depends on various factors, such as:

    *The length of the key
    
    * The number of possible values each component of the key can have 
    
    * The time it takes to attempt each key

    * If there is any mechanism that locks the attacker out after a certain number of failed attempts




### **Page 78**

GNU Privacy Guard (GPG)

GPG is used for the following: 

* Proper key management of both private and public keys

* Creating new private keys and exporting or importing any key.

* Pushing the public key to the key server 

* Encrypting and signing files using asymmetric keys for encrypting any file used for email or FTP


### **Page 91**

Disk encryption tools

* **VeraCrypt**

    Software for establishing and maintaining an on-the-fly-encrypted volume (data storage device).

    In on-the-fly encryption, data are automatically encrypted immediately before saving and decrypted immediately after loading.


* **Rohos Disk Encryption** 

    Rohos is a disk encryption tool that allows users to create hidden and encrypted partitions on a computer.

    The tool uses the NIST-approved AES encryption algorithm and an encryption key length of 256 bits.


* **BitLocker Drive Encryption** 

    BitLocker provides offline-data and OS protection for your computer. It helps ensure that data that is stored on a computer that is running Windows is not revealed if the computer is tampered with when the installed OS is offline.

    Uses a microchip that is called a Trusted Platform Module (TPM) to provide enhanced protection for your data and to preserve early boot-component integrity.


### **Page 105**

Side-Channel Attacks

Mitigation Techniques for Side-Channel Attacks:

* Use fixed-time algorithms (i.e., no data-dependent delays). 
* Add amplitude or temporal noise to reduce the attacker's signal-to-noise ratio.
* Employ power-line conditioning and filtering to slow down the power monitoring analysis.