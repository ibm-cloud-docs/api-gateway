---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-07"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, API, manage, share, gateway, develop, create, test, explore, try, invoke, call, key, secret, definition

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Viewing and testing an API
{: #test_api}

View an API and its documentation the API Explorer, and test the API with {{site.data.keyword.apigw_short}} Test and Monitor.
{: shortdesc}


## Overview
{: #overview-test_api}

Use the API Explorer to review the API's definition and try a quick API call.

Then, use {{site.data.keyword.apigw_short}} Test and Monitor to make an external call to the API so you can see how it works for your customers.


## Viewing and testing with API Explorer
{: #explore-test_api}

1. Start the gateway service.

   The gateway opens to the "Managed APIs" page.

2. On the "Managed APIs" page, click the name of the API that you want to explore.

3. In the navigation list, click **Review and test**. 

   The API Explorer opens in a new browser tab.

### View the OpenAPI definition
{: #explore_docs-test_api}

The API Explorer shows the details of the OpenAPI definition; for example, the response schema and the available operations. You can download the OpenAPI definition to reuse it.

### Try the API
{: #explore_try-test_api}

Select a language for the API call and invoke the API. The examples detail the request and response for the selected language so you can see how the API works.

1. Select the language to use for the call (`curl` is selected by default).

2. When you're reading to invoke the API, click **Try it**.

   a. If your API definition requires the use of the API secret, click **Set API Secret** to provide one with the call. 

      You can set the API secret once, so be sure to copy the value and save it for later use. 

   b. Select the Header format.

   c. Click **Call operation**. 

The request and the response display in the API Explorer.


## Test the API externally
{: #external-test_api}

Use IBM API Connect Test and Monitor, a free tool for executing API calls.

![Arrow icon](images/icon_prereqs_arrow.png "Arrow icon") Before you begin: Use the **Sharing and Keys** page to generate an API key (and optionally, an API secret) that can be used to call the API from outside of {{site.data.keyword.cloud_notm}}.

1. Collect the following information from your API.

  You can copy the following values for your API from API Explorer and paste them into Test and Monitor.

  - API endpoint: The complete API endpoint URL displays in the **Route** field on the "API Summary" page.
  
  - API key: The API key displays on the "Shared APIs" page.

  - API secret: The API secret can be copied when you create it in the Create API key dialog box while [Sharing an API](/docs/api-gateway?topic=api-gateway-share_api). You cannot access the secret later. If you lose the secret, then you must create a new secret.

2. Use your IBM ID to create a free account in IBM API Connect Test and Monitor.

   Navigate to [IBM API Connect Test and Monitor](https://www.ibm.com/cloud/api-connect/api-test){: external} and click **Start for free*.

3. Set up your call to the API.

  In API Connect Test and Monitor, complete the following fields:
  
  - **Operation**: The API's method. 

  - **Request url**: Copy the API endpoint from API Explorer.

  - **Params**: Click to add one or more request parameters. Provide the parameter name as the **key** and type the corresponding **value**.

  - "Headers" section: 

    a. Supply the parameter name and value for the API key:

       * **Key**: Type the following label: `X-IBM-Client-Id`

       * **Value**: Paste the API key's value.

    b. If you also created an API secret, click **+** and supply the parameter name and value:

       * **Key**: Type the following label: `X-IBM-Client-Secret`

       * **Value**: Paste the API secret's value.

4. Click **Send** to execute the call.

  A successful call returns the 200 status code.
