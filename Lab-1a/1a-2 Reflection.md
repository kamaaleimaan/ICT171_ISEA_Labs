# 1a-2 Ubuntu Desktop and Command Line Familiarisation 
(Do note that some of the Lab deliverables in this 1a-2 are in 1b-1 as they are requesting the same thing)

So this lab wanted me to get more familiar with Ubuntu and the various way to do things like creating files either through the file manager or through the terminal. Along with getting familiar with privileges, testing the network.

I started off with launching FireFox which came pre-installed with my Ubuntu package, I just went to youtube to show that I am also connected to the internet. I also had to show that Libre Office was working, however for some reason I had to download the Libre office suite on the Ubuntu Software Centre, which will be shown in these set of images as well. Along with that I had to show that I could navigate through the file directory, which was simple enough as it was just about the same as it is in Windows.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ea197da33d0e62ef5fcc77a3e234b146309c081e/Lab-1a/1a-2.01%20Firefox_Working.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ea197da33d0e62ef5fcc77a3e234b146309c081e/Lab-1a/1a-2.02%20LibreOffice_Working.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ea197da33d0e62ef5fcc77a3e234b146309c081e/Lab-1a/1a-2.03%20Navigating_Directories.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ea197da33d0e62ef5fcc77a3e234b146309c081e/Lab-1a/1a-2.04%20Installing_Software.png)

Next up was getting familiar with file creation and editing with the terminal instead of the regular way of going into the file manager and right-clicking to make a new folder or file. I didn't know you could do these things in the terminal, so that's cool.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ea197da33d0e62ef5fcc77a3e234b146309c081e/Lab-1a/1a-2.05%20File_Creation.png)

I had a bit of problems understanding some of the commands, and thankfully the lecturer was kind enough to link us to a website with [Top 60 Linux commands](https://www.hostinger.com/tutorials/linux-commands) along with examples of each. I then proceeded to continue on with the File Operations part of the Lab, along with the System Information Commands, User Privilege and Network Test. I did not run into much issues with these, as these are pretty straightforward. The only problem I can foresee is probably needing to know these commands by hard for future use.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ea197da33d0e62ef5fcc77a3e234b146309c081e/Lab-1a/1a-2.06%20File_Operations.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/fa802392e8c61a920700f9e9d7c789c1b10b89ef/Lab-1a/1a-2.07%20System_Info_Commands.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/fa802392e8c61a920700f9e9d7c789c1b10b89ef/Lab-1a/1a-2.08%20User_Privilege.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/fa802392e8c61a920700f9e9d7c789c1b10b89ef/Lab-1a/1a-2.09%20Network_Test.png)

After which comes the another part of the Lab, which was to get or install various software through different methods like SaaS, Binary download and the Ubuntu Software Centre and through the terminal command line. I managed to stuff all these in one image, so it may look a little cluttered, but to the left is the SaaS method, the top right hand side is the Binary Download of a .deb file and the bottom right is the installation of VLC Media Player through the Ubuntu Software Centre. I found it cool that you could intall stuff through the terminal, broadens my knowledge on how capable the terminal really is.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/fa802392e8c61a920700f9e9d7c789c1b10b89ef/Lab-1a/1a-2.10%20Software_Installation.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/fa802392e8c61a920700f9e9d7c789c1b10b89ef/Lab-1a/1a-2.11%20Command-Line_Install.png)

The last part of the lab is source code compilation, I had a bit of an issue with this at first as since I am new to coding as a whole I did not know how to code in C, but through a bit of searching and basic resources, I managed to code out a simple hello world and compile it into an executable and run it as shown in the image below.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/fa802392e8c61a920700f9e9d7c789c1b10b89ef/Lab-1a/1a-2.12%20Source_Code_Compilation.png)

Since I am only starting out, nano to me is the best file editor for remote access as it is simple and understandable to use. It helps me out by displaying the keyboard shortcuts at the bottom of the screen, making it easy for beginners like myself to edit the configuration files over a remote connection. I did a bit of searching and found out through [rackspace](https://docs.rackspace.com/docs/command-line-text-editors-in-linux) that there are other file editors like Vim and Emacs that offer many advanced features, however they have a steeper learning curve and are generally better suited to more experienced Linux users.

The different installation methods would have their own pros and cons, this can also be seen from a User Perspective, SaaS requires no installation, is always up to date and is accessible from anywhere with Internet compared to the others where you would need some form of installation, updates require you to reinstall and you would need to find your way to install the item. However, SaaS would give you less control over the software and data and would require the Internet as you would always need to be connected through SaaS compared to the other installation methods. 
Binaries on the other hand are quick and easy to install, however the software might come from different sources as the installation depends on, for example, which website you go to to access and install the item as compared to repository install through Ubuntu Software Center and terminal where those methods are the central source of installation.
Repository Install via Ubuntu Software Centre is also easy to install and update, and is generally more secure as the items are maintainted by the distrubutor, however it might take some time for the distributor to update to the newest version as compared to Binaries as you are downloading it straight from the source and not through the distributor.
Command Line Install is another way to install items, however it might be limited in what it can install, and it would require some more knowledge as compared to the previous methods.

From a developer perspective, SaaS requires server maintenance and uptime as it has to always be on to act as a service to users, it needs security as multiple users are going to be using the software on the servers as compared to using it locally through the other methods. SaaS however makes it easy to deploy updates to users making sure everyone is on the same version.
Binaries can also be seen as a way to easily distribute the compiled software as the developers themselves are the source, however developers must take into account different users using different OS's or architectures, along with each individual maintenance.
Repository Installation via Ubuntu Software Centre is also easy to deploy as you are just handing it over to the distributor and having them handle dependencies, however packaging these items for the distributors and keeping them updated requires a little more effort as compared to the other methods.
Command Line Installation from a developer perspective may have users run into compilation problems, and developers would need to give them these instructions as to how to handle it.

It helped me broaden my understanding of Linux, for example in Windows compressed files would normally be .zip files, whereas I learned through these Labs that different OS's and architectures would use different names, so the next time I come across these foreign files I would have more confidence in determining what they do and what they belong to and how to handle these files or what to do with them. It also helped me in understanding the different ways to download various software, this would be helpful if I would want to download a piece of software, I would know the multiple ways I can get it if one of the ways are not available.
