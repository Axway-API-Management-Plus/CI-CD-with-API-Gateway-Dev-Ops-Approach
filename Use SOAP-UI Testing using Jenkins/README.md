# Use SOAP-UI with Dev-Ops Approach


This document is regarding how to use SOAP-UI and trigger the test cases, generate reports and summary of test cases.

Download SOAP-UI - https://www.soapui.org/

First we need to create a SOAP-UI project using the SOAP-UI in our local machine then we could use the SOAP-UI testrunner scripts to be integrated into Jenkins so that after each Merge acceptance and deployment these SOAP UI test cases are run.

a) Create SOAP-UI project for healthcheck policy

![installation1]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Use%20SOAP-UI%20Testing%20using%20Jenkins/lib/images/soap-ui/installation1.PNG ) 

b) Create a Test case of the project created and add the assertions

![installation2]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Use%20SOAP-UI%20Testing%20using%20Jenkins/lib/images/soap-ui/installation2.PNG ) 

c) Add assertions based on the HTTP Status Code like https status code - 200 is success for heathcheck policy

![installation3]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Use%20SOAP-UI%20Testing%20using%20Jenkins/lib/images/soap-ui/installation3.PNG ) 

d) Now take the Export of this Project created in SOAP-UI

e) Install SOAP-UI in to the VM (linux) machine so that you could use jenkins to run the test cases.

f) Now go to bin directory of SOAP-UI (eg - /opt/SoapUI-5.5.0/bin/ )

g) Now use the testrunner here to Run SOAP-UI testcases and based on assertions check the test cases and you will get a summary report of the test cases which will give you idea of how many test cases get passed or failed.

Command- 

./testrunner.sh -a -f/root/jenkins/testcases/report/<report file name for SOAP-UI> /opt/SoapUI-5.5.0/<SOAP-UI project export in form of .xml>.xml -r

In case your test case is in the GitRepo 
 
./testrunner.sh -a -f/root/jenkins/testcases/report/<report file name for SOAP-UI>  /var/lib/jenkins/workspace/<RepoName>/<SOAP-UI project export in form of .xml>.xml -r

![installation4]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Use%20SOAP-UI%20Testing%20using%20Jenkins/lib/images/soap-ui/installation4.PNG )


h) Place this command in jenkins build under Execute Shell so that after every proj pack and proj deploy this is run.the SOAP-UI test case autmatically after every deployment and with each development update the SOAP-UI test case also to do regression and non-regression test. 

![installation5]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Use%20SOAP-UI%20Testing%20using%20Jenkins/lib/images/soap-ui/installation5.PNG )

Now at each deployment you can add the test cases of SOAP-UI in xml exports project in the GitLab repo and can be updated at each development stage. Hence you can now perform regression and non- regression testing uisng SOAP-UI.



![Axwaylogo]( https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png ) 
### Axway Team
