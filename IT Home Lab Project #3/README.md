# Creating Active Directory Account User

- In this project I will be showing you to create a user account in Active Directory on a Windows Server. The user we will create will be assigned the same access and permissions as an administrator.

![Windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Gx8IjvGazVI7hM0UIWoTFg.jpeg)

> **What you will need:**

- A computer with Hyper-V and Windows Server 2016 installed.
- Desire to learn something new.

## 1. Step 1: Login and Open Server Manager

- Open up Server Manager and under the “Tools” tab select the “Active Directory Users and Computers”. We will create an Active Directory User and assign this user with a permissions to be able to access certain files within an organization, as if they were working for an actual workplace.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*5VFtQbeyWNu3r1aYp_pTsg.png)

## 2.Step 2: Copying Administrator Permissions

- Under the Active Directory Users and Computers, select “Users”. For the user we will be creating will assumed the same permission policies as the administrator.
- Click on “Administrator” and right click to bring up the menu. Click “Copy” to bring up the user properties.

![winows servers](https://miro.medium.com/v2/resize:fit:720/format:webp/1*kWbukY0W022Ke5JPUa4uBg.png)

## 3. Step 3: User Account

- The user creation menu will open up, where you will enter the user information. For the first name and logon name, enter “helpdesk” and click next.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Xsk8FBg31D7jKtuLL-B7mg.png)

## 4. Step 4: Create a password for the User

- Choose a password for the new user. For the project, I recommend you use the same password as the one you made for the Windows server login.
- Click “Next”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*FhIzakZ4Imu20h3tbRkdzQ.png)

## 5. Step 5: Review

- Review everything and click “Finish” to complete the user creation.

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*knzFfCNlpQKPfVlf2BRo1Q.png)

## 6. Step 6: Verify User Account

- Under the users directory you should see the user “helpdesk” account that we just created. Under the helpdesk user properties you will see all the things that the user has access to. You can see that “helpdesk” has the same membership access as the system administrator.
- Click “ok”

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*v1Mra8eJhy741eoQeGe_6A.png)
![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*b2KHaVHqkq7xzgbxHgwlyg.png)

## 7. Step 7: Test Command on the Command line

- There may come a time when you will have to use the command line to verify a user’s account and Important metadata about the server
- On the command line enter the following:

````powershell
ipconfig /all
````

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Qejrw1u1utH5l-l9K2PS-A.png)

- The following command will bring up more data in regards to the users in the active directory. Using the command line we will bring our helpdesk user account and see info in regards to it.
- This command is extremely useful to quickly get information in regards to a user’s account info and what things they have access to.

````powershell
net user helpdesk /domain
````

![windows](https://miro.medium.com/v2/resize:fit:720/format:webp/1*RGbUOFAOl63xXgXAWL8CqA.png)