# # Active Directory Corporate Simulation Using Oracle VirtualBox

![image](https://github.com/user-attachments/assets/43f1a044-c078-4dc7-8079-10a2a48ba37f)


## Introduction/Summary

In this project, I built an Active Directory home lab utilizing Oracle Virtualbox to simulate a corporate environment with 1,000 users. The environment consisted of a Windows Server 2019 VM that acted as my ‘Domain Controller’, and a windows 10 Pro VM in place to act as a ‘client’ machine. To make the environment similar to a corporate structure, a custom Powershell script was used to populate Active Directory with 1,000 users, with each user given a unique name (first name and last) as well as a default password. The windows 10 Pro VM (our ‘client’ machine) was then configured and joined to the domain.

What followed next was using Active Directory to create group policies, security groups & organization unites. In closing, Active Directory was configured to act as a centralized management system for computers, users accounts, etc. 


## Technologies and Components Used:

-	Windows Server 2019
-	Windows 10 Pro
-	Oracle VirtualBox
-	Active Directory
-	Active Directory Domain Service
-	Network Address Translation (NAT)
-	Domain Name Service (DNS)
-	Dynamic Host Configuration Protocol (DHCP)
-	File and Storage Services
-	Internet Information Services (IIS)
-	PowerShell


## VirtualBox Set-up

I used VirtualBox to create both the DC “Domain Controller” and ‘Client’ machines (client machine created after setting up the Domain Controller completely and creation of 1,000 users).

![image](https://github.com/user-attachments/assets/6ae23cb6-8d59-4157-a760-cd82b6fc9d1a)

![image](https://github.com/user-attachments/assets/709d28bd-2f8a-48c6-90b6-6af17c2dcc17)


## Windows Server 2019 and Active Directory Configuration

Two network adapters were used to separate internal and external traffic which were renamed to be easily identified with ‘_Internet_’ for external and ‘X_Internal_X’ for internal.

![image](https://github.com/user-attachments/assets/cfefd7bc-236b-4daa-8c3b-8bee3d9f7610)

![image](https://github.com/user-attachments/assets/931f08ab-0a62-4e94-a32d-3e2bd09634eb)

![image](https://github.com/user-attachments/assets/be87c4c0-55a0-4cba-b705-594bcfd3224d)

In addition, these roles and services within Active Directory and the DC were configured

![image](https://github.com/user-attachments/assets/d05b6b9b-b778-4bb0-aabb-a83bb33f7921)

A custom name list was used with 1,000 fake names saved to a text doc. 

![image](https://github.com/user-attachments/assets/56da0a14-b87d-4a8c-8418-861c5bd9aa31)

A custom Powershell script was then executed inconjunction with the above name list to populate Active Directory, with the script parsing the names list & creating users by the first letter of the first name and the last name.

![image](https://github.com/user-attachments/assets/64a38146-9b73-45b9-b854-1e832bdd9073)

![image](https://github.com/user-attachments/assets/70c3ff45-0b32-434f-86a0-d123a15ae9a8)

![image](https://github.com/user-attachments/assets/d3ffddfe-ccd1-4d1b-b32f-8234fb1e2c1e)

![image](https://github.com/user-attachments/assets/8e5d0089-8dcd-42b1-88dd-ffa572f95574)


## Joining Windows 10 Pro To The Domain Controller

As stated earlier, I used VirtualBox to also create the Windows 10 Pro environment to be a proxy for a ‘client’ computer in real-life. The network adapter was set to “internal network” to ensure traffic flowed only through the DC. To verify connection, I pinged the previously created DC, “mydomain.com” and got a positive read-back.

After this machine was joined with the DC, I then tried accessing it using credentials from 10 users that I previously generated, logging into the Windows 10 VM. Again, to act as if I was a client/user who just got access to the work network and logging in to my first day at work. Each one was able to login with success.

![image](https://github.com/user-attachments/assets/95d8713f-af6b-4cd0-a2f9-0787c1b03b80)

![image](https://github.com/user-attachments/assets/97f9f990-0600-4694-a0c6-84c90faef14f)

![image](https://github.com/user-attachments/assets/73ae4f33-021d-4a2a-8197-2d108140b202)

## Conclusion

In conclusion, this project allowed me to gain valuable knowledge in setting up proper configuration of Active Directory as well as getting more practical hands-on experience with using scripts and VirtualBox. Playing around with Active Directory I was able to learn more about the tool, more of its ins and outs on a technical level and giving me more of a wider knowledge base of it in a more real world corporate environment.






