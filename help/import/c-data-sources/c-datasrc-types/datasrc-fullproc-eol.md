---
title: End of life for Full Processing Data Sources
description: Reasons for end of lifing and comparisons between Bulk Data Insertion API and Full Processing Data Sources.
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
---
# End of life for Full Processing Data Sources

For several years, Full Processing Data Sources enabled you to submit hit-level data to Adobe Analytics. This data was processed in the same way as data collected via our JavaScript libraries and mobile app SDK. In 2020, Adobe released the [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), which performs the same functions as Full Processing Data Sources, but with additional features. This topic provides details about additional functionality provided by the Bulk Data Insertion API and outlines differences in file formats.

Starting March 25, 2021, Adobe prevented new Full Processing Data Sources connections from being created. Existing connections were  supported until the service was fully deprecated on January 31, 2022. In addition to our standard documentation, we are providing a walk-through of the [steps needed to submit data via Bulk Data Insertion API](https://adobe.ly/aabdia).

## Why did we end-of-life this feature?

The Bulk Data Insertion API (BDIA) provides additional functionality while covering all use cases supported by Full Processing. You are better served by using Bulk Data Insertion API.

## Key Differences between Full Processing Data Sources and Bulk Data Insertion API

* Bulk Data Insertion allows submission of multiple files which can be processed in parallel. You can use Visitor Groups to ensure visitor continuity and eVar attribution.
* Bulk Data Insertion has data validation as well as error handling capabilities, thus removing some of the administrative work of submitting hit data.
* Bulk Data Insertion supports several options for visitor IDs. You can submit both Analytics ID and Marketing Cloud ID (See [Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) to learn more). Additionally, you can use your own ID as a [seed for generating an ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* Bulk Data Insertion supports List and Context Data Variables.
* Bulk Data Insertion does not support Activity Map data.

## Key Differences in file format and content

* Bulk Data Insertion has some additional required fields. See the [documentation](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) for details.
* To ensure visitor continuity and attribution, Bulk Data Insertion requires rows within files to be sorted in chronological order. See [Visitor Groups](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) to learn about the ordering of Visitor activity across files.
* Bulk Data Insertion requires files to be .csv compressed in .gzip format.
* BDIA uses “timestamp” instead of “date”.

For more detail, see the following comparison of the field values available in Bulk Data Insertion (BDIA) and Full Processing Data Sources (FPDS).

## Comparison of field values available in BDIA and FPDS

| BDIA Variable | Full Processing Column Variable | Description |
| --- | --- | --- |
| aamlh | Not supported | Adobe Audience Manager location hint. |
| browserHeight | browserHeight | Browser height in pixels (for example, 768) |
| browserWidth | browserWidth | Browser width in pixels (for example 1024) |
| campaign | campaign | Conversion campaign tracking code |
| channel | channel | Channel string (for example, Sports Section) |
| colorDepth | colorDepth | Monitor color depth in bits (for example, 24) |
| connectionType | connectionType | Visitor's connection type (LAN or modem) |
| contextData.key | Not supported | Key-values pairs are specified in by naming the header "contextData.product" or "contextData.color" |
| cookiesEnabled | cookiesEnabled | `Y` or `N` for if the visitor supports first-party session cookies |
| currencyCode | currencyCode | Revenue currency code (for example, `USD`) |
| customerID.[customerIDType].authState | Not supported | The authenticated state of the visitor. Supported values are: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT, or '' (case insensitive). Two consecutive single quotes ('') cause the value to be omitted from the query string, which translates to 0 when the hit is made. Please note the supported authState numeric values denote the following: 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT. The customerIDType can be any alphanumeric string, but should be considered case sensitive. |
| customerID.[customerIDType].id | Not supported | The customer ID to use. The customerIDType can be any alphanumeric string, but should be considered case sensitive. |
| customerID.[customerIDType].isMCSeed | Not supported | Whether or not this is the seed for the Marketing Cloud Visitor ID. Supported values are: 0, 1, TRUE, FALSE, '' (case insensitive). Using 0, FALSE, or two consecutive single quotes ('') causes the value to be omitted from the query string. The customerIDType can be any alphanumeric string, but should be considered case sensitive. |
| eVarN | eVarN, i.e. `<eVar2>`...`<eVar>` | Conversion eVar name. You can have up to 75 eVars ( eVar1 - eVar75 ) You can specify the eVar name (eVar12) or a friendly name (Ad Campaign 3). |
| events | events | [Events string](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars), formatted using the same syntax as the s.events variable. For example: scAdd,event1,event7 |
| hierN | hierN, i.e. `<hier2>`…`</hier2>` | Hierarchy name. You can have up to 5 hierarchies ( hier1 - hier5 ). You can specify the default hierarchy name `hier2` or a friendly name (Yankees). |
| homePage | homePage | Y or N -- is the current page the visitor's homepage. |
| ipaddress | Not supported | The visitor's IP address. |
| javaEnabled | javaEnabled | Y or N -- does the visitor have Java enabled. |
| javaScriptVersion | javaScriptVersion | JavaScript version (for example, 1.3). |
| language | Not supported | The browser's supported language. For example, `en-us`. |
| linkName | linkName | Name of link. |
| linkType | linkType | Type of link. Supported values include: `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF of link. |
| listn For example, list2. | Not supported | A delimited list of values that are passed into a variable, then reported as individual line items for reporting |
| marketingCloudVisitorID | Not supported | Marketing Cloud ID. See [Visitor Identification](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) and the Marketing Cloud Visitor ID Service |
| Not supported | charSet | The supported character set for your Web site. For example, UTF-8, ISO-8859-1, and so forth. |
| Not supported | clickAction | Object identifier for visitor click map (oid) |
| Not supported | clickActionType | Object identifier type for visitor click map (oidt) |
| Not supported | clickContext | Page identifier for visitor click map (pid) |
| Not supported | clickContextType | Page identifier type for visitor click map (pidt) |
| Not supported | clickSourceID | Source index for visitor click map (oi) |
| Not supported | clickTag | Object tag name for visitor click map (ot) |
| Not supported | scXmlVer | Marketing reports XML request version number (for example, 1.0). |
| Not supported | timezone | Visitor's time zone offset from GMT in hours (for example, -8). |
| pageName | pageName | Name of the page |
| pageType | pageType | Type of page (e.g., "Error Page"). |
| pageURL | pageURL | Page URL (for example, https://www.example.com/index.html). |
| plugins | plugins | Semicolon-separated list of browser plug-in names. |
| products | products | List of all products on the page. Separate products with a comma. For example: Sports;Ball;1;5.95,Toys; Top;1:1.99. |
| prop1 - prop75 | propN, i.e. `<prop2>`…`</prop2>` | Property# string (for example, Sports Section). |
| propN | propN | Property values for your properties. |
| purchaseID | purchaseID | Purchase ID number. |
| referrer | referrer | URL for page referrer. |
| reportSuiteID | s_account | Specifies the report suites where you want to submit data. You should separate multiple report suite IDs with a comma. |
| resolution | resolution | Monitor resolution (for example, 1024x768). |
| server | server| Server string. |
| state | state | Conversion state string. |
| timestamp | date | Use the ISO 8601 date format of YYYY-MM-DDThh:mm:ss±UTC_offset (for example, 2021-09-01T12:00:00-07:00 ), or Unix Time Format (the number of seconds elapsed since January 1, 1970). |
| trackingServer | Not supported | Can only be supplied via column header. |
| transactionID | Not supported | Common value used to tie multi-channel user activities together for reporting purposes. For more information, see the [Data Sources User Guide](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources). |
| userAgent | Not supported | User agent string |
| visitorID | visitorID | Visitor's Analytics ID. See [Visitor Identification](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| zip | zip | Conversion zip code. |
