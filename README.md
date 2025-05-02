# Active-Directory-Setup
This project documents the steps I took to set up an Active Directory environment, which included promoting a Windows Server to Domain Controller, adding workstations to the domain, and then creating Organizational Units & adding new users

&nbsp;

# 1\. Upgrading Server to Domain Controller

On the Windows Server go to Server Manager > "Manage" > "Add Roles and Features"

![image](https://github.com/user-attachments/assets/e515379a-7a92-45c1-a3fc-2a8e1e03e15a)

Make sure "Role-based or feature-based installation" is selected

![image](https://github.com/user-attachments/assets/89b60c12-8492-40c9-9086-8a7b836cfc3b)

Leave everything on "Server Selection" as default

![image](https://github.com/user-attachments/assets/a44db44f-2db8-4bd9-a2d4-3ad5676ac353)

Select "Active Directory Domain Services". Add more server roles if needed.

![image](https://github.com/user-attachments/assets/98869505-acc0-4aa3-b413-608a8e3f216d)

Select “Next” until you get to the Confirmation tab. Then select "Install"

&nbsp;

You should get the following message:

![image](https://github.com/user-attachments/assets/040061cd-eb72-48b2-88b2-4be55cffa038)

&nbsp;

On the Server Manager, go the to flag icon with the yellow icon, and "promote this server to a DC":

![image](https://github.com/user-attachments/assets/7e0c953e-8dff-4e0a-9bb2-72c1a4a0f348)

&nbsp;

Choose "Add a new forest" and choose a root domain name in order to create a brand new domain:

![image](https://github.com/user-attachments/assets/d17e7855-758a-4dee-b39e-dc441bcd82a8)

&nbsp;

You may leave everything as default and put in a password:

![image](https://github.com/user-attachments/assets/2bc25997-a35d-43e1-bfb2-eae8a5fa823c)

&nbsp;

Keep hitting next...

&nbsp;

Keep clicking next, then wait for verification, once verified, click "Install":

![image](https://github.com/user-attachments/assets/f7c3b304-6eea-49b9-81c2-bafb0297f565)

&nbsp;

The server will restart.

&nbsp;

When you login you should see the Name\\Administrator

![image](https://github.com/user-attachments/assets/20f3c6e8-949e-4bf9-b469-d0c9b5fd04c4)

## Creating  Users and Organizational Units

&nbsp;

Server Manager > Tools > Active Directory Users and Computers

&nbsp;

![image](https://github.com/user-attachments/assets/c3298552-5b4a-451c-be07-fbfe73849499)

This is where objects such as users, computers, and groups can be created.

&nbsp;

![image](https://github.com/user-attachments/assets/e6678643-fb80-4907-9f49-b7c586832edc)

&nbsp;

I named this one "IT", and now there is a new OU

![image](https://github.com/user-attachments/assets/60b07ae8-3e06-41d2-bfd5-ba7e1b495f3a)

&nbsp;

Now within this organizational unit, we can create a new user. They will be apart of the IT department.

![image](https://github.com/user-attachments/assets/706ffd11-7c80-4a9c-844a-d6ba4dd69e4d)

![image](https://github.com/user-attachments/assets/a2cae1c6-56ad-4710-a5d8-a4498130e494)

![image](https://github.com/user-attachments/assets/5e112ed2-eaf9-4454-ab0e-0857e6cbe14b)

&nbsp;

&nbsp;

Now we have a user in the It department. We can create or copy more and also do the same for other Departments/Organizational Units

![image](https://github.com/user-attachments/assets/745bb514-b59d-4aa7-8113-c8c500a39422)

&nbsp;

&nbsp;

&nbsp;


# Adding workstations 
Go to My PC > Properties > Advanced System Settings

Choose "Computer name" > "Change"

&nbsp;

Choose "domain" then enter the name of domain:

![image](https://github.com/user-attachments/assets/eb5ece5b-0bbf-405c-b6d2-e41c83ae2d36)

&nbsp;

If you get this message that means the machine does not know how to resolve \*.local:

![image](https://github.com/user-attachments/assets/fd9c4ad4-4ed2-45d6-9501-a48a86daa776)

&nbsp;

On the change adapter options for IPv4, you must change the DNS server to whatever the IP of the domain controller is.

![image](https://github.com/user-attachments/assets/e528749d-aa7f-4fe9-b27c-76efe696f2ad)

Making sure the configurations were set properly with "ipconfig":

![image](https://github.com/user-attachments/assets/5cbbf18e-4161-47d0-9997-e7edc9c5b1ed)

Now try to add the workstation to the domain.

&nbsp;

You can use the credentials of the ADMINISTRATOR account of the server, as that account will have the proper permissions.

![image](https://github.com/user-attachments/assets/d0d77693-df76-44be-a694-e9d244ebe5b0)

![image](https://github.com/user-attachments/assets/a8a60d6e-147c-4cd8-a232-0a5a84bbade7)
