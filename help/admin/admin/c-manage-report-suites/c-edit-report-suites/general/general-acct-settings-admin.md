---
description: Field descriptions for report suite General Account Settings in Admin.
title: General Account Settings
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
---
# General Account Settings

Field descriptions for a report suite's General Account Settings in Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

These settings contain editing options for basic report suite functionality, such as name and time zone.

Here is a video on configuring General Account Settings:

>[!VIDEO](https://video.tv.adobe.com/v/332330/?quality=12)

| Option | Description |
|--- |--- |
|Site Title|Identifies your site. Give each report suite a unique site title.|
|Base URL|Specifies the report suite's main website. The Base URL does not affect referrer filtering. Use [internal URL filters](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) instead.|
|Time Zone|Determines the date and time associated with your report data.  Changing the time zone for a live report suite creates either a spike or gap in report data. To minimize the impact, Adobe recommends changing time zones during non-peak hours to avoid skewing data.  For example, if you change the report suite time zone from Central to Pacific at 3:00pm, the report suite's current time becomes 1:00pm. Because reporting has already collected data for the 1:00 hour, reports show a traffic spike between 1:00pm and 3:00pm.  Alternatively, if you change the report suite time zone from Central to Eastern at 3:00pm, the report suite's current time becomes 4:00pm. Reports display no data between 3:00pm and 4:00pm on the day of the time change.|
|Default Page|If your [!UICONTROL Most Popular Pages] report contains URLs rather than page names, this setting prevents multiple URLs from representing the same page. For example, the URLs `https://example.com` and `https://example.com/index.html` are typically the same page. You can remove default filenames so that these two URLs would both show up as `https://example.com`.  If left blank, the following filenames are removed from the URLs:  index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi, and home.asp.  To disable stripping of filenames altogether, enter a value that is never present in your URLs.|
| Replace the last octet of IP addresses with 0 |Removing the last octet is done before any processing is done on the hit, including before IP filtering/exclusion, before checking bot rules, before Geosegmentation lookups, etc. As such, the last octet is replaced with a 0, and IP exclusion rules should be updated to match IP addresses with a zero on the end. Matching * should match 0. For example, the IP address 11.22.33.44 gets changed to 11.22.33.0. Geosegmentation data will not be quite as exact as when the whole IP address is used. Specifically, city accuracy is going to be more affected than country or region accuracy. Both Bot rules and VISTA rules are affected because the entire IP address is unavailable to them. In addition, any processing rules that are IP based, including marketing channel rules and report suite processing rules, are affected by this setting. <br> **Note**: This setting is enabled by default for any new report suites created in the London Data Center after January 2019, but only if the settings for those report suites are copied from a template listed in the Admin Console. Report suites whose settings are duplicated from other report suites will inherit all settings from the selected report suite. |
| IP Obfuscation | Turns IP addresses into non-recognizable strings, essentially removing them from Adobe data stores. When IP Obfuscation is enabled, the original IP addresses are permanently lost. <br> **Note**: The IP addresses are obfuscated everywhere in Analytics, including Data Warehouse. However, the IP setting in Target is controlled separately, so this setting has no impact on Target.<br> If IP obfuscation is enabled, all needed processing including IP filtering/exclusion, bot rules and Geosegmentation lookups are done before the IP address is obfuscated. You don't need to change anything when you enable IP obfuscation.<ul><li>Checking **Disabled** leaves the IP address in the data.</li><li>Checking **Obfuscate IP address** changes the IP to two colons followed by a hashed value (e.g., `::1932023538`).</li><li>Checking **Remove IP address** replaces the IP address with `::X.X.X.X` in the data, after geo-lookup.</li></ul>**Note**: This setting might require changes to custom [bot rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) or [IP exclusions](/help/admin/admin/exclude-ip.md). |
| Transaction ID Storage | Enables you to use [Transaction ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md) data sources. |
| Enable Data Warehouse | Enables the Data Warehouse UI under Analytics > Tools > Data Warehouse. |
| Zip Option | Lets you specify the zip code instead of using whatever our geo IP lookup produces. |
| Multi-byte character support | Multibyte character support stores characters in the report suite using UTF-8. Upon receipt, the system converts data from your web page's character set to the UTF-8 character set, so you can use any language in your marketing reports. Contact your Account Manager or Customer Care to change the multibyte character support for an existing report suite. |
| Activated | Specifies whether this report suite is activated or not. |
| Base currency | Lets you specify the base [currency](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html) for this report suite. |
| Organization ID | The ID associated with your provisioned Experience Cloud company. This ID is a 24-character alphanumeric string, followed by (and must include) @AdobeOrg. |