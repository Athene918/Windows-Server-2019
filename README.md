# Projet Windows Server

## Active Directory

### Getting Started with Active Directory

- Click on the Start Menu: Access the Start menu from your taskbar.
- Launch the Server Manager: From the Start menu, open the Server Manager.
- Navigate to Local Server: In the Server Manager dashboard, select "Local Server".

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*pBQ4LX30_v6Q4-5ansGsXQ.png)

- On this page, we will make two configuration settings to our server before we install the active directory domain service.

### 1. 1st Configuration

- Go to command prompt, enter ipconfig to view the IP configuration of your system and make a note of that

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*3lcQrNy5InB-bZ5EwyXdIg.png)

# Configuring a Static IP Address for Your Windows Server

To ensure your server can be reliably and consistently located by other devices on the network, we need to set up a static IP address. Follow these steps to configure it:

## Steps to Set Up a Static IP Address

1. **Open the Control Panel**:
   - Click on the Start menu and type `Control Panel`.
   - Open the Control Panel from the search results.

2. **Access Network and Sharing Center**:
   - In the Control Panel, click on `Network and Sharing Center`.
   - Alternatively, you can right-click the network icon in the system tray and select `Open Network and Sharing Center`.

3. **Change Adapter Settings**:
   - In the Network and Sharing Center, click on `Change adapter settings` on the left-hand side.

4. **Select Your Network Adapter**:
   - Identify the network adapter that is connected to your network. It will usually be named `Ethernet` or similar.
   - Right-click on the network adapter and select `Properties`.

5. **Configure IP Settings**:
   - In the Properties window, scroll down and select `Internet Protocol Version 4 (TCP/IPv4)`.
   - Click on the `Properties` button.

6. **Set a Static IP Address**:
   - In the Internet Protocol Version 4 (TCP/IPv4) Properties window, select `Use the following IP address`.
   - Enter the following details:
     - **IP Address**: Choose an IP address that is within your network's range and not already in use (e.g., `192.168.1.10`).
     - **Subnet Mask**: Typically, this will be `255.255.255.0`.
     - **Default Gateway**: Enter the IP address of your router (e.g., `192.168.1.1`).
   - Enter the following details for the DNS servers:
     - **Preferred DNS Server**: You can use your router's IP address (e.g., `192.168.1.1`) or a public DNS server like Google’s (`8.8.8.8`).
     - **Alternate DNS Server**: Optionally, you can add a secondary DNS server like Google's (`8.8.4.4`).

7. **Save the Configuration**:
   - Click `OK` to close the Internet Protocol Version 4 (TCP/IPv4) Properties window.
   - Click `Close` to close the Ethernet Properties window.

8. **Verify the Static IP Configuration**:
   - Open a Command Prompt by typing `cmd` in the Start menu and selecting the Command Prompt application.
   - Type `ipconfig` and press Enter.
   - Verify that the IP address you assigned is listed under your network adapter.

9. **Restart the Server**:
   - For changes to take full effect, it’s a good idea to restart your server.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*oK8y5M3t0TguFgso5gYT2g.png)

### 2. 2nd Configuration:

- At this stage, we need to change our default computer name to a more standard naming within our environment. Using a standard naming convention for devices in a network will provide us with several benefits 
   including; consistency, organization and documentation, ease of communication, scalability and security and access control. It also enhances communication, simplifies administration, and supports effective 
   network documentation and troubleshooting. 

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*7qmqn9x9_jtuNBrFTNNCsg.png)

- Still on our local server properties, click on the default computer name tio view the system properties wizard. Click on change, and change the default name to your favorite name. In this lab we will use CyberRange-DC01. Click on ok and you will be prompted to restart the server.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*1PLIf6ZysL9Ur9ZA3QHzmQ.png)

- After restarting the server, log in with your password and navigate to Server Manager > Local Server and we should see all our configurations take effect. Great job.

## WHAT IS WINDOWS ACTIVE DIRECTORY

- Active Directory is a digital phonebook for a company that tracks users, their login credentials, computers, groups, and network resources like shared folders and printers. It enables user authentication, access 
  control, and resource management, simplifying network administration by allowing administrators to manage users and assign permissions efficiently.

## A Step-by-step guide to install and configure Active Directory Domain Services In Windows Server

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*J_a3filIlF1HdJktmUzFvA.png)

- At the top right corner, click on manage > add roles and features. Leave everything as default and click on Next >Next>Next>server selection.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*qe4f04qez_DTLG1dB4Af9w.png)

- On the server roles, check the Active Directory Domain Service box and click on add features to add all the related roles and features for our AD DS. Click on next > next > next.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*WVanbbjYWIjl9Qd5o-3IMg.png)

- Here, we confirm that all features needed were selected. Click on install to now install the AD DS role in our server

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*uXcZvHpbBP40FreLfeDu-A.png)

- Once installation is done, we get a notification to promote this server to a domain controller. Select close and navigate to the notification center.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*RfG_759iQvBTK_060vxQDQ.png)

- At the notification center, select promote this server to a **domain controller.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Ys-AjqW13lY4S3kdf19rGw.png)

> - **What is a Forest:**
A forest is a collection of one or more domains that share a common schema, configuration, and global catalog. It represents the highest level of organization in the Active Directory structure. The forest establishes a trust relationship between domains, allowing users from one domain to access resources in another domain within the same forest. A forest is defined by a unique forest name and typically represents an entire organization or a distinct network environment.

- At the deployment configuration, select add a new forest and choose your preferred root domain name for this domain controller. Here we go with CYBER-RANGE.Local and click on next

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*oQA0gTTC5XIZSLL8Ln1Y-g.png)

- Leave all settings as default and choose a DSRM password for your domain controller and click on next. Select next five times to the prerequisite checks options.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*t6nvfJLuuBmtNuzevLDsRQ.png)

- This options verifies if all checks were passed successfully. Click on install to now promote the server to a domain controller. If your checks were not passed successfully I recommend you read through the error to find clues to fix the issues.

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*5TBNRB7Spp9oOlnwOEX-gA.png)

- After successful installation of the AD DS, the server will be signed out and initiate a restart to effect the configurations done.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*4jlbu10EyGWQexdwEYlrvw.png)

- Now, we see that we have a domain name with administrator logon screen. Enter the password to login to your domain controller.

![imagge](https://miro.medium.com/v2/resize:fit:720/format:webp/1*cFjR5APy-164lEOGCTIPgQ.png)

- Launch the server manager from the start menu and we could see that we have successfully installed and promoted this server to a domain controller which is up and running.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*BW1apAdihz1xI3mh18blVQ.png)

- On the local server menu we see that all configurations have been effected. Congratulations on your successful installation and promotion of the server to a domain controller.

