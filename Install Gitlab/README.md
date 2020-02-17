# Install and Setup Gitlab


This document is regarding the installation and configuration of GitLab.

## Installation Process 

### a) Start by installing the following necessary dependencies using the yum package manager

Command to Execute -> yum install curl policycoreutils-python openssh-server

![installation1]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation1.PNG ) 

### b) Install Postfix service to send notification emails, and enable it to start at system boot

Command to Execute -> yum install postfix

![installation2]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation2.PNG ) 

Command to Execute -> systemctl start postfix
Command to Execute -> systemctl enable postfix
Command to Execute -> systemctl status postfix

![installation3]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation3.PNG )

### c) Add the GitLab package YUM repository to your system

Command to Execute -> curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash

![installation4]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation4.PNG )

### d) Install the GitLab Community Edition package and make sure to change ‘http://gitlab.GUI.com‘ to the URL at which you want to access your GitLab instance from a web browser.

Command to Execute -> EXTERNAL_URL="http://gitlab.GUI.com" yum install -y gitlab-ce

(Replace the "gitlab.GUI.com" hostname by the one you want to access the Gitlab-UI)

![installation5]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation5.PNG )

#### e) Now, open a web browser and access your gitlab instance using the same url used in step d)

First you need to create a new password for your root user on Gitlab

![installation6]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation6.PNG )


Now you can create a new project in Gitlab.

![installation7]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation7.PNG )

Now once configured the project name you will get the option of the using the key to enable ssh that will help in pull and push & commit.

First you create a ssh key using the command -> ssh-keygen -t ed25519 -C "gitlab.GUI.com" (please use the right hostname using the above command)

The above command will create a public key then keep this is the Gitlab (do not use the private key).

Now you can get inside the project (you can create the project using the Readme) ->

![installation8]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation8.PNG )


Now we need to change the port 8080 as we will use the port 8080 in the jenkins

Open the file gitlab.rb

Command to Execute -> vi /etc/gitlab/gitlab.rb

In the End of the file add 

nginx['proxy_set_headers'] = { "X-Forward-Port" => "8080", "Host" => "127.0.0.1:8081" }

Now reload the gitlab-ctl and restart it

gitlab-ctl reconfigure gitlab-ctl restart

Open the file unicorn.rb

Command to Execute -> vi /var/opt/gitlab/gitlab-rails/etc/unicorn.rb

Edit the following line - to change port 8080 - to - 28080

![installation9]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Gitlab/lib/images/git/installation9.PNG )

Restart the gitlab-ctl service

gitlab-ctl restart


![Axwaylogo]( https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png ) 

### Axway Team
