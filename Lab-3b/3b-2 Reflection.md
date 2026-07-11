# 3b-2 Additional Server Setup on Ubuntu 

In this lab I went ahead and installed an additional service of my choosing, I went and chose MariaDB. The reason why I chose MariaDB is because having a way to search through and organise databases is a fundamental service to have in a real-world environment as companies would be dealing with a ton of data such as thousands or more customers who would each have their accounts and their own seperate data. Not having a way to properly organise through the data can cause a ton of traffic and waiting as data cannot be accessed or it would take a long time to look for the data.

Starting off, I went ahead and updated the package lists using `sudo apt update` before installing MariaDB using `sudo apt install -y mariadb-server mariadb-client`, from here I learnt that using `-y` would automatically say yes to the installs, as before I had to manually type in `y` to confirm the install.

![Image]()


After that, I used started MariaDB using `sudo systemctl start mariadb` to get the service started and to enable the service using `sudo systemctl enable mariadb`, along with checking the status using `sudo systemactl status mariadb` to make sure that the output is active, as seen in the screenshot below.

![Image]()


Using the `sudo mariadb-secure-installation` command, I was able to secure my MariaDB server by setting root password, removing anonymouse users, not allowing remote root login, removing the test database and to reload the privilege tables.

![Image]()


Finally, I had to verify MariaDB by going into the MariaDB shell by using `sudo mysql -u root -p`, and looking through the database by using the `SHOW DATABASES;` command inside the MariaDB shell, and safely exiting by using `EXIT;`

![Image]()
