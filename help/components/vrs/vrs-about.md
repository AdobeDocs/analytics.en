---
description: Virtual report suites segment your Adobe Analytics data so you can control access to each segment.
title: Virtual report suites overview
feature: VRS
exl-id: 45d18d14-d95a-42fe-b00a-cfce5f936e37
TQID: https://experienceleague.adobe.com/gEs8c9pIUGbbPx7DBAwFhSvT-C6W2vfosgMkrO-32ic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Virtual report suites overview

Virtual report suites segment your Adobe Analytics data so you can control access to each segment.

Many customers have data flowing into a global report suite, but also have data flowing into smaller report suites. They set a variable to multiple report suites, and send their data to more than one report suite. This is referred to as *multi-suite tagging*, or *base/parent report suites*.

For example, all data might be collected in one report suite, but then you can set up secondary report suites so other people in your company have access to part of the data, but not all of it. Data might be divided by region. You might have different websites for different countries. Other examples might be specific brands that belong to a larger company, but that each have their own marketing teams.

A *virtual report suite* allows you to reproduce this branching concept, using segments instead of multiple report suites. Data is sent to one report suite, then is divided according to segments. Using the multiple brands example, you might set a prop for the brand that an item belongs to. Using segments, you can report on the items assigned to each prop. Each of these segments becomes its own view, effectively creating a new report suite. You don't send data specifically to that segment, only to the global report suite, but it functions in your reports as if it were a different report suite.

A virtual report suite inherits most of the service levels of the base report suite, such as eVar settings, Processing Rules, Classifications, etc. The following settings are NOT inherited:

* Report suite ID (RSID)
* Report suite name
* Permission groups (virtual report suites can be assigned to their own permission groups)

## Benefits of virtual report suites {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Customers pay for secondary server calls, so eliminating these calls can result in significant savings. A virtual report suite is also completely retroactive. If the global report suite already contains data, the relevant data is automatically included in a new virtual report suite. A new secondary report suite would only begin collecting data after it is created, so it would not include any historical data. When you implement Analytics, you only need to send data to one report suite, rather than having to create implementations for the global report suite and each secondary report suite.

Virtual report suites help:

* Simplify implementation by allowing you to use a single Report Suite ID (RSID) across all sites/domains. Having all data in a single report suite enables customer analytics as we move toward the next generation of Adobe Analytics.
* Business users in your organization always see only the data segments that are relevant to them.
* Improve security by allowing Admin users to control data access more easily and more granularly after implementation.
* People metric
* A single-customer view of data (in the future)
* The ability to create unlimited virtual report suites to segment out data

## Limitations of virtual report suites {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Virtual report suites have the following limitations:

* Any limitations of segments also apply to virtual report suites

  A virtual report suite is nothing more than a segment applied to a report suite. Because each report suite has its own Data Warehouse and its own Data Feed, using multiple report suites results in some benefits that segments do not provide.
* Real-time report
* Settings and variable names cannot be customized like in a full report suite

## Virtual report suites vs. multi-suite tagging {#section_317E4D21CCD74BC38166D2F57D214F78}

| Capability  | Virtual report suite  | Multi-suite tagging  |
|--- |--- |--- |
| Offers real-time or "Current Data" reporting| No | Yes |
| Works in all Analytics Tools (Analysis Workspace, Report Builder, etc.)|Yes. **Note:** You can edit and identify them as virtual report suites only in [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Virtual report suites]. However, you can select them in report suite drop-downs in the other tools.<p>**Important**: Virtual report suites with report time processing and variable customization are not currently supported in Adobe Report Builder. | Yes |
| Can upload data to it (via classifications, data feeds, etc.) | No | Yes |
| Supports creation of DL Reports, bookmarks, dashboards, targets, alerts, segments, calculated metrics... | Yes | Yes |
| Can be individually added to Permissions Groups | Yes | Yes |
| Can use Admin functions to modify individual settings on this report suite (Admin > Report Suites) | No (Settings are inherited from parent) | Yes |

{style="table-layout:auto"}

## Combine virtual report suites and multi-suite Tagging {#section_026FA3FCD7314DD18220E73EC5702AFF}

In some cases, there are benefits to using both virtual report suites and multi-suite tagging.

For example, a retailer might use a report suite for each brand, and virtual report suites for each brand to break data out by region. Similarly, an athletic organization might use a report suite for each team, then virtual report suites to divide fans in the team's region from those outside the region.
