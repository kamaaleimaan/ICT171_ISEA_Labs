# 1b-2 Linux File Permissions and Group Access Control

This lab had me create new users on my linux system and to do user group management along with assigning file permissions. In the below images, I added alice, bob and mallory to my virtual machine and assigned only alice and bob to a shared group.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.01%20User_Created.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.02%20Sharedgroup.png)


Next, I made a directory using mkdir, and changed who owned it using change owner (chown) to alice, change group (chgrp) to the sharedgroup. I also learned a shortcut to add multiple files using {1..10} instead of manually adding them one by one.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.03%20Shared_Directory.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.04%20Files_Created.png)


I then used change permissions (chmod) to change who could access these files. I learned that the numbers that are after chmod uses binary numbers 111 to read, write and execute. The addition of these binary numbers correleate to what permissions you would want a specific user to have. For example in chmod 750, the first number 7 allows the owner to read, write and execute, the number 5 allows the group (in this case the shared group) to read and execute, and the final number 0 allows others (outside the group) to not be able to read, write or execute.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.05%20Permissions_Assigned.png)


The image below verifies which users have what permissions. Alice is able to view the file using cat, bob not being able to use echo to edit the file, and mallory outright having no access to it at all.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.06%20Access_Verification.png)


After that I learned about the -recursive flag to edit the permissions of all the files in the /home/shared folder, using chmod, chgrp and chown along with the flag to change permissions to all the items inside.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.07%20Change_Commands.png)


The lab outlined how to add mallory as part of the sudo group by using usermod -aG sudo to add mallory to the sudo group. The following image shows that mallory is allowed to run all commands.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2dab9bacc54bfa2a556a7ed1b11761aa9d54c3ba/Lab-1b/1b-2.08%20Mallory_Sudoers.png)
![Image]


w


- How do Linux permissions differ from Windows ACL? 

- What’s the effect of chmod 770 vs 750? 

- What is the risk of adding users to the sudo group? 

- Why is it important to verify with `su` and `whoami`? 

 
