
# Mulesoft Deployment Options

There are two deployment models 

1. Deploy to Cloudhub
2. Deploy to on-premises


## 1. Deploy to Cloudhub

We can deploy applicatio into cloudhub using below options

1. Directly from Studio
2. Using Runtime Manager
2. Using CICD process with the help of Mule Maven Plugin

### 1.1 Directly from Studio

1. Right click on the project root and select Anypoint Platform -> Deploy to Cloudhub

![DeploytoCloudhub](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/Deploy-Step1.png)


2. Configure your mulesoft credentials and login to Anypoint platform if you have not done.

3. Runtime Manager gets opened up and let you specify the app name, run time version, worker size and workers.

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/Deploy-Step2.png)

4. If you have any runtime variables, you can specify them under properties tab

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/Deploy-Step3.png)

5. Click on Deploy Application.

6. Once the application gets deployed, verify the logs to see for any start up errors during deployment

### 1.2 Using Runtime Manager

1. Login to Anypoint.Mulesoft.com and select Runtime Manager

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/Deploy-Step4.png)

2. Select the environment were you want to deploy
![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/Deploy-Step5.png)

3. Provide the App Name and browse to select the packaged jar generated from Studio , select the runtime version, size and worker. Click on deploy application

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/Deploy-Step6.png)

4.  Once the application gets deployed, verify the logs to see for any start up errors during deployment

### 1.3 Using Mule Maven Plugin

In addition to using Anypoint Studio, Anypoint Runtime Manager to deploy applications to CloudHub, you can also deploy, redeploy, or undeploy applications by using the Mule Maven plugin. To do so, you must meet certain prerequisites, and configure your CloudHub deployment strategy in your project’s pom.xml file.

Configure the CloudHub deployment strategy in your project’s pom.xml file so you can deploy, redeploy and undeploy your Mule application using the Mule Maven plugin.

Inside the plugin element in your project’s pom.xml file, configure your CloudHub deployment, replacing the placeholder values with your CloudHub information

```
<plugin>
  <groupId>org.mule.tools.maven</groupId>
  <artifactId>mule-maven-plugin</artifactId>
  <version>3.3.2</version>
  <extensions>true</extensions>
  <configuration>
    <cloudHubDeployment>
      <uri>https://anypoint.mulesoft.com</uri>
      <muleVersion>${app.runtime}</muleVersion>
      <username>${username}</username>
      <password>${password}</password>
      <applicationName>${cloudhub.application.name}</applicationName>
      <environment>${environment}</environment>
      <properties>
        <key>value</key>
      </properties>
    </cloudHubDeployment>
  </configuration>
</plugin>
```
Please refer below link for more information about cloudhub deployments
[Cloudhub](https://docs.mulesoft.com/mule-runtime/4.1/deploy-to-cloudhub)

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/CICD.png)

## 2. On-Premises Deployment Model

Mule application deployment consists of two main aspects:

 - The Mule runtime engine instance

- The Mule applications deployed to that Mule instance

When you deploy applications to CloudHub or to Anypoint Runtime Fabric, these services take care of the Mule runtime engine instances needed to run applications.

When you deploy applications on-premises, you are responsible for the installation and configuration of the Mule runtime engine instances that run your Mule applications. Because you have complete control of the on-premise instance (unlike with CloudHub or Runtime Fabric deployments), you must understand the characteristics specific to on-premises deployments

Mule runtime engine unpacks all applications at runtime, removes the original .jar files inside the /apps directory, creates a new folder for each application, and names each folder with the same name as the application file (minus the .jar extension).

To confirm successful deployment, verify the following:

The status of the application in the console is DEPLOYED.

An unpacked application folder exists in the /apps directory of your Mule instance: for example, for stockTrader.jar, $MULE_HOME/apps/stockTrader.

An anchor file exists for a running app: for example, $MULE_HOME/apps/stockTrader-anchor.txt.

If you want to store your applications in a different location, you can store them on Unix-based systems by creating a symlink to your application directory from $MULE_HOME/apps.

