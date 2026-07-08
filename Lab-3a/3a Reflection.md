# 3a-1 Domain, DNS and TLS Certificates with Let's Encrypt 

Labs 3a-1 and 3a-2 is similar, so I have combined them both into this reflection.

During this lab, I have set up a complete internet-facing web presence. I have configured my cloud VM to also support port 443 HTTPS, along with grabbing a free domain link from Duck DNS, and linked it with my EC2 instance's public IP address.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4ee95f3ab0221bb7533ca464eb7947abdcdf6c63/Lab-3a/3a-1.01%20Domain_Registered.png)


I then SSH'ed into my cloud virtual machine using `ssh -i (keyname).pem ubuntu@(EC2 public IP)`, after which I installed apache using `sudo apt install apache2`

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4ee95f3ab0221bb7533ca464eb7947abdcdf6c63/Lab-3a/3a-1.02%20Apache_Installed.png)


After linking my cloud's public IP to my domain in Duck DNS, I opened it up on my browser, and used `nslookup` and `dig` to ensure that it has been linked correctly.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4ee95f3ab0221bb7533ca464eb7947abdcdf6c63/Lab-3a/3a-1.03%20Domain_Tested.png)


The lab required me to use a new package manager, `snap`. [Medium, 2025](https://mikerodionov.medium.com/snap-vs-apt-e2bd51412c8c) outlines that the difference between `snap` and `apt` is that `snap` installs the most recent versions of items, whereas `apt` may download slightly outdated versions of it. From this, I learned that we use `snap` to download `certbot` as `snap` offers the most recent versions of it, whereas `apt` may use slightly outdated versions. Which is important as we would want to get the most up to date and secure version of certbot for our TLS certificates. I then used `sudo snap --classic certbot` and `sudo cerbot --apache` to get a TLS certificate for my apache web server.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4ee95f3ab0221bb7533ca464eb7947abdcdf6c63/Lab-3a/3a-1.04%20Certbot_Installed.png)

Going back to my web server using the new domain that I got, I have verified that HTTPS is being used and the connection is secure and is verified by Let's Encrypt.

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4ee95f3ab0221bb7533ca464eb7947abdcdf6c63/Lab-3a/3a-1.05%20Valid_TLS.png)


Finally, I did a auto renewal dry run by running `sudo certbot renew --dry-run`, with the successful results shown in the screenshot below

![Image](https://github.com/kamaaleimaan/ICT171_ISEA_Labs/blob/4ee95f3ab0221bb7533ca464eb7947abdcdf6c63/Lab-3a/3a-1.06%20Renewel_Output.png)


DNS resolves web addresses to IP addresses, as computers only read IP addresses, we cannot expect humans to remember each and every IP address, so we link domain names to IP addresses, for example the web address dns.google being linked to IP address 8.8.8.8. DNS server would be present in a network structure to take in these DNS queries and resolve these web addresses to IP addresses, making it much more readable for humans and making it easy to remember. DNS is crucial as we are going into a future where our reliance on the internet grows stronger, so having these readable web addresses support this reliance that is going to be growing.

To answer why DNS propogation takes time, I had to learn what it meant first, according to [SiteGround, 2025](https://www.siteground.com/kb/dns-propagation/), DNS propogation is the process of updating information on the Internet’s DNS servers. From what it is, DNS propogation would take a long time as it does the updating of information such as IP addresses on many servers across the Internet.

From the official website of [Let's Encrypt, 2025](https://letsencrypt.org/how-it-works/), they outline that a Client would firstly query the Let's Encrypt Certificate Authority (CA) to ask what it needs to do to prove that the Client is the domain owner. The Let's Encrypt CA would then look at the domain name requested and issue the Client a set of challenges. After the client completes these challenges, the CA is notified that it’s ready to complete validation. Afterwards, the CA’s job is to check that the challenges have been completed to satisfaction.

If TLS is not configured on the public-facing site, all connections to the site would be unprotected, and is vulnerable to packet sniffing, the data that is being sent in and out are unencrypted, meaning that it is in plain text, so any passwords entered or confidential information could be easily retreived as it has not been encrypted and is using the unsecure HTTP instead of HTTPS.

Leaving my cloud VM running for months would cause my credits to drain, ultimately using it all up and me not being able to access my cloud VM anymore with the exception of paying for a paid tier to regain access to it.

As explained earlier, HTTPS is the secure version of HTTP, it is crucial for modern web applications as now most modern web applications require an account of sorts or a method of payment, HTTPS is important as it encrypts the data that is being sent back and forth, giving it extra protection against eavesdroppers or Man-in-the-Middle attacks.

Let's Encrypt issued my site's TLS certificate

- How long is your certificate valid for, and how can it be renewed?


- What happens if a certificate expires and is not renewed? 

- Why does Let’s Encrypt require port 80 or 443 to be open for verification? 
