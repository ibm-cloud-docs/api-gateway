---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-07"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, API, manage, share, gateway, key, secret, authenticate, authorize, OAuth, CORS, Cross Origin Resource Sharing, domain, response

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Securing an API
{: #secure_api}

You can secure an API with an API key and secret. When you share the API with other developers, they call the API with the keys to validate their access.
{: shortdesc}


## Overview
{: #overview-secure_api}

Edit an API definition and enable security settings.

To edit the API definition:

1. Start the service where the API is managed.

2. In the navigation list, click **Managed APIs**.

3. On the "Managed APIs" page, click the API that you want to edit.

4. In the navigation list, click **Define and secure**.

4. On the API's definition page, make your changes.

5. Click **Save** to update the API.

You can add or change the following settings to secure your API.


## Application authentication
{: #keys-secure_api}

Use the "Application authentication" section of the API definition to require authentication with the API key only, or with both the API key and the API secret. 

When you use API keys, you can monitor the API and manage its use. By sending a unique key to an individual or company, you can track some statistics about how that API is used by different customers. For example, you can track the number of calls to your API by each person or company. You can also disable a key, or limit the number of calls from a particular key.

Complete the following settings to enable application authentication with keys:

* **Require application authentication via API key**: Select this option if you want to require apps that call your API to authenticate with an API key, or with a combination of an API key and an API secret.
  
* **Method**: Select **API key only** or **API key and secret**.
  
* **Location of API key and secret**: The calling app must include the API key (and secret, if you selected it) in the request header. 
  
* **Parameter name of API key**: {{site.data.keyword.cloud_notm}} requires the following parameter name for the API key: `X-IBM-Client-Id`.
  
* **Parameter name of API secret**: {{site.data.keyword.cloud_notm}} requires the following parameter name for the API secret: `X-IBM-Client-Secret`.

After you enable the use of API keys and secrets, you can create them for other users when you share the API. For more information about sharing APIs, see [Sharing an API](/docs/api-gateway?topic=api-gateway-share_api).


## OAuth user authentication
{: #oauth-secure_api}

Use the "OAuth user authentication" section of the API definition to require the use of an OAuth provider, which generates a token that the user can submit for authentication when they use an app that calls the API. Complete the following settings to enable the use of OAuth user authentication:

* **Require users to authenticate via OAuth social login**: Select this option to require user to sign in to an external application before they invoke the API. 

* Select the external application in the **Provider** field. 

  The app that invokes the API must include a token from the the provider in the request header. If the token cannot be validated with the social app, the response returns the HTTP status code 401 for an unauthorized request.

  * **App ID service**: If you selected {{site.data.keyword.appid_full_notm}} as the OAuth provider, select your own {{site.data.keyword.appid_full_notm}} service instance as the token provider. When a user is successfully authenticated, the application receives a token from {{site.data.keyword.appid_full_notm}}. 
  
    If you do not have an {{site.data.keyword.appid_full_notm}} service instance, click ![Create App ID service](images/icon_create_appid.png "Create App ID service") to create your service instance now in a new browser tab. Then, return to the "Create API Proxy" page and refresh your browser. The new service's name is displayed in the **App ID service** field. 
  
    If you already have an {{site.data.keyword.appid_full_notm}} service instance but are not sure of its settings, click ![Edit App ID service](images/icon_edit_appid.png "Edit App ID service") to open the service information in a new browser tab.
    {: tip}


## Cross-Origin Resource Sharing
{: #cors-secure_api}

Enable CORS (Cross-Origin Resource Sharing) support so that the API can be accessed from another domain. When the API is called from a web page that is hosted in another domain, the response must include a CORS header.
  
CORS support is enabled by default but you can select **Disable CORS** in the **CORS status** field if you prefer not to use CORS headers.
