## **[VulnCommerce](https://app.hackinghub.io/vuln-commerce)**

### **Objective**
Vulncommerce is an e-commerce site that sells premium laptops at affordable prices, lets just hope their laptops arent as bad as their vulnerable website

### **Solution**

### **1. Reconnaissance**

The homepage of VulnCommerce is about the products they are offering i.e. laptops.

![Homepage](<VulnCom Landing Page.png>)

Start with dnsrecon to find subdomains.

![Flag 1](<VulnCom Flag 1.png>)

The first flag has been found with the help of dnsrecon. Now use "ffuf" to find the different directories associated with the domain.

![Fuzz](<VulnCom FUZZ.png>)

Use each of these directories to find out information regarding flags.

![Flag 2](<VulnCom Flag 2.png>)

Flag 2 will be found in the "stats" directory along with the file system information. Now use sitemap on burp suite to go through all the directories. There is one uniques directory called "upload" check the files available in it.

![Upload](<VulnCom upload.png>)

Click on "tech" directory which opens updates.txt

![Flag 3](<VulnCom Flag 3.png>)

The third flag has been found with the help of Site map. Along with the flag, the directory has provided an email sign up directory, visit it.

![News](<VulnCom Newsletter.png>)

Sign up on this newsletter. You will recieve an email regarding your signup. In the email, they hav given a URL to confirm our subscription. The hash in the link sent via email has a relation with the number provided before it.

![Conf](<VulnCom Email Confirmation.png>)

Try changing the number to 8 and the hash value related to it.

![Flag 4](<VulnCom Flag 4.png>)

The fourth flag has been found with the help of changing the hash value. It also provides us with an email. Send an email to simon.boswell.osm86x8t@vulncommerce.co.uk with the login link. 
This will act as a social engineering attack. After few minuites you will get to see the name "Simon" in the login page.

![Flag 5](<VulnCom Flag 5.png>)

The fifth flag has been found using social engineering and also we have been successfully logged into Simon's account.

