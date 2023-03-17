---
title: Transaction ID data sources
description: Learn the general workflow of using transaction ID data sources.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
---
# Transaction ID data sources

Transaction ID data sources allow you to not only view online and offline data side-by-side, but tie the data together. It requires the use of the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable in your Analytics implementation.

When you send an online hit that contains a `transactionID` value, Adobe takes a "snapshot" of all variables set or persisted at that time. If a matching transaction ID uploaded through Data Sources is found, the offline and online data is tied together. 

For using transactions, the online hit with a transaction ID has to have been sent in and processed before any transaction data source data with that transaction ID is sent in. The online hit contains variables (eVars, etc.), but not events, that were on the online hit saved with the transaction ID information.

When a transaction data source hit is sent in, the transaction ID on the data source transaction hit looks up the vars, etc. (not events) that were associated with the original online hit with that transaction ID. It uses those vars on the data source transaction hit, if there was no value for a variable passed in on the data source transaction hit.

## Example

If an online hit with transaction ID 1256 is passed in and on it `evar1=blue`, `evar2=water` and `event1` are set, then transaction data for transaction ID 1256 is saved off with `evar1=blue`, `evar2=water`. No event values are saved as part of the transaction information.

Now let's assume that a data source transaction hit is then passed through the system with transaction ID 1256 and `evar1=yellow`, `evar3=mountain` and `event2` set. The system finds the saved transaction data and in the data source transaction hit sets `evar2=water` (since that is what was set on the original hit). It does not set `evar1=blue` (as it was on the original hit) because there was a value for `evar1` (yellow) already set on the data source transaction hit.  So the data source transaction hit results in having `evar1=yellow`, `evar2=water` (from the original online hit) and `evar3=mountain`. Those 3 eVar values have `event2` set - the event from the data source transaction hit.

No values from the data source transaction hit get `event1` set when the data source transaction hit is processed.

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
