---
title: zip
description: Manually populate the 'Zip Code' dimension if report suite settings allow.
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
---
# zip

The `zip` variable allows you to manually populate the 'Zip Code' dimension if the [!UICONTROL Zip Option] in report suite settings allows it. In previous versions of Adobe Analytics, this variable could only be manually set, typically when entering shipping information on a retail site. Improvements to Adobe Analytics allows this variable to be automatically set using geo-location data. This variable does not persist beyond the hit it is set.

>[!IMPORTANT]
>
>Make sure the [!UICONTROL Zip Option] in report suite settings is set to the desired value. You cannot use this variable if [!UICONTROL Geo zip] is always used. See [General Account Settings](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) in the Admin user guide for more information.

## Zip code using the Web SDK

Zip code is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Zip code using the Adobe Analytics extension

You can set Zip code either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Zip] section.

You can set Zip Code to any string value, including data elements.

## s.zip in AppMeasurement and the Analytics extension custom code editor

The `s.zip` variable is a string that typically contains a Zip Code, but can contain any desired value up to 50 bytes in length.

```js
s.zip = "84043";
```
