## Hackbookagram 
https://app.hackinghub.io/hackbook-agram

Usernames and passwords are somehow being stolen from hackbookagram
Find out how they are being stolen, locate the hackers servers and trash their cache of usernames and passwords.

Steps: 

* When we land on the page we can see our home page with the URL http://kwnvej8w.hackbookagram.com/ 

![Homepage](<Home Page.png>)

* Let's see what they have given us in the Page Source

![Tag](<Google Tag.png>)

* We can see something unusual in te source code. They have provided us a google tag and and a URL with the called googletagmaneger. Now the spelling is wrong here so seems like something must be there on that website. We open the link and find some javascript which is hard to understand. 

![JS](Javascript.png)

* We copy the whole script and try to beautify it a little.

![Beauty](Beautify.png)

* We can see here a URL of Hackbookagram with the login page and we find an endpoint "event" within the googlemaneger tag. Let's visit this tag with the endpoint.

![End](Endpoint.png)

* We get a blank white page on this website and nothing else. One thing we can think about is that, maybe there are more parameters than "e" in the website. So let's try to search for our parameters by Fuzzing googletagmaneger.

![Fuzz](FUZZ.png)

![Para](Parameter.png)

* We get our parameter named "include". Let's see what result we get after we include it in the URL.

![Flag 1](<Hackabook Flag 1.png>)

* We found our first flag and some directories leading to a php file.

* Let's check the IP address for the tag googletagmanager.

![IP](IP.png)

* We visit the IP address and find a webpage.

![Nginx](Nginx.png)

* Here we can paste the directories for the php file.

* We get a 404 error, so let's check the other directories, we find one called "datacollection". Let's FUZZ it and find out what all content it includes.

* We got a lot of information here, now let's try opening them on the URL. Everyone is giving a 404 error except the ssl parameter.

![SSL](SSL.png)

* Here we can see a text file called Flag.txt, we get our second flag here.

![Flag 2](<Hackabook Flag 2.png>)

* Alon the flag we got some files including a private key which can be used while decrypting something. 

* Let's come back to the google tagand the parameter "e" and try XSS on it so let's come back to that website and now we need to insert a username and password value. Let's create a payload first by using Cyber Chef.

* Let's use image tag as a payload for XSS. 

![XSS](XSS.png)

* Now let's paste the output base 64 form in the google tag and check for any GET request.

![GET](<GET Request.png>)

* This is the GET request where we can see there is a different IP address given, let's visit that IP address.

![Flag 3](<Hackabook Flag 3.png>)

* Here we got our third flag and a button called "Test Connection", hit the button and check burp suite for the response. 

![Test](<Test Connection.png>)

* Send the request to repeater and in the request tab we can see that they have said there is a node called ns1. So it must be a router and trying to connect somewhere.

* We can try to including different common IP addresses instead of the node value and check the response.

![Response](Response.png)

* Here you can see that we have found some username and password. Also a source called "/js/private.js". Let's request this response in the browser.

![Network](Network.png)

* Check the source code for the source "/js/private.js" and open it.

![DNS](DNS.png)

* There are two endpoints given here and the main is the DNS. We can change the dns server to our dns server to check the content and the requests.

* We will head back to burp suite again and include the endpoint to the ip address and change it to our server.

![Dns changed](<DNS Changed.png>)

