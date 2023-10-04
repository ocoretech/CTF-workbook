
## VulnForum
   https://app.hackinghub.io/vuln-forum
   
Come and join the conversation on this vulnerable forum. Can you take over the admin account and view the secret messages? 

Steps:


* To start this challenge we have to start the server and we are redirected to the page.


* On the landing page we can see some public forums, and some notices and some comments from toby.


* If we check the comments. we can see toby saying how it's a closed group.


* On the home page, we can see a login button too, so let's try logging with random credentials.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/9760a364-cc75-4d78-9485-d2a2b1f0becf)


* When we click on login, it gives us an error message saying "Invalid username or password".


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/35db11ff-4870-4d10-86bb-b9a04d5702eb)


* We check Burp Suite for the post request of login and send it to the repeater.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/913512fa-c260-4c37-a75b-f2addc64cfe6)


* Here you can see the credentials i used for login, and the method used here is local. Let's send the same request again and check the response.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/166bb2f0-1ef6-482a-8a87-1f75fc901161)



* We get the same response with the method "local". Let's change "local" to "remote" and send the same request again.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/e1be963c-7a27-47e9-8054-41a0ab890271)
                <h2><figcaption>Flag 1 Found (File Inclusion Vulnerability)</figcaption></h2>




* You can see, we got our first flag and a URL. Let's visit this url.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/4e849a60-606d-44f0-ae8e-056ed3255b6e)




* Let's try to find the subdomain of this URL with help of nslookup. We get the domain and visit the website.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/cc19d407-3439-4342-9873-4eeec70ae942)
 <h2><figcaption>Flag 2 found on Authentication page</figcaption></h2>


* Now here we have our second flag. Now let's create an account and and hit enter.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/afc7644a-8d32-413b-95c3-f2e1781fc69f)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/182f2135-25cc-4152-858b-32e0e0f69cb6)


* Now we go back to the URL, where it says Invalid Domain. Refresh the page and you will get a login page, where you can login with tha same credentials you used to create the new account.


* After logging in, we can create a new user. But before let's go to the home page and click on toby and copy the hash value in the URL.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/274d7b37-b714-4f27-b4ac-12571d229213)


* Now create the user for toby and paste the hash value in the text box of Remote UUID.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/f5e1cd65-dc92-4fd7-ae1b-8f0085396a9c)


* No go back to the home page and login with these credentials.


* Before logging in, turn intercept on in burp suite, and the press login. You have to change the method to remote and forward it to the login page. Now you are successfully logged in Toby's account and got your third flag.



![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/b273659d-386f-4c6f-ad1d-aa5e3b5bec2f)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/075ade75-c131-4c70-83ee-c4f2dd66e0e7)
  <h2><figcaption>Third flag found by logging in Toby's account</figcaption></h2>


* Here on the homepage we can see another comment in the group by John, who is the admin.


* We try to do the same thing to login as john, by creating hi user and login credential, but it doesn't work. 


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/47086bea-c522-4fa2-89d6-7a805546b4a0)


* Let's head towards the conversation of toby and john.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/d253139f-e41a-4d78-8098-92d2fb00b4fc)


* Here Toby has added a new feature to allow us to change the password. So let's change toby's password by going through the profile settings.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/e68f5e6f-de8f-4c9e-8a40-92d305aa3475)


* You can see that the password has been changed. Now let's check burp suite to see if the password has been changed. We can see a GET request, send it to the repeater. We have got a authenticated token number and our new password with toby's hash value.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/51603c65-1002-4e34-8005-880330c5b78b)


* Let's write a comment to john for e.g."Hello".


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/d524b0ff-879c-4812-ad94-4ef59ed00c20)


* After we wrote a comment, John has replied an auto-generated message. Let's check the page source. 


* While checking the page source, we can see that the challenge has mention about a plugin and a URL linked to Github, let's chek it out.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/11c3ab2f-d612-44cd-abb3-a98cf6bb9331)


* On Github we can see there is a configuration file. There are some tags given which can be used while writing a comment to john.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/2e3a74cd-0e8a-4db5-96e3-449ce55b7a2f)


* Head over to the comments tab, and let's use img as a javascript to send a comment to john.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/f3a61bbf-982e-462a-bd34-fd9c99fe3c75)


* This was just an example, but what if we send our password change GET request in the form of JS as an Stored XSS.
  
  

* Go back to burp suite and find the request of password changed in the repeater tab. Now change the hash value of Toby to John's hash value.
  

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/d1c5a5d0-1f43-49de-bf36-301625e67d1d)


* Now copy this URL and write a script with the use of IMG tag.
  

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/c0df35ea-c242-474e-b126-d68fb46e9d1c)
 <h2><figcaption>Using Stored XSS for changing the password</figcaption></h2>


* With the help of this comment, whenever John will send the automated reply, his password will change to "hello123".
  

* Check when he replies, and then click on logout, and log in John's account with the new password.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/4a8ac19d-2aeb-4a90-88e6-a1473ecb0e95)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/a40e7304-4039-4148-96ee-c9090243befb)
 <h2><figcaption>Last flag found with the help of Stored XSS</figcaption></h2>

* And this is where we find our final flag.
  














