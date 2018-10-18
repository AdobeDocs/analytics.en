---
description: Enable user permissions for General items (billing, logs, etc.), Company Management, Tools, Web Service Access, Report Builder, and Data Connectors integration.
keywords: groups;permissions
seo-description: Enable user permissions for General items (billing, logs, etc.), Company Management, Tools, Web Service Access, Report Builder, and Data Connectors integration.
seo-title: Customize Analytics Tools permissions
solution: Analytics
subtopic: Users and groups
title: Customize Analytics Tools permissions
topic: Admin tools
uuid: 04577020-f50b-455e-8b94-b7ab87909790
index: y
internal: n
snippet: y
---

# Customize Analytics Tools permissions

Enable user permissions for General items (billing, logs, etc.), Company Management, Tools, Web Service Access, Report Builder, and Data Connectors integration.

 **[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Analytics Tools]** > **[!UICONTROL Customize]**

>[!NOTE]
>
>The Fall 2016 release (October 20) brought changes to group management. See [Administrative Changes - Fall 2016](../../user_management2/c_user_management/permissions-changes.md#concept_86581595B86B47D5B8F90282FC3E31EF) for a summary of changes.

**Report Access - Analytics Tools**

![](assets/report-access-analytics-tools.png)

Click **[!UICONTROL Customize]** to select items to which this group will have access.

![](assets/customize-analytics-tools.png)

**Field Descriptions**

The settings on this page pertain to the report suites selected on the [!UICONTROL Define User Groups] page. 

<table id="table_F8CF3E5E60DA4FCB89ED85C044F0D0F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colspan="2"> <p> <b>General</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../admin/billing_admin.md#concept_B66434D0D6274C96988E40833879A0D2" format="dita" scope="local"> Billing</a> </p> </td> 
   <td colname="col2"> <p>Enables access to billing information, including traffic details for each report suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../admin/code_manager_admin.md#concept_621F6BA24BF140388D7FE4B3B556D384" format="dita" scope="local"> Code Manager</a> </p> </td> 
   <td colname="col2"> <p>Enables permission to download data collection code for web and mobile platforms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code Manager - Web Services </p> </td> 
   <td colname="col2"> <p>Allows a non-administrative user to access the Code Manager through Web Services. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../admin/logs.md#concept_8C55FE944C0C4D0E963645366A0DCFDE" format="dita" scope="local"> Logs</a> </p> </td> 
   <td colname="col2"> <p> Enables permission to log files, which help you see when users log in, their usage, access, report suites, and Admin changes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Logs - Web Services </p> </td> 
   <td colname="col2"> <p>Allows a non-administrative user to access the Admin Tools logs through Web Services. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../c_traffic_management/traffic_management.md#concept_8BD651EE8B84434CB4D6308BC6C01B79" format="dita" scope="local"> Traffic Management</a> </p> </td> 
   <td colname="col2"> <p> Traffic Management page lets you specify expected traffic volume changes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permission Management </p> </td> 
   <td colname="col2"> <p> Grants non-admin users access to the User Management pages in Admin Tools. These users have Read permissions but do not have Write permissions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permissions (Write) - Web Services </p> </td> 
   <td colname="col2"> <p>Grants non-administrative users read and write permission settings under User Management in Web Services. </p> <p> This setting refers specifically to the indicated permissions actions in the Admin API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permissions (Read) - Web Services </p> </td> 
   <td colname="col2"> <p>Allows a non-administrative user to view permission settings under User Management in Web Services. </p> <p> This setting refers specifically to the indicated permissions actions in the Admin API. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p> <b>Company Management</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../company/security_manager.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF" format="dita" scope="local"> Security</a> </p> </td> 
   <td colname="col2"> <p> Grants permission to the <span class="wintitle"> Security Manager</span> page to control access to reporting data. Options include strong passwords, password expiration, IP login restrictions, and email domain restrictions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Support Information </p> </td> 
   <td colname="col2"> <p>Grants permission to the <span class="wintitle"> Support Information</span> in <span class="wintitle"> Company Settings</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../company/web_services_admin.md#concept_4E89942575B544448D70B1296689629C" format="dita" scope="local"> Web Services</a> </p> </td> 
   <td colname="col2"> <p>Allows access to the Web Services page in the Admin Tools interface (<span class="uicontrol"> Company Settings</span> &gt; <span class="uicontrol"> Web Services</span>). </p> <p> The Web Services API provides programmatic access to <span class="keyword"> Adobe Analytics</span> services that let you duplicate and augment functionality available through the user interface. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Announcements </p> </td> 
   <td colname="col2"> <p>Version 14 only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="manage_p3p_admin.md#concept_4D55C48F2D2F41128A4CA2E5FFEC18E7" format="dita" scope="local"> P3P Policy</a> </p> </td> 
   <td colname="col2"> <p>Grants permission to upload your organizations P3P policy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Single Sign-On (Legacy) </p> </td> 
   <td colname="col2"> <p> Grants access to the single sign-on page in Admin Tools. </p> <p> <b>Note:</b> Single sign-on in the Adobe Experience Cloud is implemented using <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html" format="html" scope="external"> account linking</a> between the Experience Cloud and solutions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../company/pending_actions_admin.md#concept_285BB239DB8D4BBC8CA9A88C81A6ECCC" format="dita" scope="local"> Pending Actions</a> </p> </td> 
   <td colname="col2"> <p>Grants permission to manage pending actions in <span class="wintitle"> Company Settings</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../company/co_branding_admin.md#concept_2AFE2EC82A2E429BB0E3AC9D1E6192A4" format="dita" scope="local"> Co-Branding</a> </p> </td> 
   <td colname="col2"> <p>Grants permission to co-brand <span class="keyword"> Analytics</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../admin/preferences_manager.md#concept_479B1352242D45179B71E14500BE8B40" format="dita" scope="local"> Preferences</a> </p> </td> 
   <td colname="col2"> <p>Grants permission to the <span class="wintitle"> Preference Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../company/c_hide_report_suites.md#concept_FE86137A33A84B5D982A96F3592AEEB4" format="dita" scope="local"> Hide Report Suites</a> </p> </td> 
   <td colname="col2"> <p> Grants permission to hide report suites in the <span class="keyword"> Adobe Analytics</span> user interface. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p> <b>Tools</b> </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p>These settings grant access to Analytics tools (interfaces and applications) and advanced capabilities like segmentation and calculated metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/user/clickmap.html" format="html" scope="external"> ClickMap</a> </p> </td> 
   <td colname="col2"> <p>Displays <span class="wintitle"> ClickMap</span> in the <span class="wintitle"> Tools</span> menu in the header. (<b>Note:</b> Adobe recommends using <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-enable.html" format="html" scope="external"> Activity Map</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html" format="html" scope="external"> Current Data</a> </p> </td> 
   <td colname="col2"> <p>Grants permission to use the Current Data feature in reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/dsc/" format="https" scope="external"> Ad Hoc Analysis</a> License Users </p> </td> 
   <td colname="col2"> <p>Grants permission to access <span class="wintitle"> Ad Hoc Analysis</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/t_admin_group.html" format="html" scope="external"> Mobile App Admin </a> </p> </td> 
   <td colname="col2"> <p>Grants access to acquisition links and in-app messages in <span class="keyword"> Mobile Services</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web Service Access </p> </td> 
   <td colname="col2"> <p>Enables Web Services access for non-administrators. Generates Web Service credentials. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/arb/setup.html" format="html" scope="external"> Report Builder</a> </p> </td> 
   <td colname="col2"> <p>Grants members of this group access to <span class="wintitle"> Report Builder</span> licenses. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/" format="https" scope="external"> Analysis Workspace</a> Access </p> </td> 
   <td colname="col2"> <p>Grants users access to Analysis Workspace, the recommended reporting interface for <span class="keyword"> Adobe Analytics</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/user/" format="https" scope="external"> Reports &amp; Analytics</a> Access </p> </td> 
   <td colname="col2"> <p>Grants users access to <span class="wintitle"> Reports &amp; Analytics</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate.html" format="html" scope="external"> Create / Curate Projects</a> in Analysis Workspace </p> </td> 
   <td colname="col2"> <p>Grants users permission to create and curate projects in <span class="wintitle"> Analysis Workspace</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/" format="https" scope="external"> Calculated Metric Creation</a> </p> </td> 
   <td colname="col2"> <p>Grants users permission to create calculated metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/" format="https" scope="external"> Segment Creation</a> </p> </td> 
   <td colname="col2"> <p>Grants users permission to create segments. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <p> <b>Data Connectors</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrations (Create, Update, or Delete) </p> </td> 
   <td colname="col2"> <p>Grants permission to create, update, and delete <a href="https://marketing.adobe.com/resources/help/en_US/genesis/" format="https" scope="external"> Data Connector</a> integrations. </p> </td> 
  </tr> 
 </tbody> 
</table>

