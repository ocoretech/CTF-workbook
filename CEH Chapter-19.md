## **CEH Chapter - 19**

### **Page 5**

NIST Definition of Cloud Computing

* Cloud computing is a model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (e.g., networks, servers, storage, applications, and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction. 


### **Page 18**

Cloud Deployment Models

**Private Cloud**

Advantage:

* Security enhancement (services are dedicated to a single organization).
* Increased control over resources (organization is in charge).
* High performance
* Customizable hardware, network, and storage performances

Disadvantages:

* Costly
* On-site maintenance


**Public Cloud**

Advantages:

* Simplicity and efficiency.
* Low cost
* Reduced time (when server crashes, needs to restart or reconfigure cloud). 
* No maintenance (public cloud service is hosted off-site).

Disadvantages:

* Security is not guaranteed 
* Lack of control 
* Slower than Private Cloud



**Community Cloud**

Advantages:

* Less expensive compared to the private cloud
* Flexibility to meet the community's needs
* Compliance with legal regulations
* High scalability
* Organizations can share a pool of resources from anywhere via the Internet.

Disaadvantage:

* Competition between consumers in resource usage
* Inaccurate prediction of required resources
* Lack of legal entity in case of liability
* Moderate security



### **Page 19**

**Hybrid Cloud**

Advantages:

* Offers both secure and scalable public resources
* High level of security (comprises private cloud)
* Allows to reduce and manage the cost according to requirements


Disadvantages:

* Communication at the network level may be conflicted as it uses both public and private clouds
* Difficult to achieve data compliance
* Complex service level agreements (SLAs) 


**Multi Cloud**

Advantages:

* High reliability and low latency
* Flexibility to meet business needs
* Cost-performance optimization and risk mitigation
* Low risk of distributed denial-of-service (DDoS) attacks 


Disadvantages:

* Multi-cloud system failure affects business agility
* Using more than one provider causes redundancy
* Security risks due to complex and large attack surface 


### **Page 33**

Wrapping Attack

Countermeasures:

* Use XML schema validation to detect SOAP messages.

* Apply authenticated encryption in the XML encryption specification. 

* Improve the interface between signature verification and business logic functions.

* Ensure that users specify the SOAP body and headers to be signed by implementing the WS-SecurityPolicy "SignedParts" policy.

* Use the CryptoCoverageChecker interceptor to specify the XPath expression related to the element that should be signed or encrypted.



### **Page 35**

Side Channel Attacks

Countermeasures:

* Implement a virtual firewall in the cloud server back-end of the cloud computing.

* Implement random encryption and decryption.

* Lockdown OS images and application instances to prevent compromising vectors.

* Check for repeated access attempts to local memory.



### **Page 36**

Cloud Hopper Attack

Countermeasures:

* Implement multi-factor authentication to prevent compromise of credentials.

* Ensure mutual co-ordination between customers and CSPs in case of abnormal incidents.

* Ensure customers are aware and follow the cloud service policies.

* Use data categorization to reduce the impact of the attack.


### **Page 37**

CloudBorne Attack

Countermeasures:

* CSPs should keep the firmware up-to-date.

* Sanitize the server firmware before it is assigned to new customers. 

* Validate the server for implants and backdoors before deploying.

* CSPs should verify whether the physical hardware has been tampered with before delivery.


### **Page 38**

Man-In-The-Cloud Attack (MITC)

Countermeasures:

* Limit access to the cloud services

* Limit IP address range and offer services only via VPNs. 

* Integrate the cloud-based solution with controlled intrusion detection systems. 


### **Page 39**

Cloud Security Tools

* Cisco Umbrella

    * Cisco Umbrella is an app discovery tool provides full visibility and risk information to manage cloud applications in a secure and organized manner. 
    
    * Provides the list of apps with labels such as Unreviewed, Under Audit, Approved, and Not Approved for tracking.