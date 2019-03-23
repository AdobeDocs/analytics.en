---
description: Learn about the first-time customer experience for implementing Adobe Analytics implementation.
keywords: Getting Started
seo-description: Learn about the first-time customer experience for implementing Adobe Analytics implementation.
seo-title: Simplified implementation modal
solution: Analytics
subtopic: Analysis Workspace
title: Simplified implementation modal
topic: Reports and analytics
uuid: 6fad2c1f-476c-4985-90df-7c222e751ddc
---

# Simplified implementation modal

Learn about the first-time customer experience for implementing Adobe Analytics implementation.

<!-- 

<p>https://activation.adobedtm.com/index.php?redirected=1 </p>

 -->

New users can quickly create your first [!DNL Analytics] report suite (data repository) using this *`Getting Started with Adobe Analytics`* setup modal. Then, you can deploy [!DNL Analytics] code using [!DNL Dynamic Tag Management].

[!DNL Dynamic Tag Management] allows you to manage your Adobe Analytics implementation without needing to make changes to your site every time. If you're implementing a Mobile app, you can get the SDK that you need to begin collecting valuable data from your apps.

In this procedure enables you to:

* Quickly create your first [report suite](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html). 
* Deploy [!DNL Analytics] and the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/). 

* Run reports on basic page-level data.

>[!NOTE]
>
>Before you begin, verify that Analytics is [enabled in the Adobe Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html) (the solution provisioning process). If you received an email inviting you to log in to Analytics in the Enterprise Dashboard, you've completed this prerequisite.

**To run the simplified implementation modal** 

1. Log in to the [!DNL Adobe Experience Cloud] ( [!DNL *`<your company>`*.marketing.adobe.com]).

   When you access [!DNL Analytics], the system determines if you have a report suite. If not, the [!UICONTROL Getting Started with Adobe Analytics] page displays.

   ![](assets/analytics-implementation-rs-wizard.png)

   Alternatively, you can run this setup in [!DNL Analytics] by clicking **[!UICONTROL Help]** > **[!UICONTROL Welcome to Adobe Analytics]**. 

1. Specify the following basic information about your business:

   | Element | Description |
   |--- |--- |
   |Property Type|Is your implementation for web, mobile, or both?|
   |Industries|Specify how your company makes money (products, customer services, leads, brand awareness, and ads).|
   |Data Layer|(Recommended) A JavaScript array which is used to store information. If you perform the automatic setup using Dynamic Tag    Management, you will be using a data layer.  For a blog on data layers, see  Data Layer: From Buzzword to Best Practice.|
   |Data Repository (Report Suite)|A  report suite is a discrete data set that typically corresponds to a single property (site or app)    or brand. Each report suite has its own set of reports and metrics.|
   |Time Zone|Your local time zone. (Automatically detected.)|
   |Estimated Page Views|Roughly the number of page views your site receives per day.|
   |Base Currency|The currency in which you do business.|

1. Click **[!UICONTROL Next]**.

   The system creates a report suite. 

1. To begin deployment, click **[!UICONTROL Next]**, then click one of the following options:

   | Element | Description |
   |--- |--- |
   |Deploy|Launches  Dynamic Tag Management, where you can log in and deploy Analytics. This process automatically implements the AppMeasurement.js file and the Experience Cloud ID service ( VisitorAPI.js).<br>**Important**: In a new browser tab, a help page is displayed that walks you through  Adobe Analytics deployment via Dynamic Tag Management.|
   |Download|Downloads the installation file, named `INSTALL-ME <report suite name>.js`. This option is for experienced users who understand  JavaScript Implementation. <br>**Important**: Downloading the code does not constitute deploying  Analytics. This is a manual deployment that you perform on the pages of your site, or through Adobe consulting services.|

1. Run a report.

   After deploying the Analytics tool, you can run a report in Reports & Analytics to confirm that data is coming to your site. (See [Sign in and Navigate](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/analytics-navigation.html) to get familiar with the Analytics interface.)

   For example, a **[!UICONTROL Site Metrics]** > **[!UICONTROL Real-Time]** lets you see immediate data.

   >[!NOTE]
   >
   >The [!UICONTROL Real-Time] report requires some configuration prior to running. See [Configure Real-Time Report](https://marketing.adobe.com/resources/help/en_US/reference/t_realtime_admin.html).

**Example Real-Time Report**

   ![](assets/real-time-report.png)

