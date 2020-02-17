# Install and Setup Gitlab


This document is regarding the installation and configuration of GitLab.

### Installation Process 

### a) Start by installing the following necessary dependencies using the yum package manager

### Command to Execute -> yum install curl policycoreutils-python openssh-server

![installation1]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20And%20Configure%20Gitlab/lib/images/git/installation1.PNG ) 

### b) Install Postfix service to send notification emails, and enable it to start at system boot

### Command to Execute -> yum install postfix



Command to Execute -> systemctl start postfix
Command to Execute -> systemctl enable postfix
Command to Execute -> systemctl status postfix


![Axwaylogo]( https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png ) 

### Axway Team
