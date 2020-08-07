---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-07"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, API, manage, gateway, migrate, upgrade, space, resource group, import, export

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Migrating a managed API to the {{site.data.keyword.apigw_short}} service
{: #migrate_api}

Optionally migrate your existing API proxies and Cloud Functions APIs to the {{site.data.keyword.apigw_short}} service so they can be secured with resource groups.
{: shortdesc}


## Overview
{: #overview-migrate_api}

API proxies and Cloud Functions APIs can be secured with either Cloud Foundry spaces or IAM resource groups. If you previously created API proxies and Cloud Functions APIs in Cloud Foundry spaces, you can optionally migrate them to resource groups.

APIs created in Cloud Foundry and APIs created in {{site.data.keyword.appconserviceshort}} cannot be migrated to {{site.data.keyword.apigw_short}} because they cannot be secured with resource groups.
{: note}

### Why migrate your APIs?
{: #why-migrate_api}

With the Legacy {{site.data.keyword.apigw_short}} (also known as the API Management service), your APIs were created in Cloud Foundry spaces. A space provides users with access to a shared location for app development, deployment, and maintenance. Cloud Foundry roles grant access to spaces but offer no control over user actions. 

With the new {{site.data.keyword.apigw_full}} service, APIs are created in resource groups and access is controlled by IAM services. A resource group organizes your account resources in customizable groupings so that you can quickly assign users access to more than one resource at a time. IAM services control both access to resources, and the actions that can be performed by users, which provides a greater level of security than Cloud Foundry spaces.

For more information about the {{site.data.keyword.apigw_full}} transition from Cloud Foundry spaces to IAM resource groups, see [What is IBM Cloud Identity and Access Management](/docs/iam?topic=iam-iamoverview){: external}.


## How to migrate APIs
{: #howto-migrate_api}

Migration is a simple process: export an existing API from the Legacy {{site.data.keyword.apigw_short}}, and then import it into the {{site.data.keyword.apigw_short}} service. When you import or create an API in the {{site.data.keyword.apigw_short}} service, the API is secured with resource groups.

### Step 1. Export an API from the Legacy {{site.data.keyword.apigw_short}}
{: #export-migrate_api}

Export an OpenAPI definition from the Legacy {{site.data.keyword.apigw_short}} to a YAML file or a JSON file.

1. Start the Legacy {{site.data.keyword.apigw_short}}.

2. In the navigation list, click **Managed APIs**.

3. On the "Managed APIs" page, click the API that you want to export.

4. In the navigation list, click **Define and secure**.

5. On the API's definition page, look in the "API Info" section and click  **API Definition**.

6. Select an export option: **Export YAML file** or **Export JSON file**.

The API definition is exported to the select file format (`.yaml` or `.json`) and is stored in your downloads folder. A message displays to confirm the export; click the message to open the file.

![Export confirmation message](images/msg_export_conf.png "Export confirmation message")

The exported definition keeps all of the settings from the original API.


### Step 2. Import an API into the {{site.data.keyword.apigw_short}} service
{: #import-migrate_api}

Import a YAML file or JSON file that contains an OpenAPI definition to the {{site.data.keyword.apigw_short}} service. The imported API is secured with IAM resource groups.

You can import only API proxies and {{site.data.keyword.openwhisk_short}} APIs into the {{site.data.keyword.apigw_short}} service. APIs created in {{site.data.keyword.appconserviceshort}} and Cloud Foundry are not secured in resource groups and cannot be managed by the {{site.data.keyword.apigw_short}} service.

#### Import an API proxy 
{: #import_proxy-migrate_api}

1. Start the {{site.data.keyword.apigw_short}} service.

2. Click **Create an API Proxy**.

3. On the "Create API Proxy" or  page, look in the "API Info" section and click  **API Definition** > **Import YAML or JSON**.

4. Locate the YAML file or the JSON file on your computer, select it, and click **Open**.
  
A message displays to confirm the import.
  
![Import confirmation message for an API proxy](images/imsg_import_conf.png "Import confirmation message")

The imported definition keeps all of the settings from the original API.

#### Import a {{site.data.keyword.openwhisk_short}} API
{: #import_cfunc-migrate_api}

1. Start the {{site.data.keyword.apigw_short}} service.

2. Click **Create a {{site.data.keyword.openwhisk_short}} API**.

   The {{site.data.keyword.openwhisk_short}} "APIs" page displays.
  
3. On the "APIs" page, click **Create API**. 

4. On the "Create a {{site.data.keyword.openwhisk_short}} API" page, look in the "API Info" section and click **API Definition** > **Import YAML or JSON**.
  
5. Locate the YAML file or the JSON file on your computer, select it, and click **Open**.
  
A message displays to confirm the import.
  
![Import confirmation message for a {{site.data.keyword.openwhisk_short}} API](images/imsg_import_conf.png "Import confirmation message")

The imported definition keeps all of the settings from the original API.
