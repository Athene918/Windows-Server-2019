# Renaming Windows PC and Installing Active Directory Domain Services

- In this project I will be showing you how to rename the Windows server default from the default name to a recognizable and easier to remember name. Lastly, I will show you how to install Active Directory Domain Services onto the Windows server.

> - What you will need

1. A personal computer with internet access
2. VirtualBox and Windows 2019 server installed

## 1. Step 1: Log into Windows server & Change Windows Server Name

- Login into the Windows server through VirtualBox and navigate to “File Explorer” application and open it up.
- In “File Explorer” on the left hand side of the menu, right click on “This PC” and select the “Properties” tab. This is where we have the ability to change the name of the server.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*ttxcN2ao0MUaH3UaStw0og.png)

Take a look at the System information and you will get the important info in regards to the Windows

- On the right hand side of the display page, under the Computer name, domain, and workgroup settings tab you will see the option to change settings. Click on “change settings”.
- As you can see the default computer name is long and we are going to change it and make more personable.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*0Mbn441I4E8qsg7bqbqINQ.png)

The System Properties tab has functionalities that will allow you to make changes to the Window server. For now all we are concerned with is changing the name.

- Click “change”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*RpmT0denBPJ2bKCQ_l0WKQ.png)

Enter your desired name for the server

- Enter your desired name, leave the rest of the settings on the default and select ok

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*s-DHofRovq0pJefI3v1x7g.png)

- The changes will take place after you restart the server

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*30aKVXWvOM96NOWXJlPlxg.png)

- When prompted restart the server

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*5GY3n-ub-hwH_E5tiJRLdw.png)

- After restarting the server and logging back in. Navigate to the file explorer and you should see the server/computer name updated to the one you chose!
- Now you know how to rename your server/computer. You may have thought this was a minor accomplishment, however, in the future this will help you stay organize and know how to quickly troubleshoot a specific PC when you are working for an organization where there are hundreds of PCs.

![windows](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*XtSQ-Kv3oQLwFhMFPCp57Q.png)

## 2. Step 2: Add Roles and Features for Active Directory

- Open Server Manager from the bottom menu, Click on the Mange tab and select “Add roles and features”

![windows](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*ZVSBas0NPLT4gQUI52ZKdw.png)

- The Add Roles and Features Wizard allows for installation of services and features that can you provide all the proper resources an organization needs to thrive successfuuly. In this project we will be using it to install Active Directory.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*ToivOzJ-z8Mymy9zXZH5wQ.png)

- Select the “Role-based or feature-based installation”.

![windows](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*WIEtuN8xTeRhE7gB9nL_4A.png)

- Select the server. You should only have one server since that is all we made.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*OxaFINAYxtAmzV_sgmDePA.png)

- Under server roles select the option for “Active Directory Domain Services”. You will see by default other roles that will be part of the installation, do not worry about them we are only concerned with getting Active Directory Domain Services on our server.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*p5fO7RTE4lfGQ9sfYB-SZA.png)

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*knslv6Xsh7NamZ_bjTm3kw.png)

- The installation confirmation page will display all roles and services that will be installed.
- Click “Install”. The installation will take anywhere between 5–10mins depending on your system settings. The system will automatically restart the server to apply all the new changes!

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*wVL1lH6HjizFVj9_peAgfw.png)

- Server is restarting and applying all the new changes. If all goes well, we will have a server with Active Directory Domain Services installed.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*jKvJy-6TlobogcscIlmNTA.png)

- The Active Directory Domain Services needs a domain controller and since we do not have one we will promote our server as the controller.
- For context, Active Directory Domain Services is like a digital manager for computer stuff. It helps control who can use computers in a big group, like a school or a company. It keeps track of usernames, passwords, and what people are allowed to do on the computers. It’s kind of like a gatekeeper that keeps everything organized and secure.
- A domain controller is like a boss computer in charge of a group of computers. It decides who’s allowed to use the computers, keeps everyone’s info safe, and makes sure things run smoothly in an organization.
- Click on “Promote this server to a domain controller”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*aBZi8tTnwApLawMtE1wUvA.png)


## 3. Step 3: Active Directory Domain Services Configuration

- For the deployment operation we will create a new forest and create a demo domain name for this server.
- a “forest” is a collection of connected computer networks. These networks share the same rules and security, making it easier to manage users and resources across them. It’s like a digital community of computer neighborhoods, all under one management system.
- I chose my name as the domain name. Create your own.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*i1BycnniuwiAMtd_zgbSYQ.png)

Domain Controller Options

- You will be prompted to enter a password for the Directory Services Restore Mode. Use the same password that you use to log into the Windows server.
- For context, The “Directory Services Restore Mode” (DSRM) password is a special password used to access a Windows Server in a mode that allows you to repair or restore Active Directory Domain Services if there’s a problem. This mode is used when the normal startup of Active Directory isn’t working properly, and the DSRM password is required to make important changes to fix it. It’s like having a secret key that can unlock a special toolbox for fixing serious issues in a Windows Server’s directory services.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*dR5_EoVerrdGH4Y1ggUjmw.png)

DNS/Additional Options

- The server will automatically assign the NetBIOS domain name based upon the server name.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*qFN2iOZ6ykOikhk-6P2qzw.png)

- Leave the default path settings as is and click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*xFnZ8J23979Hlin7gvgSCw.png)

- Review page is the final stage before everything is fully configured on the Active Directory Domain Services.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*0uBJOFJ8xoHQpxeJR7fs1g.png)

- The Pre-reqs check shows that our Windows server needs some attention in various areas, however we are not going to worry about any of that at this time. Click “Install”.

![wiindows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*L85_33YIXbFBoqFeJB3rfQ.png)

- After installation our server will restart and the first thing you should notice is the domain name present in the Windows login screen!
- Log into the server so that we can verify that Active Directory Domain Services was indeed installed with no issues.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*6UXZL9a1TUiJdgfpIWVxTQ.png)


## 4. Step 4: Verification

- In Server Manager, under “Tools”, Click on “Active Directory Sites and Services”. Here is where you see the Active Directory Domain Services.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*ucJTHGoZ-tELNSjTVyIjDg.png)

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*AVg0NOs1RFc8sdXUXlpI7g.png)