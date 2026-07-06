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


I was then introduced to the scp command. The command was confusing at first, I was not sure if the command is used to get files from another device or the other way around. After some testing however, I learned that the scp command transfers files from whichever device it is used from to another device. I have also attempted Extension Challenge 3 by transferring a folder from my cloned virtual machine to my original virtual machine through the use of the -recursive addition.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.08%20SCP_File_Transfer.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/5697092c072c4bb4fa2bc2fcc97136963571301e/Lab-1b/1b-1.09%20SCP_Folder_Transfer.png)


We will get more into the Extension challenges towards the end of this reflection, now the Lab required me to edit the host file to associate Google's IP 8.8.8.8 to GoogleEpicDNS. I didn't have much issues here, I just realised that this was made to make associating IP addresses easier and mroe readable for humans. After which I showed that I can successfully ping the new readable name using Bash in the images below.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4be46657d8b187ffa50ffb508984fec090cfe44c/Lab-1b/1b-1.10%20Host_File_Edit.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4be46657d8b187ffa50ffb508984fec090cfe44c/Lab-1b/1b-1.11%20Host_File_Edit2.png)


DNS lookup is another useful command that I learned through this lab, being able to know who owns what and more information on a web address would be useful information in contacting them. 

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4be46657d8b187ffa50ffb508984fec090cfe44c/Lab-1b/1b-1.12DNS_Lookup.png)


I learned a little bit of public and private IP addressing through another bridging module, and a public IP address is just basically what the IP all my local device would use to travel through the internet, whereas my private IP is what identifies me within the local network, which is why when I look up my IP in the website vs me using ip a, it shows a different result.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4be46657d8b187ffa50ffb508984fec090cfe44c/Lab-1b/1b-1.13%20Private_Public_IP.png)


Using tar and Bunzip2 was another eye opening experience for me, like I said I still sort of see the Linux items in a Windows way, so needing to know the different terminologies helps me differentiate these operating systems. It was also interesting to learn that you could do all these in a terminal.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4be46657d8b187ffa50ffb508984fec090cfe44c/Lab-1b/1b-1.14%20Compression_Decompression.png)


Being able to look up my hardware in terminal was something I expected, the image below shows me running the command in terminal and placing it side by side with my settings to show that both of them match up.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4be46657d8b187ffa50ffb508984fec090cfe44c/Lab-1b/1b-1.15%20Hardware_Info.png)



- What’s the role of a firewall in managing services? 

- How did SSH access deepen your understanding of Linux as a server? 

- Why is file compression important in server contexts? 

- How does user privilege management help secure systems? 
