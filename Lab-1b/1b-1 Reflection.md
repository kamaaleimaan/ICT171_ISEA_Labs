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


Afterwards I outputed lsusb as a file and viewed the size and what the contents of it was.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/61dcc360e7bd08056c342d1b82d8affd01efb119/Lab-1b/1b-1.16%20Output_Redirection.png)


The Extension 1 challenge just had me going into my cloned virtual machine and creating a file. Afterwards Extension 2 had me run gedit over SSH to my cloned virtual machine, a lot of warnings popped up and it did not work, upon further searching, users on the [Raspberry Pi forums](https://forums.raspberrypi.com/viewtopic.php?t=242077&__cf_chl_f_tk=p_j7p4QSy9D6WTGfTqWKGveVElNvsdzXXcQlX7KrfWk-1783343030-1.0.1.1-eze2ru4OgOLqzqVAR6.pZr1zyMknJR20q7XSmC7rHww) explained that gedit is a GUI application, its needs a graphical interface, which is not usually possible as terminal does not support these graphical interfaces that it requires to run gedit.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/61dcc360e7bd08056c342d1b82d8affd01efb119/Lab-1b/1b-1.17%20Extension1_Extension2.png)


Extension Challenge 4 had me downloading books from the Gutenberg website and sending it over to my cloned virtual machine using scp and SSH. I still had a bit of issues on how scp works, but after realising that scp only sends files from the machine it is running from to other devices, it became clearer to me. The first image shows me compressing the books using tar and bunzip2. The second image shows me sending it over using SCP and SSH to verify that it has been installed.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/61dcc360e7bd08056c342d1b82d8affd01efb119/Lab-1b/1b-1.18%20Extension4_Compression.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/61dcc360e7bd08056c342d1b82d8affd01efb119/Lab-1b/1b-1.19%20Extension4_SCP.png)


The final part of the lab had me double checking IP addresses and using ping. I used SSH to ping the other virutal machines for both virtual machines.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/61dcc360e7bd08056c342d1b82d8affd01efb119/Lab-1b/1b-1.20%20VM_Network1.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/61dcc360e7bd08056c342d1b82d8affd01efb119/Lab-1b/1b-1.21%20VM_Network2.png)


From this lab I learnt that firewalls are used to control what network services is accessible by enabling or disabling traffic on specific ports, like how I enabled port 80 on my firewall and used an Nmap scan from my other virtual machine, it allowed traffic for that port. When the firewall rule was removed or the port was blocked, the service was no longer accessible. This shows that firewalls helps to protect systems by preventing unauthorised access while being flexible enough to allow legitimate services to be available when required.

Before actually using SSH I only ever learnt SSH as an application layer protocol in my Network Communications bridging module. Using SSH in real-time has made me realise how much more versatile the terminal is, where an actual display sometimes isn't needed to be able to set up a server. I could set up an Apache2 web server and edit it on my cloned virtual machine without ever needing to have access to my cloned virtual machine, provided I just have it turned on.

File compression is used in server environments because it is able to reduce file sizes and directories so that it is easier and faster to store and transfer these compressed files. It is also easy for servers to make backups without hogging up disk space. Through my use of tar and bunzip2 to compress files, it also showed me that it is easier to transfer files over the network easily when I did Extension Challenge 4 and used scp. This experience can be mirrored to server contexts where large amounts of data are always being transferred, improving efficiency and reducing bandwidth as files transferred are smaller (compressed) as compared to their original size.

- How does user privilege management help secure systems?

