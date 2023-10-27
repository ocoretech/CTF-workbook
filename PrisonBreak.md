## **Prison Break***

### **Objective**

Prison's are becoming more modern everyday. This hub will put your recon, javascript and asset discovery into test in order to break into a prison system.

### **Solution**

Starting with the challenge you will arrive at the home page where you can either login or signup.

![Homepage](<PB Landing Page.png>)

The website provides a backed website named 'http://app-backend.UUID.ctfio.com'. It also provides the the credential to log in the backend website.

![Backend app](<PB PrisonChat Backend.png>)

After logging in open the page source to gather more information. You will find a javascript which contains several subdomains and directories.

![JS](<PB JS.png>)

There are basically two domains, 'docs' and 'admin'. Open them and it will display a login page for both 'docs' and 'admin'. The javascript has also provided us with a directory, insert it into the URL and wait for the output.

![Docs](<PB Docs.png>)

It will redirect you to the homepage of 'docs' without even logging in and will provide you with some resources and a session token in the URL. 
Now try including the admin domain with the same session token. It will still redirect you to the admin login portal. Use the directories provided along with the admin domain in the javascript file and insert it in the URL.

![Admin](<PB LImited Func Users.png>)

You will be redirected to the admin homepage consisting of various User IDs and their messages. You can find a user with three messages but whenever you try to open the messages, it redirects you to the admin login portal. 

Copy the path of the messages and paste it into the URL with the session token. You will be redirected to details of a particular message.

![Admin Messages](<PB Admin Messages.png>)

The messages aren't visible but you can delete the messages part in the URL and a specified user id will be displayed.

![User](<PB Specified User.png>)

Check for the javascript in the page source. It provides with another directory to change the password.

![New Dir](<PB Message directories.png>)

Now insert the new directories and it will display the output as invalid request method. Check burpsuite for the GET request and send it to the repeater. Type the user id and the password in the request and change it to a POST request and hit send.

![Burp](<PB Burp Request.png>)

