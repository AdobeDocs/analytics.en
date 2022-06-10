---
description: Use transaction ID in data sources to link online and offline data together.
title: Transaction ID and visitor profiles
topic-fix: Developer and implementation
feature: Data Sources
exl-id: ca5f9e8d-853f-4444-a8fd-a20933ef33d7
---
# Transaction ID and visitor profiles

This section contains important information regarding the data from the visitor profile that is used when uploading data using a transaction ID.

## Transaction ID {#section_B248FA93ECC84F6290D237EB83618070}

When a transaction ID is recorded, a "snapshot" of the current visitor profile is saved and associated with the transaction ID. This "snapshot" contains all variable values that are currently set for the visitor, including persisting variables (such as eVars and campaigns). Values in this snapshot receive attribution for success events, purchase events, and revenue later uploaded using this same transaction ID.

After the visitor profile "snapshot" is created, it is not updated when the current visitor profile changes (due to online behavior), it is updated only with data that is uploaded using transaction ID data sources. If you set the same transaction ID value on multiple pages during the same visit, the data source upload that takes place later will be tied to the "snapshot" that was created the first time the ID was set.

**Multiple Uploads**

Multiple rows of data can be uploaded to the same transaction ID throughout the transaction ID expiration window (see below).

**Variable Expiration**

Variable expiration is not considered for the purposes of transaction IDs, because the associated visitor profile data is intended to reflect the visitor state at the time of the transaction. For example, if eVar1 is configured to expire after visit, the value in the visitor profile "snapshot" receives credit even if the value has expired or has been replaced in the current visitor profile when transaction ID data is uploaded.

**Products**

Product information (from `s.products`) is not contained in the visitor profile "snapshot," so you must upload any associated product data in the data source file along with the transaction ID. Note that you can specify only one product per row, so you might need to upload multiple rows with the same transaction ID to include all products.

**Uploaded eVar Persistence**

eVars uploaded using transaction ID data sources are added to the visitor profile "snapshot", they are not added to the current visitor profile or virtual cookie. This means that online behavior that happens after the upload is not credited to uploaded eVars, since these values are not part of the current visitor profile.

**Transaction ID Expiration Window**

The visitor profile "snapshot" associated with a transaction ID is eligible for deletion after 90 days, though the actual deletion schedule varies. If required, you can contact Adobe Customer Care to have the expiration window extended. If a row is uploaded after the transaction ID expiration window, the data in the row is recorded, but none of the data in the visitor profile "snapshot" will be credited if the profile has been deleted.

## Breakdowns and Segmentation Using Transaction IDs {#section_A4D39291200A42C496122FDB9EF6EF68}

eVars uploaded using data sources can be used to breakdown eVars that are contained in the "snapshot" of the visitor profile. Since this data is separate from the current visitor profile, you cannot breakdown by other eVars that might have been set before or after the transaction ID was set but are not part of the "snapshot."

There are a few ways to view associated visitor data that might not be available in a breakdown. In data warehouse reports, you can view transaction ID data with a visitor ID that matches the other hits from the visitor. While these transaction ID rows are excluded when counting visits/visitors per day, they are used in calculating most metrics and in segments.

As a result, you can build a segment of visitors who perform some offline event that was uploaded using transaction ID data sources. That will return everything the visitor did before and after the transaction ID event.

Likewise, visitor participation allows you to see how transaction ID props and eVars preceded an online event, or how online props and eVars preceded a transaction ID event.
