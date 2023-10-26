        
# **[HackingHub](https://app.hackinghub.io/)**



Hey folks, in this blog I'm going to share how to get started in HackingHub and complete the challenges step by step. Let's jump into it.

Before knowing about how things work in hackinghub let’s first understand what hackinghub is, what do we do in hackinghub, what is a flag, and how hackinghub helps you to develop your hacking skills.

HackingHub is a type of information security competition that challenges competitors to solve a variety of tasks. It is a special type of cybersecurity competition designed to challenge computer participants to solve computer security problems or capture and defend computer systems. Let's get into it and start our first challenge.


### **[VulnLawyers](https://app.hackinghub.io/vuln-lawyers)**
    https://app.hackinghub.io/vuln-lawyers
   
### **Objective:** Our main purpose is to find a way into their admin portal. 

### **Solution:**

### **1. Reconnaissance**
   
The website provides a domain to start the challenge. For reconnaissance, use nslookup tool and the command: (nslookup -type=any vulnlawyers.co.uk)  to find any type of record on the webpage. If the result doesn't show any useful information, move on to the next step i.e. brute forcing. 

Start searching for the subdomains with the help of brute force attack with dnsrecon(dnsrecon -d vulnlawyers.co.uk -D CTF/subdomains.txt -t brt). After finding the subdomains, use curl tool for extracting the data from the subdomain. 
The results will provide you with the first flag and a new URL "http://data.vulnlawyers.co.uk", but we will check into that later.  


                                                Flag 1 found with the hekp of dnsrecon tool
   

### **2. Finding Endpoints**

With the wordlists provided by hackinghub, start up "ffuf" tool to find out different endpoints on the domain. The command will work as following: (ffuf -w CTF/content.txt -t 2 -p 1.0 -H "Cookie: $cookie" -u vulnlawyers.co.uk/FUZZ).  Now check for the results, you can see there are five endpoints on the domain. Now see if they work one by one. Only one endpoint worked i.e. the login page on the URL. It redirects you to a denied page, where it says "Access is denied from your IP address".
  
  
![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/b88c36d3-7c3d-40e0-81f5-bdd0a5bf11e3)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/aff7639e-8669-4ced-b0cb-ed1ae8b987fb)


If you are not being able to login, there are some other ways you can try for example, open Burpsuite and search for a GET request for the login page, and send it to the repeater. Send the same request and carefully focus on the response, the second flag has been found using burp suite and a new endpoint is provided for the login page.   
     

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/08ec4318-5579-4d05-8cbc-d9fb649af036)


                                Flag 2 found with the help of Burp Suite software


Now add that new endpoint to the URL. You find the login page here and two fields: Username and Password. As you don't have the credentials, we will go back to the newly found URL while using curl i.e. "http://data.vulnlawyers.co.uk". After visiting it, you will find the third flag.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/fa1d57be-13b9-471d-aaec-c38a1c8f7b53)

                                       Flag 3 found in the new domain



### **3. Finding the Credentials**

Start up "ffuf" to find the new domain. The command works as follows: (ffuf -w CTF/content.txt -t 2 -p 1.0 -H "Cookie: $cookie" -u http://data.vulnlawyers.co.uk/FUZZ). You will find a new endpoint and you visit the website with that endpoint i.e. "users". After visiting you find multiple lawyer names and their email ids along with the fourth flag. You can notice in result that there are five lawyers and their email ids. 
This can be a huge vulnerabiltiy because you can use brute force attack and find the correct credentials.


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/c7f9e127-8c82-4dde-89c1-863fc1c27f80)


                                Flag 4 found with the help of new endpoint


After finding the correct credentials, use them to login the portal. You will find your fifth flag and the staff portal with the current cases and who is managing it.

                                Flag 5 found with the help of correct credentials

Use brute force attack on the user who is managing the case and find out the user's login credentials. After logging in, you will find out the case name and an option to delete cases. Hit enter and you will find the final and sixth flag.

                                Flag 6 found by deleting the active cases


   
