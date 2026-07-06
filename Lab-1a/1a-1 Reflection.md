# Lab 1a-1 Virtualisation & Linux Setup 
In this lab I got my hands dirty with installing a virtual machine and configuring it for my future classes or just my future in general. Personally I have tried to install virtual machines in the past so that I could download games on like itch.io without getting a nasty virus on my main pc, but I figured out the hard way that it was very tedious and hard lol. The last time I tried it I used virtualbox, and it was tough, hard, confusing. Back when I tried it was a lot harder to find solutions to some problems I was facing, hence why I dropped the whole idea of going further into virtual machines. This time however, it was a lot smoother and since there is a support structure with my classes and my lecturer, I am more confident in doing this.

## Installing, Configuring, and First Impressions with VMWare

The first challenge that I faced was which desktop hypervisor to use. The lecturer and the student resources has outlined many ways to do so such as VirtualBox, VMWare or Windows Subsystem for Linux (WSL). I ended up choosing VMWare partially due to lecturer's reccomendation but I also have searched up online which desktop hypervisor regular people use, users on [reddit](https://www.reddit.com/r/virtualbox/comments/k8s3d8/virtualbox_or_vmware_player/) are in agreement that VirtualBox is just generally harder to use at the time of me writing this. Along with my previous bad impressions of Virtualbox, I ended up choosing VMWare, you know I thought I had to pay for it, but after a few minutes of digging I managed to get the Workstation Pro for free, so thats cool.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/d1dc8da62f94c36347d1582a5f69a26b763cf22e/Lab-1a/1a-1.1%20VMWare_Installed.png)

After that I had to get the Ubuntu ISO from the official website, thanfully all the links were provided so I didn't need to worry about pressing some jank link and getting some gnarly virus. I had to wait for quite some time and was a little worried I couldn't download it in time to share it with the lecturer.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/d1dc8da62f94c36347d1582a5f69a26b763cf22e/Lab-1a/1a-1.2%20ISO_Downloaded.png)

During the initial Virtual Machine (VM) setup in VMWare, I just went with whatever VMWare reccomendded, but I did change the VM size to 25 GB, I had a bit of worries that it might be too small but ultimately told myself if I need more disk space then I can add more in the future. After that I had to do more waiting for Ubuntu to do its inital setup items and after that I finally got my Virtual Machine with a lot less hassle than I did when I previously used VirtualBox.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/d1dc8da62f94c36347d1582a5f69a26b763cf22e/Lab-1a/1a-1.3%20Ubuntu_Installed.png)

I had to take some more screenshots of my network configuration and the terminal window as part of my labs, so the images below reflect those. I had not much problems doing them, VMWare is quite straightforward as to what and where certain things are, and to get Bash I could just type in terminal like I do in Windows.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/d1dc8da62f94c36347d1582a5f69a26b763cf22e/Lab-1a/1a-1.4%20Network_Configuration.png)

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/d1dc8da62f94c36347d1582a5f69a26b763cf22e/Lab-1a/1a-1.5%20Terminal_Window.png)

Like I said before, a few years ago I had limited experience with VirtualBox, got frustrated and ran into tons of problems, and dropped trying to make a VM. However this time, I learned that these virtualisation tools are used more for just virus testing, they can also be used for a lot more testing by creating a seperate OS environment without the need of another computer or device. In the earlier link to the reddit forum page, they mentioned that VMware is known for its stability and overall less hassle. Other tools, such as VirtualBox, are a lot more rougher, while I heard from my lecturer that Hyper-V is just bad in general. I learend that while they all provide the same core function of running virtual machines, they differ in their performance, features along with ease of use.

However, I still don't feel confident using Ubuntu after completing this lab, sure I can access Ubuntu, but this is still my first time ever trying to get past the surface of a completely foreign Operating System to me. I can do the basic things like install Chrome or Steam, something that would seem similar to how it is in Windows, but my mindset would still be in the Windows mindset, not the Ubuntu mindset, if you get what I mean.

Virtualised Linux environments are able to help out with Development and Testing, as getting another device might be very costly and a big hassle to setup, having something like VMWare to spin up exact replicas of production environments in seconds would help developers test software across various Linux distributions without needing the before mentioned extra hardware.

I might want to try installing another OS like windows or maybe another version of linux if i were to set up another VM. This is to expand my horizons to explore and get my hands deeper into the different types of OS that are available, what they are good and what they aren't good at. Which one would be the best for a specific server that I would want to run.




