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

- Why does DNS propagation take time?


- How does Let’s Encrypt validate domain ownership? 

- What are the risks if TLS is not configured on a public-facing site? 

- What could happen if you leave your cloud VM running for months?

- Why is HTTPS important for modern web applications? 

- What entity issued your site’s TLS certificate? 

- How long is your certificate valid for, and how can it be renewed? 

- What happens if a certificate expires and is not renewed? 

- Why does Let’s Encrypt require port 80 or 443 to be open for verification? 
