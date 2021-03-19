---
title:
description:
---

# End of life for Full Processing Data Sources

For several years, Full Processing Data Sources has enabled you to submit hit-level data to Adobe Analytics. This data was processed in the same way as data collected via our JavaScript libraries and mobile app SDK. In 2020, Adobe released the [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), which performs the same functions as Full Processing Data Sources, but with additional features. This topic provides details about additional functionality provided by the Bulk Data Insertion API and outlines differences in file formats.

Starting March 25, 2021, Adobe will prevent new Full Processing Data Sources connections from being created. Existing connections will continue to be supported until the service is fully deprecated. The deprecation will take place in 2021, though a specific date has not yet been determined.

## Why are we end-of-lifing this feature?

The Bulk Data Insertion API (BDIA) provides additional functionality while covering all use cases supported by Full Processing. We believe you will be better served by using Bulk Data Insertion API.

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

| BDIA, FPDS, Both | BDIA Variable | Full Processing Column Variable | Description |
| --- | --- | --- | --- |
| BDIA | aamlh | Not supported | Adobe Audience Manager location hint. See valid ID values in the AAM region listing table below. |
| Both | browserHeight | browserHeight | Browser height in pixels (for example, 768) |
| Both | browserWidth | browserWidth | Browser width in pixels (for example 1024) |
| Both | campaign | campaign | Conversion campaign tracking code |
| Both | channel | channel | Channel string (for example, Sports Section) |
| Both | colorDepth | colorDepth | Monitor color depth in bits (for example, 24) |
| Both | connectionType | connectionType | Visitor's connection type (LAN or modem) |
| BDIA | contextData.key | Not supported | Key-values pairs are specified in by naming the header "contextData.product" or "contextData.color" |
| Both | cookiesEnabled | cookiesEnabled | `Y` or `N` for if the visitor supports first-party session cookies |
| Both | currencyCode | currencyCode | Revenue currency code (for example, `USD`) |
| BDIA | customerID.[customerIDType].authState | Not supported | The authenticated state of the visitor. Supported values are: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT, or '' (case insensitive). Two consecutive single quotes ('') cause the value to be omitted from the query string, which translates to 0 when the hit is made. Please note the supported authState numeric values denote the following: 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT. The customerIDType can be any alphanumeric string, but should be considered case sensitive. |
| BDIA | customerID.[customerIDType].id | Not supported | The customer ID to use. The customerIDType can be any alphanumeric string, but should be considered case sensitive. |
| BDIA | customerID.[customerIDType].isMCSeed | Not supported | Whether or not this is the seed for the Marketing Cloud Visitor ID. Supported values are: 0, 1, TRUE, FALSE, '' (case insensitive). Using 0, FALSE, or two consecutive single quotes ('') causes the value to be omitted from the query string. The customerIDType can be any alphanumeric string, but should be considered case sensitive. |
