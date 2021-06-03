---
title: Transaction ID data sources
description: Learn the general workflow of using transaction ID data sources.
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
---
# Transaction ID data sources

Transaction ID data sources allow you to not only view online and offline data side-by-side, but tie the data together. It requires the use of the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable in your Analytics implementation.

When you send an online hit that contains a `transactionID` value, Adobe takes a "snapshot" of all variables set or persisted at that time. If a matching transaction ID uploaded through Data Sources is found, the offline and online data is tied together. It does not matter which source of data is seen first.

## Overall workflow of Transaction ID data sources

Use the following generic workflow to start using Transaction ID data sources:

1. Create a data source ('Generic' category and 'Generic Data Source (Transaction ID)' type).
1. Follow the data source setup wizard to get an FTP location to upload data and download a data sources template file.
1. Update your implementation to include the `transactionID` variable.
1. Upload a data sources file to the FTP site with a `.fin` file.

## Example upload file and implementation code

If you uploaded the following data sources file, and implemented the following code on your site, you would see data linked in reporting. The data sources file uses eVar1 and event1, while the online implementation uses eVar2 and event2. Since the transaction ID matches, you could see event2 data for eVar1, and event1 data for eVar2.

### Example file

Download the template, update the values, then upload it to the data sources FTP location:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1`| `1234` |

### Example implementation code

For a more detailed explanation on transaction ID, see [`transactionID`](/help/implement/vars/page-vars/transactionid.md) In the Implement user guide.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
