## **[VulnTraining](https://app.hackinghub.io/vuln-training)**

### **Objective**

Capture all the flags

### **Solution**

### **1. Reconnaissance**

On the home page of the vulntraining server, they have displayed various training services. Check the page source for any additional information.

![Homepage](<Training Home.png>)

You will find your first flag in the page source.

![Flag 1](<VulnTraining Flag 1.png>)

Along with the flag you will find a CSS file in the source code, open the file.

![CSS](<CSS File.png>)

You can see that they have provided us another URL, open and visit it.

![URL](<Amazon URL.png>)

The URL includes a XML file which consists a directory named "flag.txt". Include it in the URL and you will find the second flag with the help of the specified directory.

![Flag 2](<VulnTraining Flag 2.png>)

Use dnsrecon to find out subdomains. You will find two subdomains but both of them will have no access. Us "theHarvester" tool for more information of our server.

![Harvester](<Harvester VulnTraining.png>)

A third subdomain has been found, visit that subdomain and you will find your third flag with the help of "theHarvester".

![Flag 3](<VulnTraining Flag 3.png>)

With the help of "ffuf" tool, search for directories/endpoints.
There are multiple endpoints provided in the reseult, use all of them in the server and look for which one provides you the information.

With "robots.txt" you will find a secret directory. Insert it in the URL and wait for the results. Fourth flag has been found using the directory "robots.txt"

![Flag 4](<VulnTraining Flag 4 .png>)


### **2. Logging in Admin URL**

By using the directory "server", it redirects you to a login page, use any random credentials then check for your "server" request in burp suite and send it to the repeater. Send the same request and check the response, you will find the fifth flag with the help of burp suite. You will aslo find a directory which leads to a secret admin login portal. But we will get to that later.

![Flag 5](<VulnTraining Flag 5.png>)

Move towards the directory ".git/index". You will find a URl leading to Github. 

![Github](<Github URL.png>)

Sixth flag is found with the help of github directory. You will find a framework too, check it out.

![Flag 6](<VulnTraining Flag 6.png>)

Click on the removed database creds and you will find the username for login but the password is still unknown. 
Open the secret admin Login portal and try to login with the removed database credentials.

![Secret Login](<Secret Login.png>)

You will successfully login in with the credentials. 

![Successful](<SLogin Success.png>)


### **3. Logging in Billing URL**

Click on the billing users and you will find the seventh flag with the username and the password for the server status portal.

![Flag 7](<VulnTraining Flag 7.png>)

Head towards the billing subdomain we found during dnsrecon and try logging in with the credentials. It says that the password is invalid, use brute force and find ou the correct password.

![Pass](Password.png)

You will find the eighth flag after successfully logging in with the help of brute force attack. You will also find some customer names and ids with their invoices. 

![Flag 8](<VulnTraining Flag 8.png>)

Click on id 1 and check for a GET request and send it to the repeater. You will find a token in the response tab when you search for a id 10. 
Use that token as a cookie with the help of "ffuf". You will find one endpoint i.e. "api".

It says API error, so try and look for any GET requests through request bin. You will find the nineth flag with the help of "api" endpoint. The GET request will also provide you with a X-token. 

![Flag 9](<VulnTraining Flag 9.png>)

### **4. Admin Subdomain Fuzzing**

Head towards the admin subdomain you found during dnsrecon and use the mod header plugin to input a X-token value.

![Admin sub](<Admin subdomain.png>)

You will be provided with another endpoint called "invoices" for the admin subdomain. Now use FUZZING to find out more endpoints of the subdomain with "invoices" endpoint. You will find admin, users, 03, 05, 3 ad 5 as endpoints. Check every endpoint to find the remaining flags.

You will find the tenth flag with the help of the endpoints, with a username and an apikey.

![Flag 10](<VulnTraining Flag 10.png>)

Change the X-token value to the apikey value you found. Now refresh and you will see there is another secret directory to be included in the URL. 
It provides you a message conversation between to users. You can see that one message has been deleted by the user, find that message by using sqlmap.

The deleted message was the last flag of our challenege.

![Flag 11](<VulnTraining Flag 11.png>)



