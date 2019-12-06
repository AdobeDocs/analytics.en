---
description: Customize user access at a granular level, including eVars, traffic reports, solution reports, and pathing reports.
keywords: groups;permissions
subtopic: Users and groups
title: Customize dimension permissions
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
---

# Customize dimension permissions

> [!IMPORTANT] User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe will notify you when it is your time to migrate users. After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** will be retired.

Customize user access at a granular level, including eVars, traffic reports, solution reports, and pathing reports.

 **[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Customize]**

> [!IMPORTANT] Some dimensions are not permissionable at this time. These dimensions are: Mobile Bookmark Length; Mobile Device Number; Mobile DRM; Mobile Information Services; Mobile Java VM; Mobile Mail Decoration; Mobile Net Protocols; Mobile OS; Mobile push to talk.
>
>These dimensions are available for all users, regardless of other permissions.

The settings on this page pertain to the report suites selected on the [!UICONTROL Define User Groups] page.

![](assets/permissions-dimensions.png)

Understand the following information about the Dimension category for permissions.

* eVars 1-250 are individually permissioned.
* All traffic reports are dimensions.
* Video & Mobile reports are dimensions, as well as other Analytics solutions reports (Experience Manager, Advertising Cloud, Social, and do on.) 
* Pathing reports are available if a user has access to the parent dimension.
* All current dimensions and metrics within custom groups have been automatically migrated to the new categories. If an existing group has metrics enabled, it will be given all newly permissionable dimensions (eVars and content aware) and metrics by default.
* Classifications Importer (formerly, SAINT) permissions: Access to classifications is determined by access to the [variable](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html) on which the classification is based.

For more information, see [Frequently Asked Questions about Permission Changes](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html).

**Customize Dimensions**

The following items are dimensions that you can permission.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Descriptions </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVars </a> </p> </td> 
   <td colname="col2"> <p>eVars 1-250 are individually permissioned. eVars are custom conversion variables that you use to segment conversion success metrics in custom reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html"> Props </a> </p> </td> 
   <td colname="col2"> <p>Props are custom traffic variables. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html"> Traffic props and conversion eVars </a> in Analytics Implementation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html"> Hierarchy </a> </p> </td> 
   <td colname="col2"> <p> The hierarchy (hierN) variable determines the location of a page in your site's hierarchy or page structure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> Similar to how List Props function, list variables allow multiple values within the same image request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Refers to standard (out-of-the-box) dimensions in Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Activity Map reporting dimensions: Activity Map Page; Activity Map Link; Activity Map Region; Activity Map Link By Region; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>This Partner integration is no longer active. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>This Partner integration is no longer active. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Not used. </p> </td> 
  </tr> 
 </tbody> 
</table>
