# Anypoint Platform Overview

Anypoint Platform is a unified, hybrid, highly productive integration platform that allows developers to create a seamless application network of applications, data, and devices.

Anypoint Platform provides us the runtime, tool, framework and library (central repository) for our APIs and applications.

- Runtime to run and deploy our applications in the cloud or on-premise.
- Tools and framework for creating an API and building simpler Mule Applications (for complex applications we go for Anypoint Studio).
- Library to store our assets (APIs and applications) where we can view and test them, and it can be reused by other developers in the organization.

An Anypoint Platform has the following components:

## Design Center

A Design center is the development environment for a Mule application as well as for our API specification. In Design Center, we can create API's with the help of RAML (RESTful API Modeling Language), a YAML based language, and simple Mule Applications in the flow designer component.

![]()

## Anypoint Exchange

Anypoint Exchange provides us the benefit of being able to share, discover, and incorporate assets and resources into our Integration or Application.

It helps us:

- Create API developer portals
- View and test our APIs
- Simulate data to API, also called as Mocking Service
- Create assets

Anypoint Exchange is a home to a complete listing of resources such as Connectors, Templates, Examples, APIs (REST, SOAP, HTTP), API spec fragments, and much more.

We can connect to Anypoint Exchange through Anypoint Studio and download and install connector examples or APIs and use them per our needs.

![]()

## Access Management

Access Management configures access and permissions within your organization and, depending on the access level, manages the users and their roles.

As the administrator of your organization or one of its business groups, you can enable, disable, or delete users. You can also invite new users and also manage existing users of your organization.

![]()

## API Manager

API Manager is the component of Anypoint Platform that helps in managing the APIs for an organization. API Manager helps us to apply different policies to our APIs that limit its use and secure it from external users.

The automated policies feature inside the API Manager allows the administrator to apply the same set of policies to all the APIs deployed to an environment in an organization. It helps the user to deploy the API with confidence as he no longer has to apply policies to the API and he knows that the environment in which he is deploying will have necessary policies applied to it.

![]()

## Runtime Manager

Runtime Manager allows us to run, deploy, and manage our deployed applications from a central location, whether they are running in CloudHub or on-premise or on the Runtime fabric.

Runtime Manager is specially designed for Mule Applications for deploying them to various available Mule runtime instances in CloudHub virtual worker or an on-premise server or Runtime fabric.

![]()
