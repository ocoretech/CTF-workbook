## VulnBegin

### **Objective**
Make your way through the challenge capturing the flags.

### **Solution**

Start the Vulnbegin challenge, you will see a landing page where it' written "Welcome There's not much here".

![Land](<Landing page.png>)

### **Reconnaissance**

Use nslookup tool to search for any extra information we can get from our domain i.e. vulnbegin.co.uk. With the help of nslookup, you will find your first flag, but to find the subdomains, use dnsrecon brute force.

With the help of dnsrecon, a subdomain has been found. Visit that subdomain and you will find your second flag. You will also notice on the subdomain where it says "User not Authenticated". Try using theHarvester tool to find out more subdomains or anyother information regarding the flags.

![Harvester](Harvest.png)

Here you can see that eleven hosts have been found, go through each of them by visiting the URLs. 

![Flag 2](<Flag 2 begin.png>)

You can see that the third flag has been found with the help of "theHarvester" tool.

### **Searching for Endpoints**

After finding the third flag, search for different endpoints using "ffuf" tool. You will find some endpoints which you can insert it in the URL.
There are two main endpoints "cpadmin" and "robots.txt". 

![admin](cpadmin.png)

Use "robots.txt" endpoint in the URL. It provides us with a directory called "/secret_d1rect0y/". 

![Robots](Robots.png)

Include this directory in the URL and you will find your fourth flag with the help of Fuzzing.

![Flag 4](<Flag 4 begin.png>)

### **Brute Force attack**

Come back to the login page and use any credentials to login.

![Invalid password](<Password Invalid.png>)

You can observe that it says the password is invalid, whic means that the username is correct but you have to find out the correct password. With the help of burp suite, use brute force attack to find out the correct password.

![Brute](<Brute force-1.png>)

The password has been found, now use this password to login on the login page. 

![Flag 5](<Flag 5 begin-1.png>)

By logging in you will find the fifth flag here with the help of brute forcing. Inspect the page and you will find a token value. Include this token value while fuzzing it to find more endpoints.
You will find three endpoints : "env", "login", "logout". Search for information in each endpoin by inserting them in the URL.

![Fuzz env](<FUZZ env.png>)

You will find a X-token and your fifth flag with the help of fuzzing.

![Env](Env.png)

Now add this X-token value in the cookie section of the page inspection and use the Mod header plugin to include this token value. Head back to the first subdomain you found and now it says that "User is authenticated" and you will find the sixth flag with the help of the endpoint "env".

Use "ffuf" to find more directories using the X-token as the cookie. You will find two directories : "user" and "robots.txt". Include them in the URL.

![Robots 1](<Robots 1.png>)

Including "robots.txt", you will find another directory which is disallowed. Include the directory in the URL.

![Secret](<Secret directory.png>)

Now include the other endpoint "user".

![User](User.png)

By entering different directories provided in the user directory, we find our seventh flag with the help of Fuzzing the X-token.

![Flag 7](<Flag 7 begin.png>)

Try searching for any other users by changing the user id.

![User 5](<User 5.png>)

By searching for different users, we find the last flag with help of user id five.
