
## VulnForum
Come and join the conversation on this vulnerable forum. Can you take over the admin account and view the secret messages? 

Steps:

* To start this challenge we have to start the server and we are redirected to the page.

* On the landing page we can see some public forums, and some notices and some comments from toby.

* If we check the comments. we can see toby saying how it's a closed group.

* On the home page, we can see a login button too, so let's try logging with random credentials.

![Login](Login.png "D:\CTF Images\VulnForum\Login.png")

![UserLogin](<Login 1.png> "D:\CTF Images\VulnForum\Login 1.png")

* When we click on login, it gives us an error message saying "Invalid username or password".

* We check Burp Suite for the post request of login and send it to the repeater.

![GET](<Get Request.png> "D:\CTF Images\VulnForum\Get Request.png")

* Here you can see the credentials i used for login, and the method used here is local. Let's send the same request again and check the response.

![Local](Local.png "D:\CTF Images\VulnForum\Local.png")

* We get the same response with the method "local". Let's change "local" to "remote" and send the same request again.

![Remote](Remote.png "D:\CTF Images\VulnForum\Remote.png")

* You can see, we got our first flag and a URL. Let's visit this url.

![Invalid](Invalid.png "D:\CTF Images\VulnForum\Invalid.png")

* Let's try to find the subdomain of this URL with help of nslookup. We get the domain and visit the website.

![Auth](Vulnauth.png "D:\CTF Images\VulnForum\Vulnauth.png")

* Now here we have our second flag. Now let's create an account and and hit enter.

![Credentials](Credentials.png "D:\CTF Images\VulnForum\Credentials.png")

![Created](Created.png "D:\CTF Images\VulnForum\Created.png")

* Now we go back to the URL, where it says Invalid Domain. Refresh the page and you will get a login page, where you can login with tha same credentials you used to create the new account.

* After logging in, we can create a new user. But before let's go to the home page and click on toby and copy the hash value in the URL.

![Hash](<Hash value.png> "D:\CTF Images\VulnForum\Hash value.png")

* Now create the user for toby and paste the hash value in the text box of Remote UUID.

![Newuser](Toby.png "D:\CTF Images\VulnForum\Toby.png")

* No go back to the home page and login with these credentials.

* Before logging in, turn intercept on in burp suite, and the press login. You have to change the method to remote and forward it to the login page. Now you are successfully logged in Toby's account and got your third flag.

![Success](Successful.png "D:\CTF Images\VulnForum\Successful.png")

![Flag](Flag-1.png "D:\CTF Images\VulnForum\Flag.png")

* Here on the homepage we can see another comment in the group by John, who is the admin.



