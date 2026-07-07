# 2b-2 Introduction to Bash Scripting & System Automation 

This lab introduced me to Bash scripting, something that is still going to take awhile to get my head wrapped around, I started off with something simple like making a directory in Bash using mkdir, creating a text file using touch inside the directory and have it output something using nano to firstly edit what is inside the text file and then using cat to take a look at the file. The difference between copy (cp) and move (mv) in bash is that cp would leave the file in whichever directory is in, while creating a new file of the copied file in the desired location, whereas mv would take the file from whichever directory it is in, and would create the same file into the desired location, and removing it from whichever directory it was originally in.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ee4f9d0a3203d92485fea3398232e89f12657290/Lab-2b/2b-2.01%20Files_Created.png)


Transitioning into making an executable to be able to output a custom message, I started off with creating using touch to amke hello_world.sh (which I learned later that I did not have to do), followed by editing it using nano, from here I had to learn what #!/bin/bash is, [GeeksForGeeks, 2026](https://www.geeksforgeeks.org/linux-unix/shell-scripting-define-bin-bash/) refers to it as a 'shebang', it would start off with the special character #!, followed by the path to the interpreter, which in this case is bash. It could theoretically be used without a shebang, since it would default to the default terminal which is bash, but it may run into some issues on some systems, which is why it is always placed at the beginning of these scripts, to specify that bash should be the interpreter of the code. After which I just made a simple echo message to personalise my script output. I then ran chmod 777, as files that are just created may not have the execute permission onto anyone, so even if I am using my admin profile, I still would not be able to execute it as there are no permissions on the file.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ee4f9d0a3203d92485fea3398232e89f12657290/Lab-2b/2b-2.02%20Bash_Script.png)


The lab then tasked me with making an executable that shows loops and conditionals, I created a new file using touch and edited it using nano again, the first image below shows what is inside the executable. From here I learnt the basics of Bash scripting, I learnt that adding a $ at the beginning of an item would differentiate it from itself, if I did not put $ infront of it, it would just echo out i instead of the variables 1 through 5 that I wanted. I also learnt about do and done, where done would close a boundary loop, whereas fi is a partner to if and closes conditional statements. I also learned more about regular expressions (regex) through the form of only accepting digits, ^[0-9]+$, where ^ indicates the beginning of the string, [0-9] indicating the boundary of digits accepted, + means it can be inputted more than once and $ to indicate the end of the string. the ! at the beginning indicates that if the input is anything besides the regex, it would echo out the appropriate result. I also added a greater, equal or lesser than 10 using -gt, -eq, elif, then and else. The second image shows that it has ran successfully. The for loop in this instance would work by telling bash to repeatedly do the same code with the next variable.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ee4f9d0a3203d92485fea3398232e89f12657290/Lab-2b/2b-2.04%20Loops_Conditional2.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ee4f9d0a3203d92485fea3398232e89f12657290/Lab-2b/2b-2.03%20Loops_Conditional.png)


Finally, 

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ee4f9d0a3203d92485fea3398232e89f12657290/Lab-2b/2b-2.06%20Resource_Monitor2.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/ee4f9d0a3203d92485fea3398232e89f12657290/Lab-2b/2b-2.05%20Resource_Monitor1.png)

- What output does `free -h` show? 

- How would you monitor network bandwidth in a Bash script?

- Why is automation important for admins?
