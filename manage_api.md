---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-07"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, API, manage, gateway, summary, status, definition, online, offline, expose, hide, delete, edit, import, export

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}
{:tip: .tip}

# Managing an API
{: #manage_api}

Manage APIs by monitoring usage, exposing or hiding endpoints, and editing, importing, exporting, and deleting API definitions.
{: shortdesc}


## Overview
{: #overview-manage_api}

APIs are managed by a particular gateway, depending on how they are secured:

  - IAM resource group: {{site.data.keyword.apigw_short}} service
   
  - Cloud Foundry space: Legacy {{site.data.keyword.apigw_short}}

To manage an API, start the gateway that manages it and then click **Managed APIs** in the navigation list. Review the following sections for information on how you can manage your APIs. 

The default domain for managed APIs in your account is generated the first time you create a managed API. If you want to ensure that all subsequent managed APIs use the same default domain, keep at least one managed API at all times so that the default domain can be inherited.
{: tip}


## Reviewing API details
{: #details-manage_api}

Use the "API Summary" page to view API definition details such as its endpoint URL (the **Route**), security settings, and sharing status. 

In addition, you can review analytics information and logging records for the past hour.

You can also set the API's status to Online or Offline.

1. Start the gateway service that manages the API.

2. In the navigation list, click **Managed APIs**.

3. On the "Managed APIs" page, click the API that you want to work with.

### API region
{: #region-manage_api}

On the "API Summary" page, the API route includes the "region", which represents the geographic area where your APIs reside. For example, if the route displays as:

```
https://25328c20.us-south.apigw.cloud.ibm.com/findbranch
```

Then the region is "us-south". 


## Setting an API online or offline
{: #on_off-manage_api}

Setting an API online exposes its endpoint so that it can be invoked by applications. To hide the endpoint, set the API offline. The API must be online before it can be shared.

1. Start the gateway service that manages the API.

2. In the navigation list, click **Managed APIs**.

3. On the "Managed APIs" page, click ![API Options icon](images/icon_api_options.png "API Options icon") > **View API** next to an API.

4. On the "API Summary" page, click the API status indicator to toggle it between Online and Offline.

   ![API status indicators](images/icon_api_status_both.png "API status indicators")


## Editing an API definition
{: #edit-manage_api}

1. Start the service where the API is managed.

2. In the navigation list, click **Managed APIs**.

3. On the "Managed APIs" page, click the API that you want to edit.

4. In the navigation list, click **Define and secure**.

4. On the API's definition page, make your changes.

5. Click **Save** to update the API.


## Exporting an API
{: #export-manage_api}

Export an OpenAPI definition to a YAML or JSON file. You can export the definition of any managed API from the gateway.

1. Start the gateway service that manages the API.

2. In the navigation list, click **Managed APIs**.

3. On the "Managed APIs" page, click the API that you want to export.

4. In the navigation list, click **Define and secure**.

5. On the API's definition page, look in the "API Info" section and click  **API Definition**.

6. Select an export option: **Export YAML file** or **Export JSON file**.

The API definition is exported to the select file format (`.yaml` or `.json`) and is stored in your downloads folder. A message displays in the page's footer to confirm the export; click the message to open the file.

![Export confirmation message](images/msg_export_conf.png "Export confirmation message")

The exported definition retains all of the settings from the original API.


## Importing an API definition
{: #import-manage_api}

You can import an OpenAPI definition file using the same process you use for creating APIs, but making sure to select the **API Definition** > **Import YAML or JSON** option. 

The steps for importing an API are summarized here. For details on creating a new API definition, see [Creating an API](/docs/api-gateway?topic=api-gateway-create_api).

1. Decide whether the API proxy will be created in an IAM resource group or a Cloud Foundry space, and start the appropriate service:

  - IAM resource group: {{site.data.keyword.apigw_short}} service
  
    The API proxy will be bound to the resource group that you selected when you provisioned the {{site.data.keyword.apigw_short}} service.
  
  - Cloud Foundry space: Legacy {{site.data.keyword.apigw_short}}

2. Click the appropriate option to create an API.

3. On the API's definition page, look in the "API Info" section and click  **API Definition** > **Import YAML or JSON**.

4. Locate the file on your computer, select it, and click **Open**.
  
A message displays to confirm the import.
  
![Import confirmation message](images/msg_import_conf.png "Import confirmation message")


## Deleting an API
{: #delete-manage_api}

1. Start the service where the API is managed.

2. In the navigation list, click **Managed APIs**.

3. On the "Managed APIs" page, locate the API that you want to delete and click ![API Options icon](images/icon_api_options.png "API Options icon") > **Delete API**.
