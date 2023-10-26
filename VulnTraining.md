## **[VulnTraining](https://app.hackinghub.io/vuln-training)**

### **Objective**

Capture all the flags

### **Solution**

### **1. Reconnaissance**

On the home page of the vulntraining server, they have displayed various training services. Check the page source for any additional information.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/5b6405d8-bb74-4c7b-af16-9e3569ee5892)


You will find your first flag in the page source.


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/b1ede416-b423-494d-bd24-94c7c61b0cda)


                                Flag 1 found in the page source


Along with the flag you will find a CSS file in the source code, open the file.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/8270c188-14eb-4a4b-b096-de461d83d427)


You can see that they have provided us another URL "https://vulntraining.s3.eu-west-2.amazonaws.com", open and visit it. The URL includes a XML file which consists a directory named "flag.txt". Include it in the URL and you will find the second flag with the help of the specified directory.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/2b62f1c4-e2ca-4125-b70e-d8bb6c7928d7)

                            
                            Flag 2 found in a specified directory in XML File


Use "dnsrecon" to find out subdomains(dnsrecon -d vulntraining.co.uk -D CTF/subdomains.txt -t brt). You will find two subdomains but both of them will have no access. Use "theHarvester" tool for more information of our server(theHarvester -d vulntraining.co.uk -b all).

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/b5e4d033-3c10-4487-bb73-5c5da2502722)


A third subdomain has been found, visit that subdomain and you will find your third flag with the help of "theHarvester".


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/565db703-e8ef-43b1-aa7b-8f3f92f27fa0)


                                Flag 3 found using theHarvester tool


### **2. Finding endpoints**


Start up "ffuf" tool, search for directories/endpoints (ffuf -w CTF/content.txt -t 2 -p 1.0 -H "Cookie: $cookie" -u https://vulntraining.co.uk/FUZZ).
There are multiple endpoints provided in the result, use all of them in the server and look for which one provides you the information.

With "robots.txt" you will find a secret directory. Insert it in the URL and wait for the result. Fourth flag has been found using the directory "robots.txt"


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/f1c90a1b-8c88-45ec-9d68-cc007dfb2135)


                                Flag 4 found in the directory secret directory


### **3. Logging in Admin URL**

By using the directory "server", it redirects you to a login page, use any random credentials then check for your "server" request in burp suite and send it to the repeater. Send the same request and check the response, you will find the fifth flag with the help of burp suite. You will aslo find a directory which leads to a secret admin login portal. But we will get to that later.


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/374bf974-215a-4015-8ccb-fd63fb058feb)

                              Flag 5 found in Burp Suite Response

Move towards the directory ".git/index". You will find a URL leading to Github. 

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/6e7f4a0c-4715-4910-9566-b1e51d99481c)


Sixth flag is found with the help of github directory. You will find a framework too, check it out.


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/2a692c45-de46-4adb-9562-29e686af5691)


                                Flag 6 found in Github directory


Click on the removed database creds and you will find the username for login but the password is still unknown. 
Open the secret admin Login portal and try to login with the removed database credentials.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/8bd3946d-26df-4d51-8bf1-f55896c25ddd)


You will successfully login in with the credentials. 


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/a781a8b9-be1d-4827-bf7c-1d9b831442fd)



### **4. Logging in Billing URL**

Click on the billing users and you will find the seventh flag with the username and the password for the server status portal.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/bc087a2b-ab11-492f-89c5-3790ec0f365d)

                                Flag 7 found by logging in Secret Portal 

Head towards the billing subdomain we found during dnsrecon and try logging in with the credentials. It says that the password is invalid, use brute force and find out the correct password.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/9fa72206-8223-4c3d-83c4-0f1109c172d5)


You will find the eighth flag after successfully logging in with the help of brute force attack. You will also find some customer names and ids with their invoices. 

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/4fac2bba-d676-4d79-9942-43427911df3c)

                              Flag 8 found by Brute force attack


Click on id 1 and check for a GET request and send it to the repeater. You will find a token in the response tab when you search for an id 10. 
Use that token as a cookie with the help of "ffuf". You will find one endpoint i.e. "api".

It says API error, so try and look for any GET requests through request bin. You will find the nineth flag with the help of "api" endpoint. The GET request will also provide you with a X-token. 

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/86f47f79-1a8b-44b3-9446-e34530bed18f)

                                    Flag 9 found in "api" endpoint


### **5. Admin Subdomain Fuzzing**

Head towards the admin subdomain you found during dnsrecon and use the mod header plugin to input a X-token value.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/4063333e-71ee-42d1-a081-7e0575d421a2)


You will be provided with another endpoint called "invoices" for the admin subdomain. Now start up "ffuf" to find out more endpoints of the subdomain with "invoices" endpoint. You will find admin, users, 03, 05, 3 ad 5 as endpoints. Check every endpoint to find the remaining flags.

You will find the tenth flag with the help of the endpoints, with a username and an api key.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/04d6ba39-9cbf-45f6-b068-7fcb3b08f1ea)

                                  Flag 10 found in "admin" directory


Change the X-token value to the api key value you found. Now refresh and you will see there is another secret directory to be included in the URL. 
It provides you a message conversation between two users. You can see that one message has been deleted by the user, find that message by using sqlmap.

The deleted message was the last flag of our challenege.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/c8fd3119-3cea-4ec7-a8a1-60916fafe82c)

                          Flag 11 found in a deleted message from the user

