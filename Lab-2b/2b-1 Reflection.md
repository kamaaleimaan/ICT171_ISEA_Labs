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


Once I have completed the lab, I then closed the instance.

![Image]()


Going over to the budget and monitoring 

- What were the benefits of cloud deployment over local virtualisation? 

- How does Apache serve files, and how did you verify this? 

- What did you learn about file ownership and permissions? 

- What risks are associated with leaving instances running? 

- How would you explain the difference between DNS and /etc/hosts to a client? 
