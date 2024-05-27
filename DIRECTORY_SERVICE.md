# THE DIRECTORY SERVICE

## How does Active Directory keep everything organized and facilitate seamless communication between different parts of the network?

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*JfCI7W-PM5bTy63fIfkvcg.png)

- After promoting the server to a domain controller, click on **Tools > Active Directory Users and Computers.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*1ZJQrsjuBo0WfEQYbiHajw.png)

- This console would help us to organize and manage users, computers and resources to allow seamless flow of communication. From this console, we would create **an organizational unit.**
  
## ORGANIZATIONAL UNIT

### Understanding Organizational Units (OUs) in Active Directory

- In the world of Active Directory, an Organizational Unit (OU) is like a special folder that helps us organize and manage different entities, similar to how we organize belongings in different sections. Think of Active Directory as a big library with books representing computers, users, or groups. Without OUs, these books would be scattered, making it hard to find what we need. 

- OUs group similar entities together on specific shelves, such as shelves for computers, users, and different departments or teams. This organization allows quick access to needed resources and enables the application of specific rules or settings to the entities within each OU, such as different permissions or security settings for different groups of users.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*WNRQxdFMuPzcjuLJ0nmQ-Q.png)

- This diagram above gives us a pictorial view of how an OU just like a container will help us organize and manage users and groups and as well assign privileges and rights to each resource.

- In simpler terms, an OU is like a special container that helps us organize and manage things in Active Directory. It keeps everything tidy, makes it easier to find what we need, and allows us to apply specific rules and settings to different groups. So, think of an OU as your personal assistant in Active Directory, helping you stay organized and in control. Let’s get started and create an OU for our company

 ![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*GrWTqx9H2fjQ8hcMzg_-zw.png)

 - Right-click on **CyberRange.local > New > Organizational Unit.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*iqRIgLP90RnLhoqntTlQsQ.png)

- Here, we assume this DC is located at the head office of CyberRange Inc. We type CyberRange-HQ and select OK. We now have successfully created an organizational unit.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*ycZXnpdi0QCT5rq68uglYQ.png)

- The next step is to right-click on CyberRange-HQ > New > Organizational Unit. This is because we assume that this company has different departments within the organization namely; IT Sec, HR and Accounts department all with users (staff/employees) within each department.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*zsmgiPd06cokHLzGwdZPgQ.png)

- Here, we create our first department in the OU as IT Sec Department and select OK.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*5slz9PZowkk19b1r7vSLQg.png0)

- The next step, we use the same method to create OU’s for HR and Account Departments. With all things been equal, you should have something like this.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*i3CpiQkMIfZle6Egxul5Dw.png)

- The next stage is to create users for each department within the OU. Here, we start with the IT Sec so we right-click on that. Select New > User to create a user account.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*9QgVcylTxVNg6jr05PHf4g.png)

- Our user in this department is called Felix Mensah. Fill in the details and choose next to set a password for our user.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*ejsuxJV1OvbZSMaa3Do4mg.png)

- This password will be used by the user to log into his machine whenever he comes to work. Choose password never expires. For our lab we will select this options but in real case scenarios this option should be avoided and have a password policies instead.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*UCy5nkyscltSoXIhaBVKZw.png)

- Finally, we have our user in the IT Sec Department. Go ahead and create two more users for both HR and Accounts department respectively.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*umujF4v1aRCH8M5p13o52w.png)

- Let’s check out some properties assigned by default to this user. Right-click on the user and select properties.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*jKo2fgui5-EJfE0Q7HseFQ.png)

- We can see a lot of tabs in this wizard. Each of the tabs can be used for a specific function by the administrator. Let’s see how we can elevate the privilege of this user to an administrator. Select Member of tab

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*DAuyd-hiHPc1ih8Yb2ngzQ.png)

- We can use this user is now part of the domain users group by default. Click on Add to add him to the **domain administrators group.**

- **Domain Users**: Domain users can log into computers, access shared folders, use printers, and do other things that the Active Directory Domain allows them to do.

- **Domain Administrators**: Domain administrators can create and manage user accounts, set security policies, install software, and perform other administrative tasks within the domain. They have the highest level of authority and responsibility to ensure the smooth functioning and security of the Active Directory domain.
- ![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*6DT7Z4t06MWNQ9blj8qu1w.png)

- From the member of tab, click on **Add > Advanced > Find Now** and scroll through the list of groups and double-click on **Domain Admin.**

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*AqxS4EvhgktTl62loUd0gg.png)

- Click on OK.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*5KhOUS0Rwj3-GnPM8yKU7g.png)

- We can see domain admin has been added as a privilege for this user. Click on Apply > OK.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*9FTYKxTTY4uF3SNXpzwOmA.png)

- As a standard practice, we sign out from the administrative account and sign in to our server with the user **Felix Mensah** since he will be in charge of IT and server management. Click on start **menu > sign out.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*wWU0exq5LK_1Oc9UIttWsw.png)
