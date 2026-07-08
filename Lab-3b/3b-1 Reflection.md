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


The lab then had me zip the backup folder up and to name it to be date specific. I firstly edited testscript.sh using `nano`, and afterwards assigning a variable `now`, and using `$` as a substitution and telling bash to run `date`

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/d83eb11d0f4a8749fc37cd137cede91afe5c4b68/Lab-3b/3b-1.06%20ZIP_Archive1.png)

- Why is using absolute paths important in scripts run by cron? 

- What are the benefits of cloud exporting for backups? 

- How does cron differ from manual execution? 

- What happens if SSH keys are not accepted ahead of time? 

- How can login messages help improve user/system engagement? 
