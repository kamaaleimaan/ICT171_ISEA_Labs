# 2b-1 Cloud Web Server Deployment with Amazon EC2 

In this lab, I used Amazon EC2 through the free tier to be able to make a web server on a cloud server. I chose Amazon EC2 as it was recommended by the lecturer, and that it clearly outlined that even though I put my payment information in they would not accidentally charge me if I were to go over the limit. Setting it up was not that bad, I just had to make the .pem key to be able to SSH into the web server. The second image below shows my network settings, ensuring that SSH and HTTP ports were open so that I could SSH into my cloud server and open up an apache web server.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.01%20EC2_Running.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.02%20AWS_Network.png)


I decided to SSH through my host OS, which if I were to do it over again I would rather do it within my virtual machine on my laptop. The process was straightforward enough, I just had to ensure that my .pem key was in the correct path to my key by adding on -i "C:\Users\(myusername)\Documents\keys\my-key.pem", after which I have successfully SSH'ed into my cloud server.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.03%20SSH_Successful.png)


Installing Apache2 was standard, as I have shown in the previous lab screenshots and reflections, and the editing was about the same. I wanted to do it through my host OS since I wanted to see the difference between bash and powershell, but they ended up being more or less similar, so I did not have much problems.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.04%20AWS_Apache.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.05%20Index_Edited.png)


However, this was my first time using wget to get a file from a website. I had a bit of issue locating where the file was at first but after a bit of digging I finally found the file location and added it on to wget to get the file.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.06%20Download_wget.png)


Then I used the copy (cp) command to copy the pdf file into /var/www/html so I could access the pdf through my web server, which I successfully did as shown in the screenshot below. Along with making the pdf accessible through a link by editing the index.html file, I was able to make a simple click here hyperlink which led to the pdf file.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.07%20PDF_via_Browser.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/3331174cb286b8bb13ce14a86845d0b800651a83/Lab-2b/2b-1.08%20Link_Inserted.png)


Once I have completed the lab, I then closed the instance to make sure I wasn't leaking out any credits.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ebb5c2c1bdf45fc87dc2be88702358c34d2a6aac/Lab-2b/2b-1.09%20Closing_Instance.png)


Going over to the budget and monitoring and the credits tab, I see that through all the commands I have ran, it only costed me 0.04 cents.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ebb5c2c1bdf45fc87dc2be88702358c34d2a6aac/Lab-2b/2b-1.10%20Budget_Monitoring.png)


Cloud servers provide no server management from the developer side, developers could focus solely on writing code without managing server infrastructure. Serverless platforms automatically scale resources to handle incoming requests, meaning to say that you would not need to prepare beforehand for large amounts of traffic coming into your server, for example a christmas sale, as cloud providers would automatically do it for you. It also saves space as during non-peak periods there would not be useless space laying around. Cloud servers also offer their services on a pay-per-use metric, where you would be charged based on actual usage of resources, as compared to paying for idle server capacity, as explained earlier. Cloud servers also offer rapid development and deployment of applications, reducing time-to-market, it also helps that cloud servers would not be affected if say for example a power outage were to happen on premise.

During my lab, I had to store a pdf file that needed to be accessible into the /var/www/html folder, showing how apache serves files, by storing them into their own folders and retrieving them when asked for it by users. I verified this by replacing the default index.html with my own webpage, copying the PDF file into /var/www/html, and creating a link to the pdf file, successfully opening both the webpage and the PDF in a seperate web browser.

Through this lab, the apache web server's /var/www/html is owned by the root user, as a normal user would not have the permissions to this directory, I had to use the sudo cp command to copy the pdf that I downloaded and place it into the web root. After the file was copied into the folder with correct ownership and permissions, Apache is able to serve the pdf successfully.

I closed the instance as I realised that leaving running instances and forgetting about them would continously bill to my credits, which would force me to make a new account if I wanted to test out cloud servers again, along with the fact that if I were to leave instances running misconfigured, it could be easily seen as a prime target for malicious activity. According to [Usage.ai, 2026](https://www.usage.ai/blogs/finops/waste/cloud-waste/), leaving my instance running would also cause cloud waste, wasting resources that could have been spent elsewhere due to my ignorance if I were to leave my instance running.

From what I found in a [Superuser forum, 2014](https://superuser.com/questions/750444/difference-between-dns-and-etc-hosts-in-name-resolving-during-an-https-request) article, I would explain the difference between DNS and /etc/hosts to a client, making as simple and readable as possible, as /etc/hosts are what the computer would look at first for web addresses, it is the local address book for the device that is being used, whereas if it cannot be found in /etc/hosts, then it would query the broader DNS system, the public phonebook.
