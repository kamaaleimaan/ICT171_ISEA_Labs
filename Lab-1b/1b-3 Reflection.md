# 1b-3 File Search, Analysis & Archiving in Linux 

In this lab, I used command-line tools to locate, inspect and search through various text files within archives. This allows for me to have the essential skills in system administration and to be able to do simple file forensics with Linux. I started off with downloading a bz2 file from my bridging module and extracting it using `bunzip2` and `tar -xvf`. After which I verified the file listings of the file directories using `ls -l` to view them.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/82ad0c56680ac702e1cc0b7bcb48f2a9f45aeffd/Lab-1b/1b-3.01%20Archive_Extracted.png)


I then used the `find` command to locate where a certain text file is within my system, even though my system is small this would definitely help me if I need to look through a big archive or a server.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/82ad0c56680ac702e1cc0b7bcb48f2a9f45aeffd/Lab-1b/1b-3.02%20FileName_Search.png)


Then I had to be able to search through texts using `grep` with the recursive flag, which was shown in the image below. It helps to locate which text file it is and where it is. I had to edit in text as the following command of `grep -r -c` would not have shown much, adding in the `-c 3` would just mean to show the previous and next 3 lines of text after the search within the text file.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/82ad0c56680ac702e1cc0b7bcb48f2a9f45aeffd/Lab-1b/1b-3.03%20Grep_Search.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/bb5706a0dbc5b2c831dea442cd5c05d3b770a47b/Lab-1b/1b-3.04%20Contextual_Search.png)


After which I had to do date and sized based searches using find. The commands given in the lab were not specific enough, so I found out that by adding `| sort | head 3 | tail -1`, I could sort out the first three results and only keep the third one as requested from the lab for the date based search. For the file sized search, since the lab outlined the size already, I just placed it into the command and the results are as shown in the image.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/bb5706a0dbc5b2c831dea442cd5c05d3b770a47b/Lab-1b/1b-3.05%20Date_Based_Search.png)
![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/bb5706a0dbc5b2c831dea442cd5c05d3b770a47b/Lab-1b/1b-3.06%20Size_Based_Search.png)


By using `du -a`, I was able to find the largest file, and using the sorting tool from earlier, I was able to list it from largest to smallest, the image below shows the largest down,

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/bb5706a0dbc5b2c831dea442cd5c05d3b770a47b/Lab-1b/1b-3.07%20Largest_File.png)


Finally, I learned how to see text frequency using the `sed -e 's/\s/\n/g' < file.txt` command to see it. Through this I learned that there are a ton of different ways to see the text, `s/` or `\s`, these are outlines to tell the terminal on how to display the text inside the text file. Putting this all together would make each word be in a new line

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/bb5706a0dbc5b2c831dea442cd5c05d3b770a47b/Lab-1b/1b-3.08%20Text_Frequency.png)


These commands can be used as search tools to be used in cybersecurity investigations as they can help analysts quickly locate and identify suspicious files in large amounts of data. Like how I used the `find` command in this lab, analysts can locate files based on their name, size and when it was modified, making it a key tool for searching for malware or hidden files. The `grep` command is also another useful search tool as it can search for specific keywords, whether it be error messages, malicious command or IP addresses which can be key evidence behind an attack that analysts can identify. By using the `du` command, analysts could also locate unusually large files that can indicate hidden malware, and the sed command can be used to identify frequently occuring patterns.

Scripting improves repetetive tasks by adding convinient ways to automate frequently used commands, by adding flags like `-r`, users do not have to go into each individual file to change permissions for example. 

The limitations I ran into were that you had to use sort to be able to really get to the bottom of what you want, without it it was a mess of big data that I was not willing to sieve through to get the answer. These commands work hand in hand to be able to help get the data I needed.
