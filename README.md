# Web-Hosting-With-Nginx-On-AWS-Cloud
**This repository contains a web application hosted on the AWS cloud.*

Welcome! This README guide walks you through the process of provisioning, configuring, deploying, and securing a landing page for a startup project (named Sentinel Healthguard) using AWS EC2 and Nginx. It doesn't matter if you’re new to cloud deployments or simply want to see how I set up this environment, you'll find every step detailed below. Feedback is highly appreciated.

## 1. Server Provisioning Steps
To get started, I provisioned an Ubuntu server on AWS EC2. Here’s exactly how I did it:

- Signed in to AWS Management Console: I logged into my AWS account and got to the EC2 dashboard.

b. Launched a New EC2 Instance: I clicked “Launch Instance” and selected the latest Ubuntu Server AMI (Amazon Machine Image).

c. Choosing Instance Type: I picked t2.micro for cost-effectiveness and free tier eligibility.

d. Configured Instance Details: I left most settings as default, ensuring to allow the automatic assignment of a public IP.

e. Added Storage: I used the default 8 GB SSD, which is sufficient for a landing page.

f. Launched And Connected To The Instance: I downloaded the PEM key, set permissions for the .pem file, and then connected via SSH from my local machine using the command format: ssh -i /path/to/key.pem ubuntu@<EC2_PUBLIC_IP>

f. After launching, I confirmed the necessary security configurations were in place in order to allow traffic.


## 2. Web Server Setup
When I logged into the Ubuntu server, I set up Nginx to serve the site. Here's the process:

a. Installed Nginx by first running "sudo apt update" and then "sudo apt install nginx -y"
b. My nginx was already running when tested. But if it's not running, it can be activated with these commands: "sudo systemctl enable nginx" and "sudo systemctl start nginx".


## 3. Deployment Process
With the server ready, I deployed the landing page through these steps:

a. I used scp from my local machine to upload the code file with this command syntax: scp -i /path/to/key.pem /path/to/folder ubuntu@<EC2_PUBLIC_IP>:/tmp/
b. I moved the file to the web root with the command syntax: "sudo mv /tmp/index.html /var/www/html/index.html", "sudo chown www-data:www-data /var/www/html/index.html", and "sudo chmod 644 /var/www/html/index.html"
c. After deploying, I tested the site by opening a browser and visiting http://13.218.63.21/ to confirm the landing page loads (and it did!).


## 4. Accessible IP

The landing page is live at:
http://13.218.63.21/


## 5. Landing Page Screenshot
Below is a screenshot of the landing page as rendered in a browser:

![Landing Page Screenshot](https://github.com/Peace-I/Web-Hosting-With-Nginx-On-AWS-Cloud/blob/main/LandingPage.png?raw=true)


This setup demonstrates a modern, secure, and scalable approach to deploying a dynamic landing page on AWS. If you have questions or want to replicate this, just follow the steps above or reach out for help. Thank you!
