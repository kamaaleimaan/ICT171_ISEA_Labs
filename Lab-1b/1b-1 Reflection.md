# 1b-1 Linux Services, SSH, Firewalls & Compression 

For this lab I went further into more linux services, along with using SSH and cloning my virutal machine to create my own virtual partner as requested by the lab. At first I thought it would be tedious, but thankfully VMWare was quite simple to deal with two Virtual Machines at the same time. To start off the solo portion, I installed apache onto my virtual machine and used the loopback IP (127.0.0.1) to make sure that it has installed properly.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.01%20Apache_Installed.png)

After which I had to edit the index.html that was found in the /var/www/html/ folder to customise my own web page. Since I am new to all these languages, I decided to just go simple and have some text on my web page.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.02%20Modified_Index_Page.png)

This was the point when the Lab required there to be a partner. VMWare has this neat feature that clones virtual machines, so I went ahead and cloned my virtual machine to make a new apache server to show that everything was working. In the image, I have a terminal with ip a showing that the IP addresses are different and I did install apache on 192.168.253.129.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.03%20IP_Address_Identified_Shared_Nmap.png)

After which I had to do an Nmap scan on my cloned virtual machine before and after apache is installed, from what I see it shows that after apache was removed, the TCP port for it was closed.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.04%20Nmap_Port_Scan.png)

I had to note some firewall changes afterwards using UFW commands, after I enabled the firewall there was a list of rules that was stated as compared to if I leave it inactive, and I can make rules as to which port can be accessed, as the Lab instructed me to open up Port 80. I did this on my original virtual machine and checked it using Nmap with my cloned virtual machine as seen in the images below.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.05%20Firewall_Changes.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.06%20Partner_Perspective_Firewall.png)

After which I had to do remote access using SSH using both my virtual machines. I firstly ran into an issue where I could not connect to the other virutal machine, but I realised that my firewall was still turned on, after disabling it SSH worked fine.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.07%20SSH_Success.png)

AAA Extension Challenge 3

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.08%20SCP_File_Transfer.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.09%20SCP_Folder_Transfer.png)

- What’s the role of a firewall in managing services? 

- How did SSH access deepen your understanding of Linux as a server? 

- Why is file compression important in server contexts? 

- How does user privilege management help secure systems? 
