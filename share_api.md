---

copyright:
  years: 2018, 2020
lastupdated: "2020-08-07"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, API, manage, share, gateway, key, secret, internal, external, customer, developer

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}
{:tip: .tip}
{:important: .important}


# Sharing an API
{: #share_api}

Share with other developers for use in their own applications. Developers who can access a shared API can read the API's documentation, create API keys for use with the API, and test the API in the API Explorer.
{: shortdesc}


## Overview
{: #overview-share_api}

API proxies and {{site.data.keyword.openwhisk_short}} APIs can be shared 
either within {{site.data.keyword.cloud_notm}} or outside of {{site.data.keyword.cloud_notm}}. When you share an API within {{site.data.keyword.cloud_notm}}, anyone with access to your {{site.data.keyword.cloud_notm}} organization can use the API. When you share the API outside of {{site.data.keyword.cloud_notm}}, you must send the endpoint and API key to the person you are sharing with.

APIs created in Cloud Foundry and {{site.data.keyword.appconserviceshort}} can be shared 
either within the current Cloud Foundry organization, or outside of the Cloud Foundry organization. When you share an API within the Cloud Foundry organization, anyone with access to the organization can use the API. When you share the API outside of the Cloud Foundry organization, you must send the endpoint and API key to the person you are sharing with.

Each API can support up to five API keys for internal users, and another five API keys for external users.  


## Share an API internally
{: #internal-share_api}

Share an API with users who can access your {{site.data.keyword.cloud_notm}} organization or your Cloud Foundry organization:

- API proxies and {{site.data.keyword.openwhisk_short}} APIs: this option is labeled "Sharing within {{site.data.keyword.cloud_notm}}" 

- Cloud Foundry APIs and {{site.data.keyword.appid_full_notm}} APIs: this option is labeled "Sharing within Cloud Foundry organization"

You can create up to five API keys for each API.

1. Start the gateway that manages the API.

   The gateway opens to the "Managed APIs" page.

2. On the "Managed APIs" page, click the name of the API that you want to share.

3. In the navigation list, click **Manage sharing and keys**. 

4. On the "Sharing and Keys" page, verify that the API is online so that it can be shared.

   ![API status indicator](images/icon_online.png "API status indicator")

   If the API is not online, you can click the **Offline** status indicator now to set the API online, which enables it for use.

5. In the "Sharing Within" section, click the appropriate option:

   - API proxy or Cloud Functions API: **Include API in account-level Shared APIs view**.

   - Cloud Foundry API or {{site.data.keyword.appid_full_notm}} API: **Include API in organizational-level Shared APIs view**

   When users consume the API, information about the user and the calling application display in the "Sharing within" section of the page.

6. Optional. Create an API key and secret

   You can optionally click **Create API key** to generate a key and secret for your own use, but it is not required for sharing the API internally. Other users create their own API keys.
   {: note}

   a. In the "Create API key" dialog box, provide the following settings:

      - **Descriptive name** A display name for the API key; for example, the name of the company that you want to share this key with. You can track individual keys by name; for example, in usage information in the API summary. 

        The name can include the following characters: A-Z a-z 0-9 - _ (no spaces allowed)

      - API key: Select **Use generated key** if you want a value created for you. Select **Specify key** to create your own value.

      - API secret: If you specified that an API secret is required (when you created the API definition), a value is generated now and displayed in the **API secret** field. 

        * Click **Show** to display the value.

        * Optionally delete the value and type a new one, and then type the same value in the **Verify API secret" field.

        Copy the secret and save it so that you can use it later for testing. After you close this dialog box, you cannot access the secret again. If you lose the secret, you must create a new one.
        {: important}

	b. Click **Create** to generate and save the API key (and secret).


## Share an API externally
{: #external-share_api}

Share an API with users who cannot access your {{site.data.keyword.cloud_notm}} organization or your Cloud Foundry organization:

- API proxies and {{site.data.keyword.openwhisk_short}} APIs: this option is labeled "Sharing Outside of {{site.data.keyword.cloud_notm}}". 

- Cloud Foundry APIs and {{site.data.keyword.appconserviceshort}} APIs: this option is labeled "Sharing Outside of Cloud Foundry organization".

You can create up to five API keys for each API.

1. Start the gateway that manages the API.

   The gateway opens to the "Managed APIs" page.

2. On the "Managed APIs" page, click the name of the API that you want to share.

3. In the navigation list, click **Manage sharing and keys**. 

4. On the "Sharing and Keys" page, verify that the API is online so that it can be shared.

   ![API status is Online](images/icon_online.png "API status is Online")

   If the API is not online, you can click the **Offline** status indicator now to set the API online, which enables it for use.

5. In the "Sharing Outside" section, click **Create API key** to generate a new key for the API.

   Creating an API key is required for sharing the API externally.
   {: note}

   a. In the "Create API key" dialog box, provide the following settings:

      - **Descriptive name** A display name for the API key; for example, the name of the company that you want to share this key with. You can track individual keys by name; for example, in usage information in the API summary. 

        The name can include the following characters: A-Z a-z 0-9 - _ (no spaces allowed)

      - API key: Select **Use generated key** if you want a value created for you. Select **Specify key** to create your own value.

    b. Click **Create** to generate and save the API key.

   The new API key and a corresponding "API Documentation Link" display. 

6. Copy the API Documentation link and send it to the external user. 

   The link opens the API Explorer for the API so that the external user can review the API definition and test the API.
