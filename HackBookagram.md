## [Hackbookagram](https://app.hackinghub.io/hackbook-agram) 


### **Objective:** 
Usernames and passwords are somehow being stolen from hackbookagram. Find out how they are being stolen, locate the hackers servers and trash                their cache of usernames and passwords.


### **Solution:**


### **1. Reconnaissance**


Check the page source of the homepage.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/dbaf8745-032e-412d-88e9-022465b3d588)


You can see something unusual in the source code. They have provided us a URL called googletagmaneger. Open the link and you will find some javascript. 

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/87b8c35a-d548-4249-afb3-6959edcb4288)


Copy the whole script and try to beautify it a little with help of online free tools.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/2af1eb88-5eaa-4337-8bcd-981333327202)


Here you find a URL of Hackbookagram with the login page and an endpoint "event" within the googlemaneger tag. Visit this tag with the endpoint.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/a1c6cfed-a689-423e-aa3d-35d65e2c5652)


You will get a blank white page on this website and nothing else. One thing about this is that, maybe there are more parameters than "e" in the website. So try to search for other parameters by fuzzing googletagmaneger.

### **2. Finding parameters**


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/1578b0e3-f49d-478d-8b45-3fe1a1fb5ac6)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/04216139-b16d-4fcf-80b1-931f637f9ff4)


You will find your parameter named "include". Let's see what result we get after we include it in the URL.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/4cf8c97a-9262-4d93-b3ef-87408f14e3e0)

                              Flag 1 found by using the tool FUZZ

First flag was found and some directories leading to a php file. Check the IP address of googletagmanager.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/48f3eb61-8174-45cb-bc1b-65df71ad0ea6)

                              

Visit the IP address and you will find a webpage that says "Welcome to nginx".

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/747c6937-9aea-46e9-be89-a27d10657cdb)


Here you can paste the directories for the php file. You will get a 404 error, so check the other directories. You find one directory called "datacollection". Try fuzzing it and find out what all content it includes. Some information has been found, try opening them on the URL. Every endpoint is giving a 404 error except the ssl parameter.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/bd3c845e-c27b-46ee-b2a3-bb91fd6e5e2c)


 You will find multiple text files and in that includes our second flag in a text file called Flag.txt.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/c776e982-fa83-48b0-b521-2c71cab91464)

                                Flag 2 found with the use of ssl endpoint
 

### **3. Performing XSS**


Come back to the googletag and the parameter "e" and try to use XSS on it. You need to insert a username and password value. First create a payload by using Cyber Chef. Let's use image tag as a payload for XSS. 

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/76b08714-7979-4a05-b74b-05204f54cd1d)


Paste the base 64 form in the googletag and check for any GET request.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/1f53bdf9-6bb4-4cec-a8b3-60e4257cd7bc)



This is the GET request where we can see there is a different IP address given, visit that IP address.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/31980d44-a383-4d77-89aa-b198368dd05c)

                                    Flag 3 found by using XSS


Here we got our third flag and a button called "Test Connection", hit the button and check burp suite for the response. 

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/f74cc87b-9b92-458c-8ecb-3971cbfa3a17)


Send the request to repeater and in the request tab you can see that they have said there is a node called ns1. It must be a router and trying to connect somewhere. You can try to include different common IP addresses instead of the node value and check for the response.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/1db6b2f1-796c-4a79-bc38-048570da8e3d)

Here you can see that we have found some username and password. Also a source called "/js/private.js". Request this response in the browser.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/3d6aa7d8-4300-46f4-9b2d-a00a4d04491a)


Check the source code for the source "/js/private.js" and open it on the URL.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/d287fe24-b902-4bcd-804f-8fd1832b80b8)


### **4. Changing the DNS Server**


There are two endpoints given here but we will focus on the DNS endpoint. You can change the dns server to your own dns server to check the content and the requests. Head back to burp suite and include the endpoint to the ip address and change it to your server.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/1aa125ea-b65a-44b1-9417-fc19cad08ed5)

Head back to index of datacollection. Here you can see that we are given with different certificates, a fullchain containing all the certificates and a private key, download them. With the use of ncat, use the fullchain.pem and the privkey.pem as the certificates and key to find out our GET request, host and a X-token.
Head to the host website i.e. www.googletagmaneger.com and use mod loader to add a request header X-token with the value. Now let's change our endpoint to our newly found GET request i.e. /api/poll and hit enter. You find the fourth flag here and description saying the latest usernames and passwords.

                                                Flag 4 found by using private key


Try fuzzing out X-token for a GET request as well as POST request. You find another endpoint called cookie, insert that in the url and check for the results.

It says Invalid Endpoint, try using curl on the same POST request and see what content you can find through it. You will find some data in the descryption called "Login Cookie". You will find the cookie here and the fifth flag.

                                                Flag 5 found by fuzzing the X-token

On the googletagmanger website, try to see if there is a login page, and there is one after searching. Now we don't have the credentials but we we have the authentic cookie. So insert some random credentials here and click on login. Now check burp suite for our login request and send it to the repeater. In the response tab we can't see a different cookie through which we can try to log in.

You can try another thing, turn on the intercept on burp suite and check if there is a logout page on the domain. Check the response on burpsuite and here you can see that there is a different cookie called "user-login-cookie=deleted". Now insert our authentic cookie instead of "deleted" in the burpsuite and forward that request. On the domain we have logged in and we can see there is a dashboard containing different usernames and passwords and a delete records button.

Click on the button and you will find your final flag with the challenge being solved



