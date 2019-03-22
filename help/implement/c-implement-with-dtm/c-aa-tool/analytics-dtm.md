---
description: Deploy Adobe Analytics using Dynamic Tag Management by creating the Adobe Analytics tool and configuring the page code either automatically or manually. The automatic method is recommended for most users.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
seo-description: Deploy Adobe Analytics using Dynamic Tag Management by creating the Adobe Analytics tool and configuring the page code either automatically or manually. The automatic method is recommended for most users.
seo-title: Add Adobe Analytics tool
solution: Analytics
title: Add Adobe Analytics tool
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
---

# Add Adobe Analytics tool

Deploy Adobe Analytics using Dynamic Tag Management by creating the Adobe Analytics tool and configuring the page code either automatically or manually. The automatic method is recommended for most users.

>[!NOTE]
>
>For improved visitor tracking, we strongly recommend that you enable [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Add an Adobe Analytics Tool {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Click  **[!UICONTROL  *`Web Property Name`*]** > **[!UICONTROL Overview]** > **[!UICONTROL Add a Tool]** > **[!UICONTROL Adobe Analytics]** .

   ![](assets/dtm-add-analytics-tool.png)

1. Fill in the fields: 

   | Element | Description |
   |--- |--- |
   |Tool Type|The type of tool, such as  Adobe Analytics.|
   |Tool Name|A descriptive name for this tool. This name displays on the  Overview tab under  Installed Tools.|
   |Configuration Method|Automatic (Recommended): Use dynamic tag management to manage the configuration. This method enables automatic synchronization of  Adobe Analytics report suites via a  Experience Cloud login or Web Services ID, and manages the [!DNL AppMeasurement] code. <br></br>After the accounts are connected, Dynamic Tag Management pulls the  Adobe Analytics report suite IDs and names into the tool configuration interface, allowing for increased speed in tool deployment with less possibility for user errors.   Note: You must choose the  Automatic option if you are an  Adobe Analytics Premium customer. See  Enabling Adobe Analytics Premium below. <br></br>Fill in the fields specific to automatic configuration:  <br></br>**Experience Cloud:** (Default) Uses  Experience Cloud single sign-on. Specify your Experience Cloud ID and password. <br></br>**Web Services:** Specify your Web Services username and shared secret.  Shared secret credentials are located in  Admin Tools >  Company Settings >  Web Services.  Developers, see  Get Web Service Access to the Enterprise API for help with obtaining Web Services credentials.<br></br>**Manual:** Manually manage the [!DNL AppMeasurement] code. You can download the  Analytics AppMeasurement code from  Admin Tools >  Code Manager.  Click  JavaScript (new) for information about downloading the code locally to copy and paste in the  Edit Code field in  Library Management.  Fill in the fields specific to a manual configuration: <br></br>**Production Account ID:** (Required) Your production account for data collection. For Analytics, this is your report suite ID. Dynamic Tag Management automatically installs the correct account in the production and staging environment.<br></br>**Staging Account ID:** (Required) Used in your development or test environment. For Analytics, this is your report suite ID. A staging account keeps your testing data separate from production.<br></br>**Tracking Server:** Specify the information for your tracking server.  The  Tracking Server and  SSL Tracking Server variables are used for first-party cookie implementation to specify the domain at which the image request and cookie is written. For more information, see the  Correctly Populate the trackingServer and trackingServerSecure Variable article.<br></br>**SSL Tracking Server:** Specify the information for your SSL tracking server.|

1. Click **[!UICONTROL Create Tool]** to create the tool and display it for editing.

   Tools are displayed on the [!UICONTROL Overview] tab, under [!UICONTROL Installed Tools]. 

1. (Conditional) Configure the tool further as necessary by following the directions in the links below ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies], and [!UICONTROL Customize Page Code]).

See [Frequently Asked Questions About the Adobe Analytics Tool](../../../implement/faq.md#concept_00DF9AF14D30469BB986BF56A448806B) for additional information about this tool.

## Edit an Existing Adobe Analytics Tool {#section_148B16AF429B4949B06238D90635B726}

You can edit an existing Adobe Analytics tool to change its configuration settings.

1. Click the  ![](assets/settings_gear.png) icon next to an installed tool from the [!UICONTROL Overview] tab. 
1. Edit the fields as desired.

   The following table includes only those elements that differ from the elements available when you are creating an Analytics tool, as described above. However, you can change any element on the page, as described in both tables. 

   | Element | Description |
   |--- |--- |
   |Enable Automatic Configuration|Note: Enabling this setting changes a manually configured implementation to the automatic configuration method described in  Configuration Method.  This option lets Dynamic Tag Management automatically retrieve your  Adobe Analytics account's configuration.  The latest available [!DNL AppMeasurement] code is used and upgrade notifications are displayed for selection as new versions become available. You can also roll back to previous [!DNL AppMeasurement] versions as necessary, such as for compatibility reasons. Up to five previous versions are displayed.|
   |Update Credentials|Refresh the API, for example, to update report suites associated with a user.|

1. (Conditional) Configure the tool further as necessary by following the directions in the links below 
   ([!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies], and [!UICONTROL Customize Page Code]). 
1. Click **[!UICONTROL Save Changes]**.
