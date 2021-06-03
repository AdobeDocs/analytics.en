---
description: Customize group permission to Analytics tools, report suite tools, metrics, and dimensions.
keywords: groups;permissions
subtopic: Users and groups
title: Customize report access - overview
feature: Admin Tools
uuid: 818a7196-8b43-4654-8d5f-800b3122aad3
exl-id: f70b53b5-1399-4b9b-ad09-df8425baeca4
---
# Customize report access - overview

>[!IMPORTANT]
>
>User and product management has moved to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** will be retired.

Customize group permission to Analytics tools, report suite tools, metrics, and dimensions.

 **[!UICONTROL Add New Group]** > **[!UICONTROL Report Access]**

The [!UICONTROL Report Access] section on the [!UICONTROL Define User Group] page provides access categories that enable you to customize permissions at a granular level.

![](assets/report-access.png)

For example, you can create a group with access to multiple Analytics tools ( [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], and [!UICONTROL Report Builder]), with permission to specific metrics and dimensions (including eVars), and capabilities like segment or calculated metrics creation.

## What You Should Know about Permissions {#section_3D25D4A5BD044008870C5B98F696244E}

<table id="table_DB7806E05E2040EC9A4CB7C3596879EC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administrator access / predefined groups </p> </td> 
   <td colname="col2"> <p> Predefined groups are no longer required for administrators. Administrators now have access to all items (tools, metrics, dimensions), as well as Web Service access, Report Builder, and Activity Map. </p> <p>The purpose of groups is to grant or restrict access to non-administrative users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom groups </p> </td> 
   <td colname="col2"> <p> Custom groups have replaced predefined groups. Existing predefined groups will be migrated to custom groups, using the same group name. Any custom groups that you have created, including their settings, will be preserved. However, you will notice that the location of settings will have moved. For example, Company settings (in Customize Admin Console) are now in <a href="/help/admin/user-management2/c-customize-report-access/groups-analytics-tools.md"> Customize Analytics Tools</a>. </p> <p> Users belonging to <span class="term"> All Report Access</span> have been migrated to a custom group with access to: </p> 
    <ul id="ul_7E1B443DEEF7452E85FEB30CA0BBC8BE"> 
     <li id="li_A510C2A4129340E0AB08EEBDBE4AEAD9">All Dimensions </li> 
     <li id="li_8BA1D7A2527C4F10AC93108B9E87F418">All Metrics </li> 
     <li id="li_265830A2C6B94AF28720DA99980EAA51">All Report Suites </li> 
     <li id="li_685B99DEAB814D7B9C11B14AA4CB8CD4">Channel Report </li> 
     <li id="li_B35420302AAB42509BD6AF0FA6349BF8">Anomaly Detection </li> 
     <li id="li_3787E4696C454D3ABD1D75F6C282A9A2">Real-Time Report </li> 
     <li id="li_3797DF9C40D1426588819116362962F5">Analysis Workspace Access </li> 
    </ul> <p>Administrators can delete custom groups and create their own, as all settings that were previously available in predefined groups are available for customization under the <span class="wintitle"> Report Access</span> settings in Define User Groups</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimension-Level Permissions </p> </td> 
   <td colname="col2"> <p>You can customize permissions to include or exclude access to dimensions (in addition to metrics). </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>All current dimensions and metrics within custom groups have been automatically migrated to the new categories. If an existing group has metrics enabled, it will be given all newly permissionable dimensions (eVars and content aware) and metrics by default. </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> Classifications Importer (formerly, SAINT) permissions: Access to classifications is determined by access to the <a href="https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html"> variable</a> on which the classification is based. </li> 
    </ul> <p>See <a href="/help/admin/user-management2/c-customize-report-access/groups-dimensions.md"> Customize Dimension Permissions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/enterprise/using/admin-console.html"> Adobe Admin Console</a> </p> </td> 
   <td colname="col2"> <p>Recommended only for new customers or customers with companies <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html"> provisioned in the Experience Cloud</a>. A migration for existing <span class="keyword"> Analytics</span> customers to the <span class="keyword"> Experience Cloud</span> identity management system is planned. </p> <p>More information is available in <a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html"> Analytics User Migration to the Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Content Aware </p> </td> 
   <td colname="col2"> <p>Content Aware includes variables that let you manage the permissions on metrics related to Experience Cloud solution integrations. You can manage permissions on <span class="keyword"> Social</span>, <span class="keyword"> Mobile</span>, or any other data that was inserted through a <span class="keyword"> Experience Cloud</span> integration. These will be enabled by default. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Defunct permissions / reports </p> </td> 
   <td colname="col2"> <p>These defunct reports will be removed: </p> 
    <ul id="ul_C0415CFF0562472297272EC58ECC0774"> 
     <li id="li_62B1CE33B1454987B878B321EB40D62E">Monthly Summary </li> 
     <li id="li_71CD776D212540A18F9B083D2E11A296">Visitor Home Page </li> 
     <li id="li_406200AD68C74D11B5F53988A4E76A68">Netscape Plugins </li> 
     <li id="li_A124637D69C94C78921C8B028D890541">Key Visitors </li> 
     <li id="li_5C26FF95371B4F3080FF75C7F8DE0F72">Pages Viewed By Key Visitors </li> 
     <li id="li_E7E262BD0CF64E16B838F995F6A13B8A">Visitor Snapshot </li> 
     <li id="li_0EDC74625C0D4B1A992FCA49B648E4C0">DRM </li> 
     <li id="li_ACC92E6EA188409486E7C943F26B9DAC">Net Protocols </li> 
     <li id="li_6E18C4D12377416A8124BBD13164B03A">Java Version </li> 
     <li id="li_1599265E59EF4F34BB406356410C9E68">Bookmark URL Length </li> 
     <li id="li_3035442010984C409089B21E03DB7BCC">Device Number Transmit </li> 
     <li id="li_6B2163ED8FC84EBF933D97A504B4D527">PTT </li> 
     <li id="li_0EB8A4A7619B45DF87109B183A7C69C8">Decoration Mail Support </li> 
     <li id="li_989FAC662F7344E6BDDC517B79D4581E">Information </li> 
     <li id="li_F1FB7F8E415443F3B63F6D11D59A04AB">Information Service </li> 
    </ul> <p>These reports: </p> 
    <ul id="ul_F71505C59F734EA9B541BF8AB9F9388F"> 
     <li id="li_7D461907B895447280E69CF1520DF47C">Can still be accessed by Bookmarks. </li> 
     <li id="li_27BA2DD6BA4C446FBAA06B6C76CD171F">Are not included in new Dimensions permission category. </li> 
     <li id="li_504E9D8421714406A0F37DEF1E10E34B">Can no longer have their permissions edited. </li> 
     <li id="li_0022E8DCA07344C793847E8282EFBEEF">Will retain access for custom groups with current access. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
