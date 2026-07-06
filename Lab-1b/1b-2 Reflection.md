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
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/e0cc3dcb501026849d6043313bd4cf8378fc2bd3/Lab-1b/1b-2.09%20Mallory_Perms.png)


Finally, I had to remove the file using rm and the recursive flag to remove everything, I did this and afterwards went into alice using su and checked that it was not there at all.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/e0cc3dcb501026849d6043313bd4cf8378fc2bd3/Lab-1b/1b-2.10%20Folder_Cleanup.png)


Through this lab, I learned that linux permissions are much simpler and easier to manage as they are based on the three permission types I listed just now (read, write, execute). These permissions are then assigned to three groups of people: the file owner, the group, and everyone else. In the lab, I used the chmod, chown, and chgrp commands to change who could access the shared directory and its files. For example, Alice had full access, Bob had read and execute permissions, and Mallory had no access until she was added to the sudo group. For Windows ACL, I found out through [ask ubuntu](https://askubuntu.com/questions/1226759/is-the-windows-permission-system-different-from-that-of-linux) that Windows ACLs are more detailed, leading to more flexibility and control. Instead of linux's rwx, Windows ACL has more specific rights like Full control, Modify, Read, Read and execute, Write and Special permissions. Overall, Linux permissions are easier to manage, while Windows ACLs provides finer-grained control over the files and folder access.

As explained earlier, the different placements of the numbers mean different things, chmod 770 would allow the owner of the file to read, write and execute the file, the owning group would be able to also read, write and execute, and everyone else outside of it would NOT be able to read, write or execute. On the other hand, chmod 750 allows the owner of the file to read, write and execute the file, the real change is in the owning group, now it would only be able to read and execute, and everyone else outside of it would NOT be able to read, write or execute.

Adding users to the sudo group would give them administrator privileges. As shown in the screenshot earlier, mallory now is able to run all commands as she is in the sudo group. This means she is able to edit directories outside of her own profile. While this is useful for system administration, it would also add more security risks as these privileges can accidentally or maliciously damage the system as mallory can now do almost anything. This is why sudo access should only be given to trusted users who require it and are trusted to not damage the system.

Being able to verify with su and whoami is important as it helps to confirm that the commands that are being executed are being done so by the intended user. During the lab, I used su to switch between alice, bob and mallory while whoami would verify the current user that i was logged into before testing out the file permissions. This would ensure that the results that came out of it accurately reflected each of the user's permissions rather than the other users or the administrator. Without being able to verify the current users, permission tests would produce incorrect results.
