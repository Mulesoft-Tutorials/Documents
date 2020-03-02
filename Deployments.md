
# Mulesoft Deployment Options

There are two deployment models 

1. Deploy to Cloudhub
2. Deploy to on-premises


## Deploy to Cloudhub

We can deploy applicatio into cloudhub using below options

1. Directly from Studio
2. Using Runtime Manager
2. Using CICD process with the help of Mule Maven Plugin

## Directly from Studio

1. Right click on the project root and select Anypoint Platform -> Deploy to Cloudhub

![DeploytoCloudhub]()


2. Configure your mulesoft credentials and login to Anypoint platform if you have not done.

3. Runtime Manager gets opened up and let you specify the app name, run time version, worker size and workers.

![]()

4. If you have any runtime variables, you can specify them under properties tab

![]()

5. Click on Deploy Application.

6. Once the application gets deployed, verify the logs to see for any start up errors during deployment
