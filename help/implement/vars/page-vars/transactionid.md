---
title: transactionID
description: Use this variable to link online and offline data together.
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
---
# transactionID

The `transactionID` variable uniquely identifies a transaction so the hit can tie to data uploaded through Data Sources. This variable is valuable in cases where you want to use data from other channels and link it to data collected with AppMeasurement.

>[!NOTE]
>
>Make sure that [!UICONTROL Transaction ID Storage] is enabled in a report suite before using this variable. See [General Account Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) in the Admin user guide for more information.

When you set `transactionID` on a hit, Adobe takes a "snapshot" of all Analytics variables set or persisted at that point in time. Data uploaded through Data Sources with a matching transaction ID is permanently tied to those variable values.

By default, Adobe remembers all transaction ID values (linked and unlinked) for up to 90 days. If your offline interaction process is longer than 90 days, contact Customer Care to have this limit extended.

## Transaction ID using the Web SDK

Transaction ID is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM field `commerce.order.transactionID`.

## Transaction ID using the Adobe Analytics extension

You can set transaction ID either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Transaction ID] section.

You can set transaction ID to any string value, including data elements.

## s.transactionID in AppMeasurement and the Analytics extension custom code editor

The `s.transactionID` variable is a string containing a unique identifier for a transaction. Valid values include alphanumeric characters up to 100 bytes in length. Its default value is an empty string.

```js
s.transactionID = "ABC123";
```

If you have more than one transaction ID for a hit, you can delimit each with a comma. Multiple transaction IDs are still subject to the 100-byte limit.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>If you integrate multiple offline channels using this variable, make sure that different channels don't overlap transaction IDs. For example, if you have a call center transaction ID value of `1234` and a sales lead transaction ID value of `1234`, they can conflict and cause unexpected results. Make sure that transaction IDs contain unique formats per offline channel and differentiate them if necessary. For example, set your call center transaction ID to `call_1234` and your sales lead transaction ID `lead_1234` in both Data Sources and AppMeasurement.
