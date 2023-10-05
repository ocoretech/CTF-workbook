        
# **CTF Challenges (HackingHub)**
https://app.hackinghub.io/


Hey folks, in this blog I'm going to share how to get started in CTF(HackingHub) and complete the challenges step by step. Let's jump into it.

Before knowing about how things work in CTF let’s first understand what CTF is, what we do in CTF, what is a flag, and how CTF helps you to develop your hacking skills.

Capture the Flag(HackingHub) is a type of information security competition that challenges competitors to solve a variety of tasks. It is a special type of cybersecurity competition designed to challenge computer participants to solve computer security problems or capture and defend computer systems. Let' get into it and start our first challenge.


### **CTF Challenges solutions**

### 1. [VulnLawyers](https://app.hackinghub.io/vuln-lawyers)
    https://app.hackinghub.io/vuln-lawyers
   
### **Objective:** Our main purpose is to find a way into their admin portal. 

### **Solution:**

### **1. Reconnaissance**
   
   We have to find 6 flags by using our skills, let's jump into it. 
   The website provides a domain to start the challenge.
   For reconnaissance, use nslookup to find any type of record on the webpage. If the result doesn't show any useful information, move on to the next step i.e. brute forcing.
   Start searching for the subdomains with the help of bruteforcing with dnsrecon. After finding the sub-domains, use curl for extracting the data from the subdomain. You will find a different URL "http://data.vulnlawyers.co.uk", but we will check it later.  
   The first flag has been found with the help of brute force vulnerability.

### **2. Finding Endpoints**

With the wordlists provided by hackinghub, use FUZZ tool to find out different endpoints on the domain. Now check for the results, you can see there are five endpoints on the domain. Now see if they work one by one.
Only one endpoint worked i.e. the login page on the URL. It redirects you to a denied page, where it says "Access is denied from your IP address".
  
  
![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/b88c36d3-7c3d-40e0-81f5-bdd0a5bf11e3)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/aff7639e-8669-4ced-b0cb-ed1ae8b987fb)


If you are not being able to login, there are some other ways you can try for example, open Burpsuite and search for a GET request for the login page, and send it to the repeater.
Send the same request and carefully focus on the response, the second flag has been found using burp suite and another endpoint for the login page.   

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/7f788958-b0a1-4c6a-bc7e-eb16c03381b6)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/2247b7de-cacc-468c-b99a-521af77a3a3f)
     

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/08ec4318-5579-4d05-8cbc-d9fb649af036)

Now add that new endpoint to the URL. You find the login page here and two fields: Username and Password. As you don't have the credentials, we will go back to the newly found URL while using curl i.e. "http://data.vulnlawyers.co.uk". After visiting it, you will find the third flag.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/fa1d57be-13b9-471d-aaec-c38a1c8f7b53)
#### Flag 3 found in new domain


### **Finding the Credentials**

FUZZ the new domain, you find a new endpoint and you visit the website with that enpoint i.e. "users". After visiting we find multiple lawyer names and their email ids along with the fourth flag. You can notice in result that there are five lawyers and their email ids. 
This can be a huge vulnerabiltiy because you can use burp suite to brute force and find the correct credentials.

![Flag 4 found by Fuzzing](https://github.com/ocoretech/CTF-workbook/assets/67775716/4aadde45-7036-4a74-8a21-428b5a0410d4)


After finding the correct credential, login the staff portal, 


* After we login, we get our fifth flag and the staff portal with the current cases and who is managing it.


   
