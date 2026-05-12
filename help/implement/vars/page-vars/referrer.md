---
title: referrer
description: Override the automatically collected referrer for a hit.
feature: Appmeasurement Implementation
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YsYfgjFNDiJoQbvPU-XoB6bQt2IAriP1qmkOqc2lFDk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# referrer

The `referrer` variable overrides the automatically collected referrer in reports. This variable is helpful in situations where the referrer might be lost, such as during redirects or temporarily forwarding the visitor to a payment processor. This variable helps populate the 'Referrer' and 'Referring Domain' dimensions.

## Referrer using the Web SDK

Referrer is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webReferrer.URL`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.referrer`

The Web SDK automatically includes `web.webReferrer.URL` on every event sent, if available.

## Referrer using the Adobe Analytics extension

You can set referrer either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Referrer] section.

You can set referrer to any string value, including data elements.

## s.referrer in AppMeasurement and the Analytics extension custom code editor

The `s.referrer` variable is a string containing the URL of the previous page. This variable can store a maximum of 255 bytes; values larger than 255 bytes are truncated. AppMeasurement automatically sets this variable to `document.referrer`; you do not need to set this variable unless you want to override the automatically collected value.

```js
s.referrer = "https://example.com";
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Avoid setting this variable to non-URL values. Do not strip the URL's protocol.

## Example

Many organizations deal with implementations around redirects. You can use the [`Util.getQueryParam()`](../functions/util-getqueryparam.md) utility to obtain referrer from the URL if your site accommodates it. Make sure that you URL encode any values included in the query string.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
