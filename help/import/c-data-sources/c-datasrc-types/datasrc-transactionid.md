---
title: Transaction ID data sources
description: Learn the general workflow of using transaction ID data sources.
---

# Transaction ID data sources

Transaction ID data sources allow you to not only view online and offline data side-by-side, but tie the data together. It requires the use of the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable in your Analytics implementation.

When you send an online hit that contains a `transactionID` value, Adobe takes a "snapshot" of all variables set or persisted at that time. If a matching transaction ID uploaded through Data Sources is found, the offline and online data is tied together. It does not matter which source of data is seen first.

## Overall workflow of Transaction ID data sources

Use the following generic workflow to start using Transaction ID data sources:

1. Create a data source ('Generic' category and 'Generic Data Source (Transaction ID)' type).
1. Follow the data feed setup wizard to get an FTP location to upload data and download a data sources template file.
1. Update your implementation to include the `transactionID` variable.
1. Upload a data sources file to the FTP site with a `.fin` file.
