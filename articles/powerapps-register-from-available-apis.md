<properties
	pageTitle="Create and configure Microsoft managed and IT managed APIs in PowerApps | Microsoft Azure"
	description="Learn about the available APIs in PowerApps in the Azure portal"
	services="powerapps"
	documentationCenter="" 
	authors="MandiOhlinger"
	manager="dwrede"
	editor=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na" 
   ms.date="11/18/2015"
   ms.author="guayan"/>

# Register a Microsoft managed API or an IT managed API
There are **Microsoft managed** and **IT managed** APIs. When you enable PowerApps Enterprise, the Microsoft managed APIs are available to you automatically. The memory, connectivity, trust, and more are also automatically managed for you. Your next step is to enter any specific user settings, like a Twitter account and password. 

Using the IT managed APIs, you control and monitor everything, including memory, connectivity, trust, and more. The IT managed APIs also include the APIs that can connect to an on-premises system, like SQL Server and SharePoint Server. 

To use the **Microsoft managed** or **IT managed** APIs, you must "register" the APIs in the Azure portal. Once registered, you can use these APIs in your PowerApps. The following options are available: 

- Register a Microsoft managed API or an IT managed API
- Register an API hosted within [your App Service Environment][1]
- Register using a [Swagger 2.0 API definition][2]

This article focuses on the Microsoft managed APIs and the IT managed APIs. 

#### Prerequisites to get started

- Sign up for [PowerApps Enterprise]()
- Create an [app service environment]()


## View the available Microsoft managed APIs
The **Microsoft managed** APIs are provided with PowerApps Enterprise and are also hosted by Microsoft. In many scenarios, the Microsoft managed APIs are ideal for PowerApps. For example, if your PowerApp sends a tweet, uploads a file to OneDrive, or displays data from an Excel file, then these Microsoft managed APIs are a good choice. 

Some additional benefits include: 

- You get all the Microsoft managed APIs available for you to register your own instance. 
- The resources, including network, memory, or security configurations, are monitored automatically. For example, if you need more memory to display Excel data in your PowerApp, more memory is automatically added. 
- A trust between your PowerApp and the API, like Office and Twitter, is created automatically. 


#### Microsoft managed APIs

API | Description | Steps Link
--- | --- | ---
![][31] | **Dropbox**<br/><br/> You can get, update, delete items, and more. | [**Get Started**](4)
![][32] | **DynamicsCRM Online**<br/><br/> You can get, update, delete items, and more. | [**Get Started**](5)
![][33] | **Excel**<br/><br/> You can get, update, delete items, and more. | [**Get Started**](6)
![][34] | **Google Drive**<br/><br/> You can get, update, delete items, and more. | [**Get Started**](7)
![][35] | **Microsoft Translator**<br/><br/>Translates text, detects languages, and more. | [**Get Started**](8)
![][36] | **Office365 Outlook**<br/><br/>Manage your email. | [**Get Started**](9)
![][37] | **Office365 Users**<br/><br/>Access user profiles, their managers, their direct reports, and more. | [**Get Started**](10)
![][38] | **OneDrive**<br/><br/> You can get, update, delete items, and more. | [**Get Started**](11)
![][39] | **Salesforce**<br/><br/> You can get, update, delete items, and more. | [**Get Started**](12)
![][40] | **SharePoint Online**<br/><br/> You can get, update, delete items, and more. | [**Get Started**](13)
![][43] | **Twitter**<br/><br/> Send tweets, search tweets, see followers, and more. | [**Get Started**](16)


## View the available IT managed APIs
The **IT managed** APIs are controlled by you and managed by you. They do not run in the Microsoft managed environment. In some scenarios, using these APIs in your own IT managed environment may suit the needs of your PowerApps. For example, your PowerApp uses the Twitter API and you need to use your organization's Twitter key (instead of the Microsoft Twitter key). In this situation, it's best to configure the Twitter API as an IT managed API. In another example, your PowerApps use the SQL Server API to connect to an on-premises database. In an IT managed environment, you can set up a virtual network or use Express Route to connect to on-premises. The choice is yours.

Some additional benefits include:

- The resources, including network, memory, or security configurations, are monitored by you. For example, if you need more memory to display Excel data in your PowerApp, you control how much more memory to add in your environment. 
- You set up the trust and control the security between your PowerApps and the API. For example, you determine if the Office365 API can be Microsoft managed (an automatic trust) or use the Office365 API within your own environment (create your own trust). 
- **All** of the Microsoft managed APIs can also be IT managed. For example, if you want to create your own instance of Office365 and have full control over this instance, you can. You can then use your Office365 IT managed API and the Office365 Microsoft managed API in the same environment. It really depends on the needs of your PowerApp.
- When connecting to on-premises systems or using the Bing Search API, you control security, authentication, licensing, and more.


#### IT managed APIs
> [AZURE.NOTE] Remember, **all** of the Microsoft managed APIs can also be IT managed. The following APIs cannot be Microsoft managed.

API | Description | Steps Link
--- | --- | ---
![][30] | **Bing Search**<br/><br/>Embed search results, add search functionality, and more. | [**Get Started**][3]
![][42] | **SQL Server**<br/><br/>You can get, update, delete items, and more. | [**Get Started**](15)
![][41] | **SharePoint Server**<br/><br/>You can get, update, delete items, and more. | [**Get Started**](14)


#### Why register your own instances

Using the out-of-box Microsoft managed APIs is convenient. Having said that, registering your own instances as IT managed APIs has many benefits. At a high level, we recommend you create IT managed APIs when you want to: 

- Have full manageability on the APIs, including user access, security when connecting to other systems, API call limits, monitoring and advanced features like policies, and more.
- Access on-premises data since App Service Environment supports virtual networks.
- Set up the APIs for business users, which they may not be able to use by themselves.

The following table compares the capabilities of the Microsoft managed and IT managed APIs:

| Capability | Microsoft Managed | IT Managed |
| ---------- | ----------------- | ------------ |
| API call limits | Defined by Microsoft | Defined by yourself (via policies) |
| Bring your own key when connecting to SaaS | Not supported | Supported |
| API user access | Enabled for everyone | Fully manageable at AAD user and group level |
| API Monitoring | Not supported | Supported |
| API Policies | Not supported | Supported |
| Connection user access | View only | Fully manageable at AAD user and group level |
| Connection management | View only | Fully manageable |


## Register a Microsoft managed or IT managed API

1. In the [Azure portal](https://portal.azure.com/), select **PowerApps**. In PowerApps, select **Manage APIs**:  
![][17]
2. In Manage APIs, select **Add**:  
![][18]  
3. In **Add API**, enter the API properties:  

	- In **Name**, enter a name for your API. Notice that the name you enter is included in the runtime URL of the API. Make the name meaningful and unique within your organization.
	- In **Source**, select **From available APIs**:  
	![][19]
4. Select **API** and then choose the API you want to register:  
![][20]
5. Select your specific API and add any configurable properties.
6. Select **ADD** to complete these steps.

> [AZURE.TIP] When you register an API, you're registering the API to your app service environment. Once in the app service environment, it can be used by other apps within the same app service environment, especially PowerApps.


## Summary and next steps

In this topic, you've seen how to register your own instance of the available APIs  that PowerApps provides out-of-box. Here are some related topics and resources for learning more about PowerApps:  

- [Configure APIs][21]
- [Add a new API, add a connection, and give users access][22]

<!--References-->
[1]: powerapps-register-api-hosted-in-app-service.md
[2]: powerapps-register-existing-api-from-api-definition.md
[3]: powerapps-create-api-azuremarketplace-bingsearch.md
[4]: powerapps-create-api-azuremarketplace-dropbox.md
[5]: powerapps-create-api-azuremarketplace-crmonline.md
[6]: powerapps-create-api-azuremarketplace-excel.md
[7]: powerapps-create-api-azuremarketplace-googledrive.md
[8]: powerapps-create-api-azuremarketplace-microsofttranslator.md
[9]: powerapps-create-api-azuremarketplace-office365-outlook.md
[10]: powerapps-create-api-azuremarketplace-office365-users.md
[11]: powerapps-create-api-azuremarketplace-onedrive.md
[12]: powerapps-create-api-azuremarketplace-saleforce.md
[13]: powerapps-create-api-azuremarketplace-sharepointonline.md
[14]: powerapps-create-api-azuremarketplace-sharepointserver.md
[15]: powerapps-create-api-azuremarketplace-sql.md
[16]: powerapps-create-api-azuremarketplace-twitter.md
[17]: ./media/powerapps-register-from-available-apis/registered-apis-part.png
[18]: ./media/powerapps-register-from-available-apis/add-api-button.png
[19]: ./media/powerapps-register-from-available-apis/add-api-blade.png
[20]: ./media/powerapps-register-from-available-apis/add-api-select-from-marketplace-blade.png
[21]: powerapps-configure-apis.md
[22]: powerapps-create-new-connector.md
[30]: ./media/powerapps-register-from-available-apis/bingsearch.png
[31]: ./media/powerapps-register-from-available-apis/dropbox.png
[32]: ./media/powerapps-register-from-available-apis/dynamicscrmonline.png
[33]: ./media/powerapps-register-from-available-apis/excel.png
[34]: ./media/powerapps-register-from-available-apis/googledrive.png
[35]: ./media/powerapps-register-from-available-apis/microsofttranslator.png
[36]: ./media/powerapps-register-from-available-apis/office365outlook.png
[37]: ./media/powerapps-register-from-available-apis/office365users.png
[38]: ./media/powerapps-register-from-available-apis/onedrive.png
[39]: ./media/powerapps-register-from-available-apis/salesforce.png
[40]: ./media/powerapps-register-from-available-apis/sharepointonline.png
[41]: ./media/powerapps-register-from-available-apis/sharepointserver.png
[42]: ./media/powerapps-register-from-available-apis/sqlserver.png
[43]: ./media/powerapps-register-from-available-apis/twitter.png