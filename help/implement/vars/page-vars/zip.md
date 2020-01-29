---
title: zip
description: Manually populate the 'Zip Code' dimension if report suite settings allow.
---

# zip

The `zip` variable allows you to manually populate the 'Zip Code' dimension if the [!UICONTROL Zip Option] in report suite settings allows it. In previous versions of Adobe Analytics, this variable could only be manually set, typically when entering shipping information on a retail site. Improvements to Adobe Analytics allows this variable to be automatically set using geo-location data. This variable does not persist beyond the hit it is set.

> [!IMPORTANT] Make sure the [!UICONTROL Zip Option] in report suite settings is set to the desired value. You cannot use this variable if [!UICONTROL geo zip] is always used. See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

## Zip in Adobe Experience Platform Launch

You can set Zip Code either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Zip] section.

You can set Zip Code to any string value, including data elements.

## s.zip in AppMeasurement and Launch custom code editor

The `s.zip` variable is a string that typically contains a Zip Code, but can contain any desired value up to 50 bytes in length.

```js
s.zip = "84043";
```
