## [Vulnrecruitment](https://app.hackinghub.io/vuln-recruitment)

### **Objective:**   
Dig into the past staff members to work out how to get in.

### **Solution**

### **1. Reconnaissance**

Search for subdomains by using dnsrecon (dnsrecon -d vulnrecruitment.co.uk -D CTF/subdomains.txt -t brt). It will display 2 results, you will find the main domain and a subdomain "admin.dxmhcfxk.vulnrecruitment.ctfio.com". Visit the the subdomain URL and it displays the following message.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/42f18fc0-7210-42bb-a801-ad29ab1b4732)



Use "theHarvester" tool for gathering information about "vulnrecruitment.co.uk"(theHarvester -d vulnrecruitment.co.uk -b all).

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/717df765-582e-4a5f-8f13-f9090afdb507)


You will find an interesting URL, two IPs and two hosts. By visiting our new URL, we find the first flag.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/78483c32-7bf5-49bf-b9fd-292eb3a336f1)

                               Flag 1 found on the new subdomain


### **2. Searching for endpoints** 

Try using fuzzing to find endpoints for the domain (ffuf -w CTF/content.txt -t 2 -p 1.0 -H "Cookie: $cookie" -u http://vulnrecruitment.co.uk/staff/FUZZ). It would take some time to search as there are numerous records to go through. After some time, you can check, the result displays three endpoints: css, js, and staff.

Fuzz "staff" endpoint because the other endpoints aren't working

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/c824a368-4944-499c-a4d1-778e1c6ad136)


Add the endpoint "portal" to the staff page of our domain.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/17aaea8c-238d-4f23-8b52-db80546923d2)


### **3. Brute Force Attack** 
 
By adding "portal" to the staff page redirects us to staff login page, try logging in with the three users on the page and see if it logs in. It says incorrect password. Check for the login request in burp suite.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/e8f140dc-fac2-4193-bce1-67224235a768)


Perform brute force attack by adding a simple list of passwords from passwords.txt given by hackinghub to find out the correct password.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/f8d04833-ba41-44bc-ac8f-bdb607eac547)


You can see clearly that the password for this particular email is "thunder". Now login on the portal with the credentials.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/73e487e1-182c-46c4-a082-4e4adc7187be)
 

After logging in, you find your second flag and a conversation betweeen Archie and Amelia. Amelia is not working in vulnrecruitment at the moment.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/271c30e9-1ed3-47bd-9380-5582ff1d0a4d)

                                     Brute Force Vulnerability for second flag


Here you can see Amelia's email address which can be used to login into her account. Brute force with the same method and find her password to login.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/0b917833-9128-4c3f-8899-63b0340e256d)



Login into her account and there is a question given, until you don't answer correctly, we can't log in.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/b33cb6cb-5173-4ff3-add8-761d55ec988e)


### **4. Searching for Amelia's favourite pub**

You find some coordinates of a place by fuzzing. Those coordinates lead to a pub called " The New Welcome Sailor". We will try this name as an answer for our question. You will find your next flag after logging in successfully and also find an uploads sections where it says download the listing.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/85eadd75-a277-407a-bfdc-69d009d410a2)
                             
                                 
                                   Found the third flag by brute forcing
                                   

Check for a POST request for "uploads". You will find a JSON file and how it can work as a vulnerabilty. If you change that to redirect to our admin domain, then you can access the files on that domain. End the the request to repeater and change it into a redirect like CSRF vulnerabilty with our admin domain. Send this request and check for the response. Here you have found your last flag in the var files section.


### **Common Vulnerabilities in Vulnrecruitment:**
1. Brute Force
2. Cross-Site Request Forgery


### **Tools used:**
1. nslookup
2. dnsrecon
3. theHarvester
4. ffuf
5. BurpSuite


