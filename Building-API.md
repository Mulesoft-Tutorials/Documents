
# Building API

We can build API's using two approaches

1. Build using API specification written in RAML and with the help of APIKit Router
2. Build it directly using Anypoint Studio



# Mule Message Structure
![MuleMessage](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/MuleEventandMsg.png) 


# API Proxy

A proxy is an application that provides a level of protection for your API. You don’t have to modify the API to guard against attacks on your web service. Mule Runtime hosts a Mule proxy application. There is a proxy type for each type of web service:

- RAML/OAS Proxy

- WSDL Proxy

- HTTP Proxy

- HTTPS Proxy

API Manager automatically generates the proxy app when you configure the API as an endpoint with a proxy and includes an Autodiscovery element in the app. Mule locks the API until all policies have been applied. The client app (consumer) calls the proxy which forwards the call to the API. After you deploy the app, Mule Runtime calls API Manager using the client ID and secret to get the policies for the API.

In most cases, the proxy you generate in API Manager is suitable for deployment. However, you can modify the proxy to log data to a file or send data to a Splunk account with the Anypoint Splunk Connector, for example.

You can import a proxy that you download from API Manager into Studio as a Mule Deployable Archive. You can then modify the proxy in Studio.

# Creating Proxy Application

After you have created API specification using RAML and published to exchange, you can create the proxy application using API Manager

Please follow below steps to create proxy application

1. Login to anypoint.mulesoft.com and select the API Manager

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/proxy-step1.PNG)

2. Select the environment accordingly

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/proxy-step2.PNG)

3. Click on Manage API and select **Manage API from Exchange**

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/proxy-step3.PNG)

4. Provide the following fields according based on the API type

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/proxy-step4.PNG)

  API Name : Name of the API published to exchange
  Asset Type : RAML/OAS (Auto populated)
  API Version: 1.0 (Auto populated)
  Asset Version : 1.0.0 (Auto populated)
  Managing Type : cloudhub
  Proxy deployment target : cloudhub
  Mule version : select this option for mule 4
  Implementaiton URI : URL of the service which need to be prpxied
  
  
  click on save.

5. Go to the deployment configurations section

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/proxy-step5.PNG)

  select the the runtime version
  provide the proxy application name to be deployed to runtime
  click on deploy to deploy your proxy application to cloudhub
  
  ![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/proxy-step6.PNG)
  
  

## Applying Policies



## What Is a Flow?

A flow is a connected collection of Mule components.

It usually consists of an inbound endpoint component (from where a message originates), and an outbound endpoint component. Therefore, the flow is responsible for the various processing stages in which the message may undergo.

Each flow may have a processing strategy as well as an exception handling strategy associated with it. A flow may also reference another flow using a flow reference component.

There are three different types of flows in Mule:

Subflows – a synchronous flow inheriting the processing and exception handling strategy of the parent flow
Synchronous Flows – a synchronous flow with its processing and exception handling strategy
Asynchronous Flows – an asynchronous flow with its processing and exception handling strategy

## Subflows

We use subflows to group common logic. Subflows are processed synchronously; that is, execution of the calling flow halts until the subflow is complete.

The subflow is called using a flow reference component. Additionally, subflows inherit the processing strategies and exception handling strategies of the calling flow. We can call a subflow from multiple different flows. Should we not wish to inherit these strategies, we could call a synchronous flow.

## Synchronous Flows

Like a subflow, a synchronous flow is also processed synchronously. This means that when we call a synchronous flow, it must complete before the parent flow resumes its execution.

We add synchronous flows to our Mule application by adding regular flows; there is no “synchronous flow” component. We add a regular flow component:
Unlike a subflow, it doesn't inherit the processing and exception handling strategies of the calling flow. Consequently, the processing and exception handling strategies of the calling flow do not affect the behavior of this type of flow.

For these reasons, this type of flow is ideal for transactional processing since messages processed using synchronous flows execute on a single thread.


## Asynchronous Flows

Asynchronous flows execute in parallel to the calling flow; i.e., they are processed asynchronously.

We add asynchronous flows to the Mule application in the same way we add synchronous ones. So, what makes the flow asynchronous, is that we call it from within an asynchronous scope. We can do this by wrapping the flow reference component in an async component

Similarly to synchronous flows – they don't inherit the processing and exception handling strategies of the calling flow.

Additionally, messages processed using asynchronous flows execute on multiple threads, making this type of flow ideal for time-consuming tasks such as sending out emails or performing I/O operations.

