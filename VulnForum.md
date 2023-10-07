
## [VulnForum](https://app.hackinghub.io/vuln-forum)

### **Objective:**  Take over the admin account and view the secret messages.

### **Solution:**


### **1. Reconnaissance**


On the landing page you can see some public forums, and some notices and some comments from Toby. If you open the comments section, you can see that Toby is talking about how it's a closed group. On the home page, there is a login button too, try logging with random credentials.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/9760a364-cc75-4d78-9485-d2a2b1f0becf)


Click on login, it gives you an error message saying "Invalid username or password".


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/35db11ff-4870-4d10-86bb-b9a04d5702eb)


Check Burp Suite for a POST request of login and send it to the repeater.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/913512fa-c260-4c37-a75b-f2addc64cfe6)


You can observe the credentials i used for login, and the method used here is local. Send the same request again and check the response.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/166bb2f0-1ef6-482a-8a87-1f75fc901161)


You will get the same response with the method "local". Let's change "local" to "remote" and send the same request again.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/e1be963c-7a27-47e9-8054-41a0ab890271)
                          
                          Flag 1 found(File Inclusion Vulnerability) 




We found our first flag and a URL. Visit this url.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/4e849a60-606d-44f0-ae8e-056ed3255b6e)


Try to find the subdomain of this URL with help of nslookup and visit the website.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/cc19d407-3439-4342-9873-4eeec70ae942)

                            Flag 2 found on Authentication page


Here you found the second flag. Now create an account and hit enter.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/afc7644a-8d32-413b-95c3-f2e1781fc69f)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/182f2135-25cc-4152-858b-32e0e0f69cb6)


### 2. **Logging in as Toby**


Go back to the URL, where it says Invalid Domain. Refresh the page and you will get a login page, where you can login with tha same credentials you used to create the new account.


After logging in, create a new user. Before creating a user, head back to the home page and click on Toby and copy the hash value in the URL.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/274d7b37-b714-4f27-b4ac-12571d229213)


Now create the user for Toby and paste the hash value in the text box of Remote UUID.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/f5e1cd65-dc92-4fd7-ae1b-8f0085396a9c)


Before logging in, turn intercept on in burp suite, and then press login. You have to change the method to remote and forward it to the login page. Now you are successfully logged in Toby's account and found your third flag.



![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/b273659d-386f-4c6f-ad1d-aa5e3b5bec2f)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/075ade75-c131-4c70-83ee-c4f2dd66e0e7)

                          Flag 3 found by logging in Toby's account


On the homepage you can see another comment has been added in the group by John the admin. Try to do the same thing to login as John, by creating his user and login credential, but this time it didn't work. 


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/47086bea-c522-4fa2-89d6-7a805546b4a0)


Head towards the conversation of Toby and John.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/d253139f-e41a-4d78-8098-92d2fb00b4fc)


Toby has added a new feature to allow you to change the password. Change Toby's password through the profile settings.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/e68f5e6f-de8f-4c9e-8a40-92d305aa3475)


You can see that the password has been changed. Now check burp suite to see if the password has been changed. You can see a GET request and then send it to the repeater. You will find an authenticated token number and our new password with Toby's hash value.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/51603c65-1002-4e34-8005-880330c5b78b)


Write a comment to John for e.g."Hello".


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/d524b0ff-879c-4812-ad94-4ef59ed00c20)


John has replied an auto-generated message, check the page source. You can notice that the challenge has mentioned about a plugin and a URL linked to Github, let's check it out.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/11c3ab2f-d612-44cd-abb3-a98cf6bb9331)


On Github there's a configuration file. There are some tags given which can be used while writing a comment to John.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/2e3a74cd-0e8a-4db5-96e3-449ce55b7a2f)


Head over to the comments tab, and you can use 'img' as a javascript to send a comment to John.


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/f3a61bbf-982e-462a-bd34-fd9c99fe3c75)


This was just an example, but what if you send the password change GET request in the form of JS as an Stored XSS. Go back to burp suite and find the request of password changed in the repeater tab. Now change the hash value of Toby to John's hash value.
  

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/d1c5a5d0-1f43-49de-bf36-301625e67d1d)


Now copy this URL and write a script with the use of IMG tag.
  

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/c0df35ea-c242-474e-b126-d68fb46e9d1c)

                          Using Stored XSS for changing the password


With the help of this comment, whenever John will send the automated reply, his password will change to "hello123". Check for his reply, and then click on logout, and log in John's account with the new password.

![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/4a8ac19d-2aeb-4a90-88e6-a1473ecb0e95)


![image](https://github.com/ocoretech/Sahil-workbook/assets/67775716/a40e7304-4039-4148-96ee-c9090243befb)

                          Last flag found with the help of Stored XSS

This is where we find our final flag.
  














