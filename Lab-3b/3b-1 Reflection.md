# 3b-1 Bash Backup Scripting, Cron Jobs & Cloud Export 

For this lab, I went more into Bash scripting to create file backups, and to schedule these backups using cron jobs, and sending these backups to my cloud server. I started with editing a new executable bash_testing.sh using `nano`. In this executable I used the `for` loop and assigned variables `{1..5}`, along with the `do`, `done` loop and used `echo` to echo out the variables. I then used `chmod 777` to ensure that it is executable. I then ran `./bash_testing.sh` to run the executable.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2cdc5e12bc0e12a2dad4ef880211799e10123974/Lab-3b/3b-1.01%20Bash_Scripting1.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2cdc5e12bc0e12a2dad4ef880211799e10123974/Lab-3b/3b-1.02%20Bash_Result.png)


I then used `touch` to create files to backup in the `/home/kamaal/Documents` folder, along with using `ls -R` to confirm that they have been created.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2cdc5e12bc0e12a2dad4ef880211799e10123974/Lab-3b/3b-1.03%20Creating_Files.png)


I then had to create an executable testscript.sh to be able to copy the files in the `/home/kamaal/Documents` folder and rename the folder into backup. I created and edited the executable using `nano`, and had the `cp -R` command inside the executable to copy over the files and create the new backup. Then I ran `chmod 777` on the executable to ensure that it can be executed. After which I ran `./testscript.sh` to run the executable.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2cdc5e12bc0e12a2dad4ef880211799e10123974/Lab-3b/3b-1.04%20Testscript.png)

I then had to move it to `/usr/bin` to ensure that it can be ran anywhere, I firstly removed the previous backup folder using `rm -r backup` and made sure to change the owner to root using `sudo chown root testscript.sh`, and moving it over using `sudo mv testscript.sh /usr/bin/testscript.sh`. I then ran the script from `/usr/bin` using `/usr/bin/testscript.sh`.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/2cdc5e12bc0e12a2dad4ef880211799e10123974/Lab-3b/3b-1.05%20Moving_Testscript.png)


The lab then had me zip the backup folder up and to name it to be date specific. I firstly edited testscript.sh using `nano`, and afterwards assigning a variable `now`, and using `$` as a substitution and telling bash to run `date` and to place that as the name in `now` when naming the zip file using `zip -r`. I then ran the script using `sudo /usr/bin/testscript.sh`.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/d83eb11d0f4a8749fc37cd137cede91afe5c4b68/Lab-3b/3b-1.06%20ZIP_Archive1.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/87391328d05e397a7a22c6b22944b7318a9aa1fd/Lab-3b/3b-1.07%20ZIP_Result1.png)


I then had to put it into a crontab to make sure that the backups are created every hour, from what I am inputting, I am inputting that I want `/usr/bin/testscript.sh` to run every hour, every day, every month, every day of the week with `9 *  * * *` followed by who I would want it to run, which I put as `root`.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ba123d5deba945e70c03ddd6740f75d2b2c2c7bd/Lab-3b/3b-1.08%20Crontab.png)


The lab then required me to send these backups to my cloud, so I had to `nano` the executable and add in the `scp -i /home/kamaal/(mykey).pem "/home/kamaal/backup_$now.zip" ubuntu@(EC2 Public IP):~/` to make sure that it send it over to my cloud server.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ba123d5deba945e70c03ddd6740f75d2b2c2c7bd/Lab-3b/3b-1.09%20SCP_Cloud1.png)


After which I left my laptop alone for awhile to make sure that the cron jobs were doing their work, and after two hours I saw that two files were correctly created and exported over to my cloud server, as shown in the two screenshots below.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/87391328d05e397a7a22c6b22944b7318a9aa1fd/Lab-3b/3b-1.10%20Successful_Cron.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/87391328d05e397a7a22c6b22944b7318a9aa1fd/Lab-3b/3b-1.11%20Successful_SCP.png)


Actually I did run into the problem of using `~/Document` firstly instead of using absolute paths. According to [fivenines.io, 2026](https://fivenines.io/blog/what-is-a-cron-job-in-linux/), cron jobs are ran in a minimal environment, meaning that the paths and other environment settings would be different from the interactive shell. Meaning that for reliability sakes, absolute paths must be ran in cron. I had to change it midway through to the screenshots that you see in this reflection.

The benegits of cloud exporting is that there are backups located in different systems, so if the original system were to need the backup but for some reason it cannot gain access to it or lost it, it can rely on the cloud export for the backups, this can be mirrored to a larger scale where companies need to have tons of backup data, and exporting them into the cloud would be beneficial for them. 

Cron differs from manual execution as it can execute tasks at scheduled intervals, whereas manual execution would need to have a human in real-time type in commands to be able to execute the code or commands.

If SSH keys are not accepted ahead of time you would not be able to establish access to the device that you are trying to SSH into as SSH cannot verify and trust correctly until you have the correct SSH key to be able to SSH into the device.

Login messages can help identify if you have logged into or are using the correct system profile. These login messages could also help improve by giving useful information when a user signs in. For example whenever I SSH into my cloud server they would let me know of the last login, so I know that I am the only one that has been logging into my cloud server. These login messages could also display system notices, maintenance announcements, and security warnings for users to tend immediately to.
