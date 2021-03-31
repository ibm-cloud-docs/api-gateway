---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-07"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, API, gateway, support, responsibility, responsible

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Responsibility for resources and features
{: #responsibilities}

Review the following tables to understand who is responsible for managing the different resources and features in {{site.data.keyword.apigw_full}}.
{: shortdesc}

## Responsibility for {{site.data.keyword.apigw_short}} resources
{: #responsibilities-resources}

While most of the {{site.data.keyword.apigw_short}} resources are managed by IBM, you are responsible for some resources that are typically managed by you. Table 1 lists the {{site.data.keyword.apigw_short}} resources and notes which party is responsible for managing different aspects of each resource.

| Resource                     | Incident and Operations Management | Identity and Access Management | Security and Regulation Compliance | Disaster Recovery |
| ---------------------------- | --------------------- | ------------------| --------------------- | -------- |
| Data                         | You                   | You               | You                   | You      |
| Application                  | You                   | You               | You                   | You      |
| Observability                | Shared                | Shared            | IBM                   | IBM      |
| App networking               | Shared                | IBM               | IBM                   | IBM      |
| Virtual storage              | IBM                   | IBM               | IBM                   | IBM      |
| Virtual network              | IBM                   | IBM               | IBM                   | IBM      |
| Hypervisor                   | IBM                   | IBM               | IBM                   | IBM      |
| Physical servers and memory  | IBM                   | IBM               | IBM                   | IBM      |
| Physical storage             | IBM                   | IBM               | IBM                   | IBM      |
| Physical network and devices | IBM                   | IBM               | IBM                   | IBM      |
| Facilities and Data Centers  | IBM                   | IBM               | IBM                   | IBM      |
{: caption="Table 1. Resource responsibility" caption-side="top"}


## Responsibility for {{site.data.keyword.apigw_short}} features
{: #responsibilities-features}

Most of the responsibility for {{site.data.keyword.apigw_short}} features is shared between you and IBM. Table 2 specifies each party's responsibilities for features.

| Feature             | Your Responsibility           | IBM's Responsibility           |
| --------------------| ----------------------------- | -------------------------------|
| API Creation        | Provide REST API specifications using OpenAPI files and the {{site.data.keyword.apigw_short}} APIs | Provision and deploy the REST API using your specifications |
| App Networking      | Provide the endpoints for routing API traffic | Expose the API to the Internet using your specified endpoint to route traffic |
| API Keys            | Enable API Keys as the authentication method for a REST API and distribute keys to API subscribers | Generate and authenticate API keys |
| OAuth               | Enable OAath as the authentication method for a REST API and select an {{site.data.keyword.apigw_short}}-compatible OAuth provider | Authenticate using OAuth token or IAM, and integrate with OAuth-enabled services |
| Actions             | Configure | Integrate, generate, and activate |
| Monitoring          | (None) | Integrate with {{site.data.keyword.cloud_notm}} Log Analysis to provide API metrics on the {{site.data.keyword.apigw_short}} dashboard |
| Rate Limiting       | Implement rate limits using the {{site.data.keyword.apigw_short}} console | Enforce rate limits |
| REST API Management | Provide {{site.data.keyword.apigw_short}} with the desired REST API specifications | Host, provision, integrate, and implement your APIs using your {{site.data.keyword.apigw_short}}-compatible specifications |
{: caption="Table 2. Feature responsibility" caption-side="top"}


