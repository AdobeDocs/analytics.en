---
description: You can create a new report suite by selecting a pre-defined template, or by using one of your existing report suites to serve as a model.
title: New report suite - settings
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
---
# New report suite - settings

You can create a new report suite by selecting a pre-defined template, or by using one of your existing report suites to serve as a model.

Descriptions of the elements used when [creating a report suite](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>The [Virtual Report Suite documentation](/help/components/vrs/c-workflow-vrs/vrs-create.md) shows you how to create virtual report suites.

| Element | Description |
| --- | --- |
| Report Suite ID | Specifies a unique ID that can contain only alphanumeric characters. This ID cannot be changed after it is created. Adobe sets the required ID prefix and it cannot be changed, either.  When creating multiple report suites, ensure that the naming convention you use guarantees unique report suite IDs. |
| Site Title | Identifies the report suite in  Admin Tools. This title is also used in the  Report Suite drop-down list in the suite header. |
| Time Zone | Schedules events and time stamp data. |
| Base URL | (Optional) Defines the base domain for the report suite. This URL functions as an internal URL filter if you do not explicitly define internal URL filters for the report suite. |
| Default Page | (Optional) Strips occurrences of the  Default Page value from URLs it encounters. If your  Most Popular Pages report contains URLs rather than page names, this setting prevents multiple URLs for the same web page.  For example, the URLs `https://example.com` and `https://example.com/index.html` are typically the same page.<p> You can remove extraneous filenames so that both these URLs show up as `https://example.com` in your reports. If you do not set this value, Analytics automatically removes the following filenames from URLs: `index.htm`, `index.html`, `index.cgi`, `index.asp`,  `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi`, and `home.asp`. To disable filename stripping, specify a Default Page value that never occurs in your URLs. |
| Go Live Date | Informs Adobe of the date that you expect this report suite to become active. If your deployment schedule changes, provide an updated traffic estimate using the  Permanent Expected Traffic tool in  Traffic Management. |
| Estimated Page Views Per Day | Identifies the estimated number of page views you expect this report suite to support in a day. Large traffic volumes require a longer approval process. To avoid processing delays, be as accurate as possible with this estimate. |
| Base Currency | Specifies the default currency used to store all monetary data. Analytics reporting converts transactions in other currencies to the base currency, using the current conversion rate at the time it receives the data. Analytics reporting uses the  currencyCode JavaScript variable to identify the currency of a given transaction. |
| Disable Multi-byte Character Support | Disables multibyte character support for the report suite. If you disable multibyte character support, the system assumes that data is in `ISO-8859-1` format. Web pages must specify their character set in the  charSet JavaScript variable. <p>Multibyte character support stores characters in the report suite using UTF-8. Upon receipt, the system converts data from your web page's character set to the UTF-8 character set, so you can use any language in your marketing reports.  Contact your Adobe Account Team or Customer Care to change the multibyte character support for an existing report suite. |

{style="table-layout:auto"}
