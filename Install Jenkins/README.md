# Install and Setup Jenkins

This document is regarding the installation and configuration of Jenkins.

## Installation Process 

### a) Install Java

Command to Execute -> sudo yum install java-1.8.0-openjdk-devel

![installation1]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation1.PNG ) 

### b) Enable the Jenkins repository

Command to Execute -> curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo

![installation2]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation2.PNG ) 

### c) Add the repository to your system

Command to Execute -> sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

### d) Install the latest stable version of Jenkins by typing

Command to Execute -> sudo yum install jenkins

![installation3]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation3.PNG )

#### e) Start the Jenkins service

Command to Execute -> sudo systemctl start jenkins
Command to Execute -> systemctl status jenkins
Command to Execute -> sudo systemctl enable jenkins

### f) open your browser and type your domain or IP address followed by port 8080

URL -> http://your_ip_or_domain:8080

![installation4]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation4.PNG )

then,

![installation5]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation5.PNG )

then,

![installation6]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation6.PNG )

This process will take some time to install the plugins for jenkins 

Note: I got into an issue here some of the plugins did not got installed so then

go into /var/jenkins/plugins/ dir and give executable permission here to all files & restart the jenkins service.
Command to Execute ->  /var/jenkins/plugins/
Command to Execute ->  chmod 777 *
Command to Execute ->  sudo systemctl restart jenkins

Now the plugins will get install

![installation7]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation7.PNG )

Once the jenkins user is created you will get on this page

![installation8]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Install%20Jenkins/lib/images/jenkins/installation8.PNG )

![Axwaylogo]( https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png ) 
### Axway Team


