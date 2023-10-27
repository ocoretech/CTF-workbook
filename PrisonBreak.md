## **[Prison Break](https://app.hackinghub.io/prison-break)**

### **Objective**

Prison's are becoming more modern everyday. This hub will put your recon, javascript and asset discovery into test in order to break into a prison system.

### **Solution**

Starting with the challenge you will arrive at the home page where you can either login or signup.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/208bad85-11f2-404d-9ff6-a07a5187f2cc)


The website provides a backed website named 'http://app-backend.UUID.ctfio.com'. It also provides the the credential to log in the backend website.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/afd0923c-6384-4e21-aebb-4176af4637e7)


After logging in open the page source to gather more information. You will find a javascript which contains several subdomains and directories.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/bb0248e1-ce5c-4289-89f4-bfbf80fa5839)


There are basically two domains, 'docs' and 'admin'. Open them and it will display a login page for both 'docs' and 'admin'. The javascript has also provided us with a directory, insert it into the URL and wait for the output.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/03f20aee-2650-412b-8d59-9de6545ea077)


It will redirect you to the homepage of 'docs' without even logging in and will provide you with some resources and a session token in the URL. 
Now try including the admin domain with the same session token. It will still redirect you to the admin login portal. Use the directories provided along with the admin domain in the javascript file and insert it in the URL.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/c63d46c0-0970-4481-99e2-a1c5ad53123d)


You will be redirected to the admin homepage consisting of various User IDs and their messages. You can find a user with three messages but whenever you try to open the messages, it redirects you to the admin login portal. 

Copy the path of the messages and paste it into the URL with the session token. You will be redirected to details of a particular message.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/a648ad0b-a728-4e0c-88d0-2ad911a026eb)


The messages aren't visible but you can delete the messages part in the URL and a specified user id will be displayed.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/56893045-7f4c-4bfb-b64c-b1d2ede71305)


Check for the javascript in the page source. It provides with another directory to change the password.

![image](https://github.com/ocoretech/CTF-workbook/assets/67775716/09816cbe-bc93-49f9-8c44-f8c2f369f420)


Now insert the new directories and it will display the output as invalid request method. Check burpsuite for the GET request and send it to the repeater. Type the user id and the password in the request and change it to a POST request and hit send.

![Burp](<PB Burp Request.png>)

