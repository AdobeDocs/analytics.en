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
>For improved visitor tracking, we strongly recommend that you enable [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Add an Adobe Analytics Tool {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Click  **[!UICONTROL  *`Web Property Name`*]** > **[!UICONTROL Overview]** > **[!UICONTROL Add a Tool]** > **[!UICONTROL Adobe Analytics]** .

   ![](assets/dtm-add-analytics-tool.png)

1. Fill in the fields: 

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tool Type </p> </td> 
   <td colname="col2">The type of tool, such as <span class="keyword"> Adobe Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tool Name </p> </td> 
   <td colname="col2">A descriptive name for this tool. This name displays on the <span class="wintitle"> Overview</span> tab under <span class="wintitle"> Installed Tools</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Configuration Method </p> </td> 
   <td colname="col2"> <p> <b>Automatic</b> (Recommended): Use dynamic tag management to manage the configuration. This method enables automatic synchronization of <span class="keyword"> Adobe Analytics</span> report suites via a <span class="keyword"> Experience Cloud</span> login or Web Services ID, and manages the AppMeasurement code. </p> <p>After the accounts are connected, Dynamic Tag Management pulls the <span class="keyword"> Adobe Analytics</span> report suite IDs and names into the tool configuration interface, allowing for increased speed in tool deployment with less possibility for user errors. </p> <p> <p>Note: You must choose the <span class="wintitle"> Automatic</span> option if you are an <span class="keyword"> Adobe Analytics Premium</span> customer. </p> </p> <p>Fill in the fields specific to automatic configuration: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (Default) Uses <span class="keyword"> Experience Cloud</span> single sign-on. Specify your Experience Cloud ID and password. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Web Services</b>: Specify your Web Services username and shared secret. </p> <p>Shared secret credentials are located in <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Company Settings</span> &gt; <a href="https://docs.adobe.com/content/help/en/analytics/admin/company-settings/web-services-admin.html"> Web Services</a>. </p> <p>Developers, see <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api"> Get Web Service Access to the Enterprise API</a> for help with obtaining Web Services credentials. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manual</b>: Manually manage the AppMeasurement code. You can download the <span class="keyword"> Analytics</span><span class="keyword"> AppMeasurement</span> code from <span class="ignoretag"><span class="uicontrol"> Admin Tools</span> &gt; <span class="uicontrol"> Code Manager</span></span>. </p> <p>Click <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html"> JavaScript (new)</a> for information about downloading the code locally to copy and paste in the <span class="wintitle"> Edit Code</span> field in <a href="/help/implement/c-implement-with-dtm/c-aa-tool/library-management.md"> Library Management</a>. </p> <p>Fill in the fields specific to a manual configuration: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>Production Account ID: </b>(Required) Your production account for data collection. For Analytics, this is your report suite ID. Dynamic Tag Management automatically installs the correct account in the production and staging environment. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>Staging Account ID: </b>(Required) Used in your development or test environment. For Analytics, this is your report suite ID. A staging account keeps your testing data separate from production. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Tracking Server: </b>Specify the information for your tracking server. </p> <p>The <span class="wintitle"> Tracking Server</span> and <span class="wintitle"> SSL Tracking Server</span> variables are used for first-party cookie implementation to specify the domain at which the image request and cookie is written. For more information, see the <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html"> Correctly Populate the trackingServer and trackingServerSecure Variable</a> article. </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>SSL Tracking Server: </b>Specify the information for your SSL tracking server. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Create Tool]** to create the tool and display it for editing.

   Tools are displayed on the [!UICONTROL Overview] tab, under [!UICONTROL Installed Tools]. 

1. (Conditional) Configure the tool further as necessary by following the directions in the links below ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies], and [!UICONTROL Customize Page Code]).

See [Frequently Asked Questions About the Adobe Analytics Tool](/help/implement/faq.md) for additional information about this tool.

## Edit an Existing Adobe Analytics Tool {#section_148B16AF429B4949B06238D90635B726}

You can edit an existing Adobe Analytics tool to change its configuration settings.

1. Click the  ![](assets/settings_gear.png) icon next to an installed tool from the [!UICONTROL Overview] tab. 
1. Edit the fields as desired.

   The following table includes only those elements that differ from the elements available when you are creating an Analytics tool, as described above. However, you can change any element on the page, as described in both tables. 

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enable Automatic Configuration </p> </td> 
   <td colname="col2"> <p>Note: Enabling this setting changes a manually configured implementation to the automatic configuration method described in <span class="term"> Configuration Method</span>. </p> <p>This option lets Dynamic Tag Management automatically retrieve your <span class="keyword"> Adobe Analytics</span> account's configuration. </p> <p>The latest available AppMeasurement code is used and upgrade notifications are displayed for selection as new versions become available. You can also roll back to previous AppMeasurement versions as necessary, such as for compatibility reasons. Up to five previous versions are displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Update Credentials </p> </td> 
   <td colname="col2"> <p>Refresh the API, for example, to update report suites associated with a user. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Conditional) Configure the tool further as necessary by following the directions in the links below ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies], and [!UICONTROL Customize Page Code]). 
1. Click **[!UICONTROL Save Changes]**.
