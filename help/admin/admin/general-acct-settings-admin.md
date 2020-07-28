---
description: Field descriptions for report suite General Account Settings in Admin.
title: General Account Settings
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
---

# General Account Settings

Field descriptions for a report suite's General Account Settings in Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

These settings contain editing options for basic report suite functionality, such as name and time zone.

| Option | Description |
|--- |--- |
|Site Title|Identifies your site. Give each report suite a unique site title.|
|Base URL|Specifies the report suite's main website. The Base URL does not affect referrer filtering. Use [internal URL filters](/help/admin/admin/internal-url-filter-admin.md) instead.|
|Time Zone|Determines the date and time associated with your report data.  Changing the time zone for a live report suite creates either a spike or gap in report data. To minimize the impact, Adobe recommends changing time zones during non-peak hours to avoid skewing data.  For example, if you change the report suite time zone from Central to Pacific at 3:00pm, the report suite's current time becomes 1:00pm. Because reporting has already collected data for the 1:00 hour, reports show a traffic spike between 1:00pm and 3:00pm.  Alternatively, if you change the report suite time zone from Central to Eastern at 3:00pm, the report suite's current time becomes 4:00pm. Reports display no data between 3:00pm and 4:00pm on the day of the time change.|
|Default Page|If your [!UICONTROL Most Popular Pages] report contains URLs rather than page names, this setting prevents multiple URLs from representing the same page. For example, the URLs `https://mysite.com` and `https://mysite.com/index.html` are typically the same page. You can remove default filenames so that these two URLs would both show up as `https://mysite.com`.  If left blank, the following filenames are removed from the URLs:  index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi, and home.asp.  To disable stripping of filenames altogether, enter a value that is never present in your URLs.|
|Replace the last octet of IP addresses with 0|Removing the last octet is done before IP filtering. As such, the last octet is replaced with a 0, and IP exclusion rules should be updated to match IP addresses with a zero on the end. Matching * should match 0. Checking this option means that the IP address is altered before it is processed. For example, the IP address 134.123.567.780 gets changed to 134.123.567.0. Geosegmentation data will not be quite as exact as when the whole IP address is used. Specifically, city accuracy is going to be more affected than country or region accuracy. Both Bot rules and VISTA rules are affected because the entire IP address is unavailable to them. In addition, any processing rules that are IP based, including marketing channel rules and report suite processing rules, are affected by this setting. <br> **Note**: This setting is enabled by default for any new report suites created in the London Data Center after January 2019, but only if the settings for those report suites are copied from a template listed in the Admin Console. Report suites whose settings are duplicated from other report suites will inherit all settings from the selected report suite.|
|IP Obfuscation|Turns IP addresses into non-recognizable strings, essentially removing them from Adobe data stores. When IP Obfuscation is enabled, the original IP addresses are permanently lost. <br> **Note**: The IP addresses are obfuscated everywhere in Analytics, including Data Warehouse. However, the IP setting in Target is controlled separately, so this setting has no impact on Target.<br> If IP obfuscation is enabled, IP exclusion happens before the IP address is obfuscated, so customers don't need to change anything when they enable IP obfuscation. <br> Checking **Disabled** leaves the IP address in the data. <br> Checking **Obfuscate IP address** changes the IP to a hashed value (e.g., 234abc6493872038). <br> Checking **Remove IP address** replaces the IP address with x.x.x.x in the data, after geo-lookup. <br> **Note**: This setting might require changes to custom [bot rules](/help/admin/admin/bot-removal/bot-rules.md) or [IP exclusions](/help/admin/admin/exclude-ip.md).|
|Transaction ID Storage|Enables you to use [Transaction ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md) data sources.|
|Activate Ad Hoc Analysis|Indicates whether the report suite in question shows up as an available report suite in Ad Hoc Analysis. Use this setting to limit which report suites show up as an option for Ad Hoc Analysis. For example, you can disable Ad Hoc Analysis for development and QA report suites.|
|Enable Data Warehouse|Enables the Data Warehouse UI under Analytics > Tools > Data Warehouse.|
