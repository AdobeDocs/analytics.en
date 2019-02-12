---
description: Field descriptions for report suite General Account Settings in Admin.
seo-description: Field descriptions for report suite General Account Settings in Admin.
seo-title: General Account Settings
solution: Analytics
title: General Account Settings
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
index: y
internal: n
snippet: y
---

# General Account Settings

Field descriptions for report suite General Account Settings in Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

These settings contain editing options for basic report suite functionality, such as name and time zone. 

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Site Title</span> </td> 
   <td colname="col2"> <p>Identifies your site. Give each report suite a unique site title. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Base URL</span> </td> 
   <td colname="col2"> <p>Specifies the report suite's main website. The Base URL does not affect referrer filtering. Use <a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local"> internal URL filters</a> instead. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Time Zone</span> </td> 
   <td colname="col2"> <p>Determines the date and time associated with your report data. </p> <p>Changing the time zone for a live report suite creates either a spike or gap in report data. To minimize the impact, Adobe recommends changing time zones during non-peak hours to avoid skewing data. </p> <p>For example, if you change the report suite time zone from Central to Pacific at 3:00pm, the report suite's current time becomes 1:00pm. Because reporting has already collected data for the 1:00 hour, reports show a traffic spike between 1:00pm and 3:00pm. </p> <p>Alternatively, if you change the report suite time zone from Central to Eastern at 3:00pm, the report suite's current time becomes 4:00pm. Reports display no data between 3:00pm and 4:00pm on the day of the time change. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Conversion Level</span> </td> 
   <td colname="col2"> <p> Enables or disables e-commerce variables such as eVars and campaigns. Use the <span class="uicontrol"> Enabled, no Shopping Cart</span> option to hide all shopping cart reports if you don't have a shopping cart on your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Default Page</span> </td> 
   <td colname="col2"> <p> If your <span class="wintitle"> Most Popular Pages Report</span> contains URLs rather than page names, this setting prevents multiple URLs from representing the same page. For example, the URLs <span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove default filenames so that these two URLs would both show up as <span class="filepath"> https://mysite.com</span>. </p> <p>If left blank, the following filenames are removed from the URLs: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default.cgi</span>, <span class="filepath"> default.asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home.cgi</span>, and <span class="filepath"> home.asp</span>. </p> <p>To disable stripping of filenames altogether, enter a value that is never present in your URLs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Replace the last octet of IP addresses with 0 </span> </td> 
   <td colname="col2"> <p>Removing the last octet is done before IP filtering. As such, the last octet is replaced with a 0, and IP exclusion rules should be updated to match IP addresses with a zero on the end. Matching * should match 0. </p> <p>Checking this option means that the IP address is altered before it is processed. For example, the IP address 134.123.567.780 gets changed to 134.123.567.0. Geosegmentation data will not be quite as exact as when the whole IP address is used. Specifically, city accuracy is going to be more affected than country or region accuracy. Both Bot rules and VISTA rules are affected because the entire IP address is unavailable to them. In addition, any processing rules that are IP based, including marketing channel rules and report suite processing rules, are affected by this setting. </p> <p>Note:   This setting is enabled by default for any new report suites created in the London Data Center after January 2019, but only if the settings for those report suites are copied from a template listed in the Admin Console. Report suites whose settings are duplicated from other report suites will inherit all settings from the selected report suite. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> IP Obfuscation</span> </td> 
   <td colname="col2"> <p>Turns IP addresses into non-recognizable strings, essentially removing them from Adobe data stores. When IP Obfuscation is enabled, the original IP addresses are permanently lost. </p> <p>Note:  The IP addresses are obfuscated everywhere in Analytics, including Data Warehouse. However, the IP setting in Target is controlled separately, so this setting has no impact on Target. </p> <p>If IP obfuscation is enabled, IP exclusion happens before the IP address is obfuscated, so customers don'’t need to change anything when they enable IP obfuscation. </p> <p>Checking <span class="uicontrol"> Disabled</span> leaves the IP address in the data. </p> <p>Checking <span class="uicontrol"> Obfuscate IP address</span> changes the IP to a hashed value (e.g., 234abc6493872038). </p> <p>Checking <span class="uicontrol"> Remove IP address</span> replaces the IP address with x.x.x.x in the data, after geo-lookup. </p> <p>Note: This setting might require changes to custom <a href="../../admin/admin/bot-rules/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> bot rules</a> or<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"> IP exclusions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Geography Reporting</span> </td> 
   <td colname="col2">Enables <span class="uicontrol"> Visitor</span> &gt; <span class="uicontrol"> GeoSegmentation</span> reports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transaction ID Storage</span> </td> 
   <td colname="col2"> <p>Enables you to use <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID" format="https" scope="external"> Transaction ID</a> data sources. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Activate Ad Hoc Analysis</span> </td> 
   <td colname="col2"> <p>Indicates whether the report suite in question shows up as an available report suite in Ad Hoc Analysis. Use this setting to limit which report suites show up as an option for Ad Hoc Analysis. For example, you can disable Ad Hoc Analysis for development and QA report suites. </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> Enable Data Warehouse</span> </td> 
   <td colname="col2"> <p>Enables Data Warehouse UI under <span class="uicontrol"> Tools</span> &gt;<span class="uicontrol"> Data Warehouse</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

