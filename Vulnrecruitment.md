## Vulnrecruitment
https://app.hackinghub.io/vuln-recruitment

This recruitment company has a serious security problem but you'll have to dig into its past staff members to work out how to get in.

Steps: 

* When we land on the page we can see our home page with the URL http://dxmhcfxk.vulnrecruitment.ctfio.com/

![Homepage](Home.png)

* For searching the subdomains we use dnsrecon on the vulnrecruitment URL.
We get 2 results and find our main domain and a subdomain "admin.dxmhcfxk.vulnrecruitment.ctfio.com". We visit the the subdomain URL and it shows the following message.


![Domain](Subdomain.png)


* We try to use theharvester tool for gathering information about vulnrecruitment.co.uk

![Harvest](Harvester.png)

* We found an interesting URL, two IPs and two hosts. We now use curl to find further information in the interesting URL.

* We visit the interesting URL we found and find our first flag on the website.

![Flag1](RecFlag1.png)

* We use fuzzing to find endpoints for our domain.

* We find 3 endpooints: css, js, and staff.

* Let's try fuzzing staff as an endpoint too.

![Portal](Portal.png)

* Let's try adding the endpoint portal to the staff page of our domain.

![Portal](<Staff Portal.png>)
 
* By adding portal endpoint to the staff page redirects us to staff login page, let's try logging in with the three users on the page and see if it logs in. It's saying incorrect password, let's check for the login request in burp suite.

![Login](<Portal login.png>)

* We perform brute force using burp to find ou the correct password.

![Brute](<Brute force.png>)

* We can see clearly that the password for this particular email is thunder. Now let's login on the portal.

![OTP](OTP.png)

* It says that they have sent us a four digit code and we have three attempts to to enter it to continue. 

* After logging in, we get our next flag and a conversation betweeen archie and amelia, who is not working in vulnrecruitment now.

![Convo](Conversation.png)

* Here we can see Amelia's email address which can be used to login into her account. Let's brute force and find her password to login.

![Amelia](<Amelia's Password.png>)

* We login into her account and there is a question given, until we don't answer correctly, we can't log in.

![Pub](Pub.png)

* We find some coordinates of a place by fuzzing a new endpoint.

* Those coordinates lead to a pub called " The New Welcome Sailor". We will try this name as an answer for our question.

* We found our next flag after logging in and an uploads sections where it says download the listing.

![Upload](Uploads.png)

* We check for a POST request for uploads. And in that we find a JSON file and how it can work as a vulnerabilty. If we change that to redirect to our admin domain, then we can access the files on that domain.

* Let's send the the request to repeater and change it into a redirect like CSRF vulnerabilty with our admin domain. Let's send this request and check for the response. Here we have got our last flag in the var files section.

