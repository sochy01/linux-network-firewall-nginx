Linux Network, Firewall & Nginx Setup

This project is part of my practical Linux networking and server configuration exercise.
The goal of this task was to configure a Linux machine, set up a static IP, enable a firewall, install and configure Nginx, and explore basic DNS settings.

I documented each step and pushed all configuration files and screenshots here.

1. Network Configuration (Static IP)

I checked my network interface using ip addr and ip route.

I edited the Netplan YAML file in /etc/netplan to assign a static IP address to my network interface.

I added a gateway and DNS nameservers (8.8.8.8) so that the machine can connect to the internet.

After saving, I applied the configuration using:

sudo netplan apply

To confirm, I ran ip addr and ping 8.8.8.8 to make sure the connection was working.


2. Firewall Setup

I installed and enabled the Ubuntu firewall using UFW:

sudo apt update

sudo apt install ufw -y

sudo ufw enable


I allowed necessary services like SSH, HTTP, and HTTPS:

sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https


I checked the firewall status with:

sudo ufw status

3. Nginx Installation & Basic Website

I installed Nginx on the server using:

sudo apt update
sudo apt install nginx -y


I created a basic HTML page inside /var/www/html/ and confirmed that it loads in the browser.

I also copied my Nginx configuration (nginx.conf) and website files into this repo for documentation.

4. DNS (Basic)

I explored DNS by editing the /etc/hosts file to map a test domain like:

127.0.0.1   mywebsite.local


After this, I was able to use ping mywebsite.local locally to test name resolution.

5. Screenshots

I included screenshots of:

Netplan configuration

Firewall rules

Nginx website running in the browser

DNS testing

You can find them in the screenshots/ folder.

Summary

This task helped me understand how networking, firewalls, DNS, and web servers work together on a Linux system.
I learned how to manually set a static IP, secure the system with UFW, deploy a simple Nginx website, and use DNS to resolve local domains.
