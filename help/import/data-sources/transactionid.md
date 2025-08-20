---
title: Transaction ID data sources
description: Store values from an online hit to enrich offline hits using a shared transaction ID.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
---
# Transaction ID data sources

Transaction ID data sources are a variation of summary data sources that let you apply values saved from an online hit to offline rows that share the same transactionID. This approach is useful when you capture a transaction online but receive details later from another system. Primary examples include product returns, booking cancellations, or outcomes from call center interactions.

>[!NOTE]
>
>Before using transaction ID data sources, you must first enable it in [General Account Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) for the desired report suite.

## How it works

The concept of transaction IDs require two parts:

* **Online hit**: Any full Analytics hit sent to a report suite (AppMeasurement, Web SDK, API, etc). On this hit, you set the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) implementation variable.
* **Offline hit**: A row uploaded through data sources that contains the same transaction ID as an online hit.

When you send an online hit that contains a transaction ID, Adobe takes a "snapshot" of the following dimensions that were set or persisted at that point:

* [Category](/help/components/dimensions/category.md)
* [eVar 1-250](/help/components/dimensions/evar.md)
* [Marketing channel](/help/components/dimensions/marketing-channel.md)
* [Marketing channel detail](/help/components/dimensions/marketing-detail.md)
* [Product](/help/components/dimensions/product.md)
* [Tracking code](/help/components/dimensions/tracking-code.md)
* [Zip code](/help/components/dimensions/zip-code.md)

When you upload an offline hit through data sources that contains a matching transaction ID, any available dimensions within the "snapshot" are appended to the data source row. If a given dimension is present in both the online and offline hit, the offline hit value is used.

>[!IMPORTANT]
>
>The concept of transaction ID data sources only help fill data source rows. They do not impact or change the online hit.

## Transaction ID data source considerations

Transaction ID data sources have the following properties:

* The online data must be collected and processed first. If a transaction ID data source is uploaded before a report suite processes a hit matching that transaction ID, the data is treated like a summary data source.
* Transaction IDs collected from online hits expire after 25 months.
* Data sources uploaded with an expired transaction ID are treated similarly to data uploaded without a transaction ID.
* If you set the same transaction ID on multiple online hits, only the first occurrence's "snapshot" is used. Subsequent duplicate transaction ID online hits are processed as if they did not have a transaction ID.
* Once you populate a given `transactionID`, value it is considered immutable until that transaction ID expires. 
* If you set the same transaction ID on multiple data source rows, any available dimensions from the online hit are appended to the offline hit. Offline hits for the same transaction ID do not know anything about each other; data is not passed between offline hits.

For example:

1. You send in a page view from AppMeasurement where:
   * `eVar1` equals `blue`
   * `eVar2` equals `water`
   * `events` equals `event1`
   * `transactionID` equals `1256`
2. After the hit is collected and processed, you upload a transaction ID data source where:
   * `eVar1` equals `yellow`
   * `eVar3` equals `bird`
   * `events` equals `event2`
   * `transactionID` equals `1256`
3. Once the data sources hit is processed, you view a report in workspace. The data would show the following:
   * `eVar1` equals `yellow`
   * `eVar2` equals `water`
   * `eVar3` equals `bird`
   * `events` equals `event2`

The eVar1 value `blue` and the `event1` metric are not present in reporting, since the transaction ID hit overwrote those respective values.
