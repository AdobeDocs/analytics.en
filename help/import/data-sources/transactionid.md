---
title: Transaction ID data sources
description: Learn the general workflow of using transaction ID data sources.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
---
# Transaction ID data sources

Transaction ID data sources allow you to not only view online and offline data side-by-side, but tie the data together. It requires the use of the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable in your Analytics implementation.

Before using transaction ID data sources, you must first enable it in [General Account Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

When you send an online hit that contains a `transactionID` value, Adobe takes a "snapshot" of all variables set or persisted at that time. If a matching transaction ID uploaded through data sources is found, the offline and online data is tied together.

Transaction ID data sources have the following properties:

* The online data must be collected and processed first. If a transaction ID data source is uploaded before a report suite processes a hit matching that transaction ID, the data is not linked.
* If the same variable is included in both the online hit and the transaction ID data source, the value from the transaction ID data source is used.
* If a variable is included in an online hit and not a matching transaction ID data source hit, the online hit variable is unaltered.

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

Note that the eVar1 value `blue` and the `event1` metric are not present in reporting, since the transaction ID hit overwrote those respective values.
