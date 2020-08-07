---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-07"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, API, manage, share, gateway, develop, create, proxy, Cloud Foundry, App Connect, Cloud Functions, resource group, space, organization, IAM, whatis

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# What is {{site.data.keyword.apigw_short}}?
{: #whatis_apigw}

{{site.data.keyword.apigw_full}} is a free service that you can use to create, secure, share, and manage APIs that access {{site.data.keyword.cloud_notm}} resources.
{: shortdesc}

{{site.data.keyword.apigw_short}} works by inserting a fast and lightweight gateway in front of existing {{site.data.keyword.cloud_notm}} endpoints. The gateway intercepts an incoming API call and executes security policies, and then routes the call to the back-end application. After the request is processed, the back-end application sends the response to the gateway, which then routes it back to the caller.


## {{site.data.keyword.apigw_short}} features
{: #whatis_apigw-features}

{{site.data.keyword.apigw_short}} offers the following features to control usage, increase adoption, and track statistics about your APIs.

### Rate limiting 
{: #whatis_apigw-rate-limit}

You can enforce a rate limit to manage the number of calls that applications can make to your APIs. You can specify a rate limit so that only a permitted number of calls are made per second, minute, or hour. You can set this rate to apply to the overall API, or set a single limit for the API that applies to a particular API key.

### OAuth
{: #whatis_apigw-oauth}

To prevent unauthorized access to your data, you can ensure that only users with the correct authentication can access your APIs. The OAuth token-based authorization protocol allows third-party websites or applications to access user data without requiring the user to share personal information.

### CORS (Cross-Origin Resource Sharing)
{: #whatis_apigw-cors}

CORS is a mechanism that uses HTTP headers to allow an app to retrieve data from an API across domain boundaries. Only those cross-domain API calls that include the appropriate CORS header can be fulfilled. If your API does not enable CORS, then it can return data only to apps within the same domain.

### API analytics
{: #whatis_apigw-analytics}

{{site.data.keyword.apigw_short}} uses the {{site.data.keyword.cloud_notm}} LogDNA service to store and display information that is generated during API invocations. You can use the analytics feature to track call usage. You can also monitor usage to understand how your APIs are being used so that you can make informed decisions about how to update your APIs to increase adoption. 

You can view the following statistics about your APIs:
* The number of responses and average response time in the last hour, or your specified time interval.
* The number of API calls per minute.
* The last 100 responses.

## {{site.data.keyword.apigw_short}} service and Legacy {{site.data.keyword.apigw_short}}
{: #whatis_apigw-compare}

- {{site.data.keyword.apigw_short}} service

  {{site.data.keyword.apigw_short}} is an {{site.data.keyword.cloud_notm}} service. You provision an instance of the service for your own use, and select a service plan that controls pricing and access. The {{site.data.keyword.apigw_short}} service creates and manages APIs in resource groups that are secured by [Identity and Access Management services](/docs/iam?topic=iam-iamoverview){: external}. A resource group enables you to organize your account resources in customizable groupings so that you can quickly assign users access to more than one resource at a time. IAM services control both access to resources, and the set of actions that can be performed by users, providing a greater level of security than Cloud Foundry spaces.

  When you provision an {{site.data.keyword.apigw_short}} service, you select a resource group for it. All API proxies that you create with the service are bound to that resource group. APIs for Cloud Functions actions can be distributed among multiple resource groups and still be managed by a single {{site.data.keyword.apigw_short}} service.

- Legacy {{site.data.keyword.apigw_short}}

  The Legacy {{site.data.keyword.apigw_short}} uses built-in {{site.data.keyword.cloud_notm}} tools to create and manage APIs hosted in Cloud Foundry spaces, where access is controlled by using roles. A space provides users with access to a shared location for app development, deployment, and maintenance. Cloud Foundry roles grant access to spaces, but offer no control over user actions. 
  
  The Legacy {{site.data.keyword.apigw_short}} is available to all users. You do not provision a service instance, so you cannot manage the service itself. 

If you previously created and managed APIs with the Legacy {{site.data.keyword.apigw_short}} (through the {{site.data.keyword.cloud_notm}} API Management dashboard), all of those features are still supported. In addition, you can choose to create new API proxies and {{site.data.keyword.openwhisk_short}} APIs that are based on IAM resource groups instead of Cloud Foundry spaces. If you prefer to manage all of your APIs within a single service, then you can [migrate your legacy APIs](/docs/api-gateway?topic=api-gateway-migrate_api) to resource groups and manage them with the new {{site.data.keyword.apigw_short}}.

Table 1 summarizes the feature differences between {{site.data.keyword.apigw_short}} service and the Legacy API gateway.

| Feature | {{site.data.keyword.apigw_short}} service | Legacy {{site.data.keyword.apigw_short}} |
| ------- | ------------------- | -------------------------- |
| Create API proxies | Yes | Yes |
| Create APIs for {{site.data.keyword.openwhisk_short}} | Yes | Yes |
| Create APIs for {{site.data.keyword.appconserviceshort}} flows | No | Yes |
| Manage APIs for Cloud Foundry apps | No  | Yes |
| API endpoint | Endpoints are allowed in multiple regions and can be customized. | A single endpoint is allowed, and can be customized. |
| APIs created in | IAM resource groups | Cloud Foundry spaces |
| APIs can be shared | Up to five API keys for distribution to consumers within {{site.data.keyword.cloud_notm}}, and five more API keys for external consumers.  | Up to five API keys for distribution to consumers within {{site.data.keyword.cloud_notm}}, and five more API keys for external consumers. |
| Number of calls | 1 million calls per month. After your block of free calls is exhausted, API traffic might be throttled on an as-needed basis. Traffic restrictions will be based on overall system usage and performance. Until paid plans become available for API Gateway, throttling will implemented only as needed to prevent performance degradation| Unlimited. |
| Provisioning | Provision your single service instance before use or when you create your first API. |Always available. You do not need to provision your own service. |
| Expiration | Service instance expires after 30 days of inactivity. | No expiration |
{: caption="Table 1. Differences between {{site.data.keyword.apigw_short}} service and Legacy {{site.data.keyword.apigw_short}}" caption-side="top"}