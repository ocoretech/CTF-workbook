## Vulnrecruitment
https://app.hackinghub.io/vuln-recruitment

This recruitment company has a serious security problem but you'll have to dig into its past staff members to work out how to get in.

Steps: 

* When we land on the page we can see our home page with the URL http://dxmhcfxk.vulnrecruitment.ctfio.com/

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/81b1385b-4086-450d-a929-75c3a3ea6580)

<h2><figcaption>HomePage</figcaption></h2>


* For searching the subdomains we use dnsrecon on the vulnrecruitment URL.
We get 2 results and find our main domain and a subdomain "admin.dxmhcfxk.vulnrecruitment.ctfio.com". We visit the the subdomain URL and it shows the following message.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/42f18fc0-7210-42bb-a801-ad29ab1b4732)



* We try to use theharvester tool for gathering information about vulnrecruitment.co.uk

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/717df765-582e-4a5f-8f13-f9090afdb507)


* We found an interesting URL, two IPs and two hosts. We now use curl to find further information in the interesting URL.

* We visit the interesting URL we found and find our first flag on the website.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/78483c32-7bf5-49bf-b9fd-292eb3a336f1)
 <h2><figcaption>Flag 1 found on the new subdomain.</figcaption></h2>

* We use fuzzing to find endpoints for our domain.

* We foundd three endpoints: css, js, and staff.

* Let's try fuzzing staff as an endpoint too.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/c824a368-4944-499c-a4d1-778e1c6ad136)


* Let's try adding the endpoint portal to the staff page of our domain.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/17aaea8c-238d-4f23-8b52-db80546923d2)

 
* By adding portal endpoint to the staff page redirects us to staff login page, let's try logging in with the three users on the page and see if it logs in. It's saying incorrect password, let's check for the login request in burp suite.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/e8f140dc-fac2-4193-bce1-67224235a768)


* We perform brute force using burp to find ou the correct password.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/f8d04833-ba41-44bc-ac8f-bdb607eac547)


* We can see clearly that the password for this particular email is thunder. Now let's login on the portal.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/73e487e1-182c-46c4-a082-4e4adc7187be)


* It says that they have sent us a four digit code and we have three attempts to to enter it to continue. 

* After logging in, we get our next flag and a conversation betweeen archie and amelia, who is not working in vulnrecruitment now.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/271c30e9-1ed3-47bd-9380-5582ff1d0a4d)
<h2><figcaption>Brute Force Vulnerability for second flag</figcaption></h2>


* Here we can see Amelia's email address which can be used to login into her account. Let's brute force and find her password to login.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/0b917833-9128-4c3f-8899-63b0340e256d)
<h2><figcaption>Brute Force attack to find the password</figcaption></h2>


* We login into her account and there is a question given, until we don't answer correctly, we can't log in.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/b33cb6cb-5173-4ff3-add8-761d55ec988e)


* We find some coordinates of a place by fuzzing a new endpoint.

* Those coordinates lead to a pub called " The New Welcome Sailor". We will try this name as an answer for our question.

* We found our next flag after logging in and an uploads sections where it says download the listing.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/85eadd75-a277-407a-bfdc-69d009d410a2)
<h2><figcaption>Found the third flag by brute forcing</figcaption></h2>

* We check for a POST request for uploads. And in that we find a JSON file and how it can work as a vulnerabilty. If we change that to redirect to our admin domain, then we can access the files on that domain.

* Let's send the the request to repeater and change it into a redirect like CSRF vulnerabilty with our admin domain. Let's send this request and check for the response. Here we have got our last flag in the var files section.

