## DYNAMIC HOST CONFIGURATION PROTOCOL (DHCP)

> - DHCP stands for Dynamic Host Configuration Protocol, which is a fancy way of saying it helps devices on a network get their own special addresses.

> - Imagine you have a big room full of computers, and each computer needs its own unique number so it can talk to the other computers. Instead of having to manually assign a number to each computer, DHCP helps automate this process.

> - Think of DHCP like a friendly helper who gives out special addresses to the computers in the room. When a new computer comes into the room and wants to join the network, it asks the DHCP for an address. The DHCP then checks its list of available addresses and gives one to the computer. This way, every computer gets its own unique number without any conflicts.

> - DHCP makes it easier to connect to a network because you don’t have to worry about picking an address yourself or making sure no one else is using the same address. It’s like having someone who takes care of all the address assignments so you can focus on using the computers and talking to your friends on the network.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*w5ax6za4gxb7AKAJnrXGkw.png)

- Click on **Manage > Add Roles and Features**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*XYPZqRYjA9a1DbHmUaxiwQ.png)

- Click Next three times to Server Roles and check the **DHCP box > Add Features**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*k-fKIt1jGCPN80co62Qvcg.png)

- Leave all as default and click on next 4 times to **confirmation > install > close**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*NwgcJJaYaoxa0TamvZrPfg.png)

- Navigate to the **notification center > complete DHCP configuration.** Leave all settings as default and click on next.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*HfAFnn1jpYWUtpgW3lkIKA.png)

## THE DHCP CONFIGURATION

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*9r-M1591e-v4jx58FACvjw.png)

- Go to **Tools > DHCP.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*mIGjYtQEo2YTZIb-W1Sb2w.png)

- From this console we see our domain name with two different types of IP addressing schemes i.e IPv4 and IPv6. For this lab we will use IPv4 as our addressing scheme.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*icld9Q8Tbxi5FkuAWiko2g.png)

- Right-click on IPv4 > New Scope

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Bcg0X19FnqW0S4m-75M9Pg.png)

- We get a welcome wizard, click Next

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Xcp76kWysIO2dz52BObtyQ.png)

- Here, provide a scope name and a description for the DHCP and click on Next.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Pm2JjzrmRqGTZ5RAZlCrsg.png)

- Set up IP Address range, here we choose the range of IP we would use in our lab and the default subnet mask. Want learn more about IP addressing, subnet mask?
![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*_x2q0-6BTWm5cAu-3Yortg.png)

- Next step is add exclusions if we desire to do so. We will specify the range of IPs we want to exclude in our DHCP server, **select add > Next**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*vK0S5YZoebtg2jmXTkqUUA.png)

- The lease duration typically specifies how long a client can use an IP address from the scope. Here, we specify in number of days, hours or minutes and click **Next.**7

![image](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*fSL2kl86ZKu5tQFHf7PExw.png)

- Finally, we choose **No**, and select **next.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*u12Y2t6pEI6InGFi2-eTig.png)

- Upon completing the scope, we notice that we have two more settings to do before all our clients can talk to our DHCP server. Click on finish.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*uwE-YE93GfIQDw_1etJAEw.png)

- Now, our DHCP scope has been configured.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*6n67Tc-AwHDxbhyL-DiSQg.png)

- When we expand on the scope, we see a list of folders and the address pool folder shows us the set of IPs we have with it’s description.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*s1u0X7Vh4Shx0ZNPBJV52A.png)

- Next, we set up Scope options which are basically additional configuration parameters that can be assigned to the clients. We will set options for DNS servers and Router (Gateway). Right-click on **Scope Options > Configure Options.**

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*yitGMFjT67Sm31VPTaASow.png)

- Check the **router box > type the IP address for your gateway > click on Add > Apply**

- We do same for DNS servers as well. Check the DNS box, enter the server name CyberRange.local > click on resolve to get the IP for the domain. Click on **Add. Apply** settings and click OK.

![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*pPrMhk6ZbeXet5qT414dKQ.png)
