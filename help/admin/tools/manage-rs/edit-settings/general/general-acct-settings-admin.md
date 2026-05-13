---
description: Field descriptions for report suite General Account Settings in Admin.
title: General Account Settings
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
TQID: https://experienceleague.adobe.com/1HGpY4lstZB6baXYggrD4xni1SWbYTDLa2fqYw11yd4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# General Account Settings

Field descriptions for a report suite's General Account Settings in Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

These settings contain editing options for basic report suite functionality, such as name and time zone.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring general account settings](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/manage-report-suites/configuring-general-account-settings){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

| Option | Description |
|--- |--- |
|Site Title|Identifies your site. Give each report suite a unique site title.|
|Base URL|Specifies the report suite's main website. The Base URL does not affect referrer filtering. Use [internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) instead.|
|Time Zone|Determines the date and time associated with your report data.  Changing the time zone for a live report suite creates either a spike or gap in report data. To minimize the impact, Adobe recommends changing time zones during non-peak hours to avoid skewing data.  For example, if you change the report suite time zone from Central to Pacific at 3:00pm, the report suite's current time becomes 1:00pm. Because reporting has already collected data for the 1:00 hour, reports show a traffic spike between 1:00pm and 3:00pm.  Alternatively, if you change the report suite time zone from Central to Eastern at 3:00pm, the report suite's current time becomes 4:00pm. Reports display no data between 3:00pm and 4:00pm on the day of the time change.|
|Default Page|If your [!UICONTROL Most Popular Pages] report contains URLs rather than page names, this setting prevents multiple URLs from representing the same page. For example, the URLs `https://example.com` and `https://example.com/index.html` are typically the same page. You can remove default filenames so that these two URLs would both show up as `https://example.com`.  If left blank, the following filenames are removed from the URLs:  index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi, and home.asp.  To disable stripping of filenames altogether, enter a value that is never present in your URLs.|
| Replace the last octet of IP addresses with 0 | When enabled, replaces the last octet of IP addresses with a zero. This occurs before geo-related reports are populated and therefore may impact the accuracy of these reports. |
| IP Obfuscation | Turns IP addresses into non-recognizable strings, essentially removing them from Adobe data stores. When IP Obfuscation is enabled, the original IP addresses are permanently lost. <br> **Note**: The IP addresses are obfuscated everywhere in Analytics, including Data Warehouse. However, the IP setting in Target is controlled separately, so this setting has no impact on Target.<br> If IP obfuscation is enabled, all needed processing including IP filtering/exclusion, bot rules and Geosegmentation lookups are done before the IP address is obfuscated. You don't need to change anything when you enable IP obfuscation.<ul><li>Checking **Disabled** leaves the IP address in the data.</li><li>Checking **Obfuscate IP address** changes the IP to two colons followed by a hashed value (e.g., `::1932023538`).</li><li>Checking **Remove IP address** replaces the IP address with `::X.X.X.X` in the data, after geo-lookup.<br/>This option is selected by default for new report suites.</li></ul>**Note**: This setting might require changes to custom [bot rules](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) or [IP exclusions](/help/admin/tools/exclude-ip.md).<br> **Note**: Data collected using the Web SDK can have IP obfuscation applied at the Edge Network through [data stream configuration](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#@advanced-options). If IP obfuscation is applied at the Edge Network, it is already obfuscated when it reaches Analytics. This obfuscation impacts bot rules and geo lookups. |
| Transaction ID Storage | Enables you to use [Transaction ID](/help/import/data-sources/transactionid.md) data sources. |
| Enable Data Warehouse | Enables the Data Warehouse UI under Analytics > Tools > Data Warehouse. |
| Zip Option | Lets you specify the zip code instead of using whatever our geo IP lookup produces. |
| Multi-byte character support | Multibyte character support stores characters in the report suite using UTF-8. Upon receipt, the system converts data from your web page's character set to the UTF-8 character set, so you can use any language in your marketing reports. Contact your Adobe Account Team or Customer Care to change the multibyte character support for an existing report suite. |
| Activated | Specifies whether this report suite is activated or not. |
| Base currency | Lets you specify the base [currency](/help/implement/vars/config-vars/currencycode.md) for this report suite. |
| Organization ID | The ID associated with your provisioned Experience Cloud company. This ID is a 24-character alphanumeric string, followed by (and must include) @AdobeOrg. |
