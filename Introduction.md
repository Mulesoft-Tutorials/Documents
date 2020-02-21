# Introduction
- - - -

### 1. What is integration and ESB

Enterprise application integration (**EAI**) is the use of technologies and services across an enterprise to enable the integration of software applications. EAI is related to developing Web service integration, service-oriented architecture, content integration and business processes.

**ESB**, which is the abbreviation for “enterprise service bus,” is a software architecture that provides integration of enterprise applications and services for complex architectures, such as middleware infrastructure platforms.
An ESB's primary function is to provide the connections between communicating applications - acting much like a router to control the data. It is commonly used in enterprise application integration (EAI) or service-oriented architecture (SOA) principles. The interaction and communication between components are across the bus, which has a similar function as a physical computer bus to handle data transfer or message exchange between services without writing any actual code.
ESB as an infrastructure software service-oriented model works as a managed message system that provides routing, data transformation, translation upon a client's request and event-interpretation. It is often needed to transform messages into a format that the application can interpret. ESB is also used to change data content or execute services via a rule engine.

### 2. What are the drawback of existing integration model

Due to the nature of ESB and it's central role of orchestrating all systems on the network, it causes the bus itself to be a single point of failure. Also, due to over-abstraction of the individual tools, performance can be reduced. But, you can reduce these disadvantages with efficient monitoring and exception handling. You can also reduce them by using multiple reliable cloud systems and connectors

### 3. Microservice Architecture

Microservices - also known as the microservice architecture - is an architectural style that structures an application as a collection of services that are

- Highly maintainable and testable
- Loosely coupled
- Independently deployable
- Organized around business capabilities
- Owned by a small team

The microservice architecture enables the rapid, frequent and reliable delivery of large, complex applications. It also enables an organization to evolve its technology stack.

In Microservice Architecture, each service is self-contained and implements a single business capability.

Differences Between Traditional Architecture and Microservices
Consider an E-commerce application as a use-case to understand the difference between both of them.

### 4. What is Mulesoft and Application Network

API-led connectivity is a methodical way to connect data to applications through reusable and purposeful APIs. These APIs are developed to play a specific role – unlocking data from systems, composing data into processes, or delivering an experience

The main purpose of API-led connectivity is to enable the integration flows to be reused by many parties and to be reused inside the integration platform. With the reusability of the already available logic (implemented in flows), the developers can evolve their logic in faster and safer ways, leading to a short time to market. APIs are created in layers and the best plus point as compared to E2E approach is that more components (flows) can be reused which makes easier to implement new systems and services.

  #### System API ####
  
  This is the foundational layer of the three-layer architecture. These APIs can be defined for various domains of an organization, for example, ERP, key customer and billing systems, proprietary databases, etc. System APIs provide a means of accessing these underlying systems of records and exposing the data in canonical formats. A System API defines the contract RAML/WSDL to describe how to interact with the domain. For example, a System API for a customer domain can contain resources with methods like GET, POST, PUT, and DELETE, and the related schemas (XSD, JSON) and responses (200, 400, 500, etc).
  
  Basically, one can see that System APIs generally expose the sensitive information of an organization. They should not be exposed for public use

 #### Process API ####
 
 Process layer APIs are responsible for shaping the data by orchestrating and choreographing various data by calling multiple System APIs. The orchestration involves the aggregating, splitting, and routing of data. The main purpose of Process APIs is to strictly encapsulate the business process independent of the source systems (System APIs) from which the data originates. 

For example, in a purchase order process, it needs to interact with various domains of the organization. The Process API (purchase order/order fulfillment) interacts with the already available System APIs to implement the logic.

The Process APIs should be held privately inside the organization as per recommendation and should not be exposed for public use.

#### Experience API ####

At this point, we have all the sensitive information of an organization exposed privately by System APIs, and the Process APIs have already exposed the business process logic. The business process data is consumed across a broad range of clients/channels with different formats. For example, our Order Purchase API (Process Layer) has exposed data in the JSON format, but we have a client application that accepts only XML format, or vice versa. This simple transformation logic is implemented in the Experience Layer and the implementations are exposed as Experience APIs.

In other words, Experience APIs are the means by which data can be reconfigured easily to meet the needs of multiple audiences. Also, we can remove the unnecessary methods and expose only the necessary methods in Experience APIs in a simple way.

The Experience APIs are the ones which should be exposed publicly for consumption. In short, they are the final products of an organization in the API-led connectivity approach. Various policies can be applied to the APIs as well, as they can be monetized to earn revenue for the organization.
 

### 5. Anypoint studio installation and setup

  #### 5.1 Setting up account with Mulesoft
  
    1. Go to the site [Anypoint Platform] (https://anypoint.mulesoft.com)
    2. Click on signup to create new account
    3. Provide all the details and click on Accept and create account
    
   > This is trail account and is valid only for 7. You can create multiple user name with the same email address.
  
  #### Prerequisites for Installing Studio ####
  
    - Ensure that you have the Java SE JDK 8 installed and configured.
    - Download the Anypoint Studio installation file from the Download Site
   > After downloading and installing the JDK, ensure that your JDK installation is properly configured within the JAVA_HOME environment variable:
  - In Search, search for System (Control Panel) and select it.
  - Click Advanced System Settings.
  - Click Environment Variables.
  - In System Variables, look for the PATH environment variable:
  - If PATH is visible, select it and click Edit to navigate to Edit System Variable.
  - If PATH is not visible, click New to navigate to New System Variable.
  - Ensure that the /bin directory of your JDK 1.8.0 installation is the first item in your PATH environment variable.
  - Click OK.

### 6. Github and Maven installation

https://github.com/Mulesoft-Tutorials/Documents

