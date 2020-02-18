# Configure GitLab and Jenkins

This document is regarding how to configure Gitlab and Jenkins. If you have already setup Jenkins and GilLab now you can follow this document to start working on the configuration part.

Open the Jenkins and Now go to "Manage Jenkins" option and then "Manage Plugins"

![installation1]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation1.PNG ) 

Install the GitLab Plugins

![installation2]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation2.PNG )

Go to the Gitlab and click on settings option under your profile icon in right corner

![installation3]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation3.PNG )

Then go to the option Access Token using the left navigation bar

![installation4]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation4.PNG )

Generate a new token and select the "api" Scope and a expiry time. Now copy the token and open the jenkins and go to  "Credentials" option

![installation5]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation5.PNG )

Open it and select add credentials option

![installation6]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation6.PNG )

Once you have successfully added the Credentials (token based) you can start connection to GitLab from Jenkins.

![installation7]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation7.PNG )

Now go to "Manage Jenkins" option and then "Configure System"

![installation8]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation8.PNG )

Now add the Gitlab settings here and select the credentials that you created in above step

![installation9]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation9.PNG )

And test your connection & Save it.

Now Create a "New Item" and select a Freestyle project option.

![installation10]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation10.PNG )

From the Gitlab you can copy the path of the Git-Repo

![installation11]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation11.PNG )

No changes in general 

![installation12]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation12.PNG )

Under the Source Code Management, select Git option and enter the Git repo URL's

![installation13]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation13.PNG )

In Build Triggers option select Poll SCM and enter "* * * * *"

![installation14]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation14.PNG )

Now under the Build use Execute shell and write your shell scripts to use proj pack and proj deploy. 

For more details visit docs.axway - https://docs.axway.com/bundle/APIGateway_753_PromotionGuide_allOS_en_HTML5/page/Content/DeployPromoGuideTopics/deploy_package_tools.htm

![installation15]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation15.PNG )

Save these changes in Jenkins

Now go to GitLab - Under settings of Gitlab then go to integration

![installation16]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation16.PNG )

Copy the Jenkins job link

![installation17]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation17.PNG )

Add this URL in the Gitlab setting and select the option "Merge requests events"

![installation18]( https://github.com/Axway-API-Management-Plus/CI-CD-with-API-Gateway-Dev-Ops-Approach/blob/master/Configure%20GitLab%20and%20Jenkins/lib/images/configure/installation18.PNG )


Note: The idea is to only do deployment once the merge request is accepted by the authorize reviewer. Hence we select "Merge request events" on Gitlab and "******" on Jenkins.

Hence when a new branch is created for the new API development then take an copy from master branch and then work on the new branch. Once completed you can create a merge request to merge new branch to master branch. The reviewer will check the merge request and after evaluation he will approve the merge request then Jenkins will make the deployment and after that SOAP-UI test cases will run and report will be generated.


![Axwaylogo]( https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png ) 
### Axway Team
