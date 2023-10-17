## [VulnBegin](https://app.hackinghub.io/vuln-begin)

### **Objective**
Make your way through the challenge capturing the flags.

### **Solution**

Start the Vulnbegin challenge, you will see a landing page where it's written "Welcome There's not much here".


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/91660f88-9883-4039-ae3a-81dd71bd74da)


### **Reconnaissance**

Use nslookup tool to search for any extra information we can get from our domain i.e. vulnbegin.co.uk. With the help of nslookup, you will find your first flag, but to find the subdomains, use dnsrecon brute force.

                                                    Flag 1 found by using nslookup


With the help of dnsrecon, a subdomain has been found. Visit that subdomain and you will find your second flag. You will also notice on the subdomain where it says "User not Authenticated". Try using theHarvester tool to find out more subdomains or more information regarding the flags.

                                                    Flag 2 found using dnsrecon


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/249fd214-5cf2-4f6b-a27d-36dad72f075f)

Here you can see that eleven hosts have been found, go through each of them by visiting the URLs. 


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/7ef67f37-3988-425c-bc10-2b4dee328670)

                                    Flag 3 found by theHarvester


You can see that the third flag has been found with the help of "theHarvester" tool.

### **Searching for Endpoints**

After finding the third flag, search for different endpoints using "ffuf" tool. You will find some endpoints which you can insert it in the URL.
There are two main endpoints "cpadmin" and "robots.txt". 

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/b427b85f-4ec0-4709-abff-efdc624ee366)


Use "robots.txt" endpoint in the URL. It provides us with a directory called "/secret_d1rect0y/". 

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/755b8637-ea5d-4b37-86b3-dd7bdb6d11a6)


Include this directory in the URL and you will find your fourth flag with the help of Fuzzing.


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/8ac008c4-f194-49a4-b9dc-4a8a1e004508)


                                Flag 4 found by fuzzing disallowed directory

### **Brute Force attack**

Come back to the login page and use any credentials to login. You can observe that it says the password is invalid, which means that the username is correct but you have to find out the correct password. With the help of burp suite, use brute force attack to find out the correct password.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/f1675eaf-6a9d-4361-a6c6-2a8999e59f9f)


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/9cf63c4a-ae47-4f28-aae6-48abd449c0c2)

The password has been found, now use this password to login on the login page. 


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/009be33c-ab9e-413d-be83-830092cb7725)

                                Flag 5 found by brute force attack


By logging in you will find the fifth flag here with the help of brute forcing. Inspect the page and you will find a token value. Include this token value while fuzzing it to find more endpoints.
You will find three endpoints : "env", "login", "logout". Search for information in each endpoint by inserting them in the URL.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/b4e77f84-8092-460a-a943-f9f961d34f61)


You will find a X-token and your sixth flag with the help of fuzzing.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/83aa5670-89e2-4ad2-b629-cc2f57020f67)


                            Flag 6 found with the help of fuzzing


Now add this X-token value in the cookie section of the page inspection and use the Mod header plugin to include this token value. Head back to the first subdomain you found and now it says that "User is authenticated" and you will find the seventh flag with the help of the endpoint "env".


![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/08ea6556-e4ea-48f3-8afe-ba7649bde5af)

                            Flag 7 found with the help of the endpoint "env"


Use "ffuf" to find more directories using the X-token as the cookie. You will find two directories : "user" and "robots.txt". Include them in the URL.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/8d9fdca2-e8e6-43a5-bb09-825a5d219037)


Including "robots.txt", you will find another directory which is disallowed. Include the directory in the URL.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/a2b51d6a-e8c6-434c-9c6c-a59630846a05)


Now include the other endpoint "user".

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/973b8278-1f68-4642-a9c6-cd67cb3d6cb5)


By entering different directories provided in the user directory, we find our eighth flag with the help of Fuzzing the X-token.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/0b583fca-31a6-49f9-940d-1a44f6af45ac)


                                    Flag 8 found by fuzzing X-Token


Try searching for any other users by changing the user id.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/b94f9051-85ba-44b8-8c06-ee1dd74fba06)

                            Flag 9 found by changing directory to User id 5


By searching for different users, we find the last flag with help of user id five.
