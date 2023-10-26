## **[VulnCommerce](https://app.hackinghub.io/vuln-commerce)**

### **Objective**
Vulncommerce is an e-commerce site that sells premium laptops at affordable prices, lets just hope their laptops arent as bad as their vulnerable website

### **Solution**

### **1. Reconnaissance**

The homepage of VulnCommerce is about the products they are offering i.e. laptops.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/a2577ba2-0d39-4c12-bae7-f40436b4df29)


Run dnsrecon to find subdomains


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/220d2984-6914-4ed9-bf7f-021d1499ce17)


                                      Flag 1 found by using dnsrecon


The first flag has been found with the help of dnsrecon method. Start up ffuf to find different directories associated with the domain(ffuf -w CTF/content.tct -t 2 -p 1.0 -u vulncommerce.co.uk)

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/121c36e9-6353-4222-b04e-06dac3c12952)

Use each of these directories to find out information regarding flags.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/71dbf782-493f-4b42-bac6-42c0a1515b0f)

                                      
                                      Flag 2 found by new directory


Flag 2 has been found in the "stats" directory along with the file system information. 


### **2. Usage of Sitemap**


Now use sitemap on burp suite to go through all the directories. There is one unique directory called "upload" check the files available in it.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/a88e71fe-9b82-4ab8-8876-8a5b88f1e0d0)


Click on "tech" directory which opens updates.txt

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/60cabaa2-6f5b-43eb-80fa-1c864ff1b999)


                                      Flag 3 found from Burp Suite


The third flag has been found with the help of Site map. Along with the flag, the directory has provided an email sign up directory, visit it.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/23dd4199-a944-4583-a84a-3f1b03466e57)


### **3. Changing the hash value**


Sign up on this newsletter. You will recieve an email regarding your signup. In the email, they have given a URL to confirm our subscription. The hash in the link sent via email has a relation with the number provided before it.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/26aaa000-6908-4707-9341-f7e5b425bacb)


Try changing the number to 8 and the hash value related to it.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/8897cc13-f940-4e9a-9f3f-e9a4fac18d49)

                               
                                Flag 4 found by changing the hash value and the id number


The fourth flag has been found with the help of changing the hash value. 

### **4. Social Engineering Attack**


It also provides us with an email. Send an email to simon.boswell.osm86x8t@vulncommerce.co.uk with the login link. 
This will act as a social engineering attack. After few minuites you will get to see the name "Simon" in the login page.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/0ed8236a-4a65-48fb-94b9-8ff8b106c635)


                                      Flag 5 found (Social engineering)


The fifth flag has been found using social engineering and you have been successfully logged into Simon's account.



### **Common Vulnerabilities in Vulnrecruitment:**
1. Social Engineering


### **Tools used:**
1. nslookup
2. ffuf
3. Sitemap
4. BurpSuite



