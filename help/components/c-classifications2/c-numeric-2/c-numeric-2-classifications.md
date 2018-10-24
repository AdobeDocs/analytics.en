---
description: Numeric 2 classifications provide custom, flexible metrics that you can import into the Adobe Marketing Cloud via the importer.
seo-description: Numeric 2 classifications provide custom, flexible metrics that you can import into the Adobe Marketing Cloud via the importer.
seo-title: Numeric 2 classifications overview
solution: Analytics
subtopic: Classifications
title: Numeric 2 classifications overview
topic: Admin tools
uuid: d1bb73fb-1f6f-4223-ac90-a1e69ac97abe
index: y
internal: n
snippet: y
---

# Numeric 2 classifications overview

Numeric 2 classifications provide custom, flexible metrics that you can import into the Adobe Marketing Cloud via the importer.

>[!NOTE]
>
>In the May 10, 2018, Analytics Maintenance release, Adobe started to limit the functionality of date-enabled and numeric classifications. These classification types were removed from the Admin and Classification Importer interfaces. No new date-enabled and numeric classifications can be added. Existing classifications can still be managed (uploaded to, deleted) through the standard classification workflow, and will continue to be available in reporting.

A common way to use numeric 2 classifications is for numeric variables that change over time for different items, such as the cost of goods sold. In admin, you can create classifications on the [!UICONTROL Conversion Classification] page, and then use the importer to export a file, make edits, and then import the file back in to Adobe. After importing the data, you can use the numeric classifications when creating calculated metrics.

>[!IMPORTANT]
>
>Analysis Workspace and Ad Hoc Analysis do not support Numeric 2 classifications.

The following table illustrates the differences among classification types: 

|  FEATURE  | TEXT  | NUMERIC 1.0  | NUMERIC 2.0  |
|---|---|---|---|
|  Displays as a report  | Yes  | No  | No  |
|  Can be used as a metric  | No  | Yes  | Yes  |
|  Can be created on the base report  | Yes  | No  | Yes  |
|  Calculated based on events  | No  | Yes  | Yes  |
|  Multiple rows per key  | No  | No  | Yes  |
|  Can have different values for different time periods  | No  | No  | Yes  |
|  Can be used in calculated metrics  | No  | Yes  | Yes  |

