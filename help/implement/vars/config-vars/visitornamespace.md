---
title: visitorNameSpace
description: (Retired) Helped determine third-party cookie domain.
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/RHVRufQsrgYigyj0n348-xAZqrDyvpiV83G7fhpo5Q0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
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
# visitorNamespace

>[!IMPORTANT]
>
>This variable is retired. Use [`trackingServer`](trackingserver.md) instead.

In previous versions of Adobe Analytics, AppMeasurement used the `visitorNameSpace` variable to help determine the subdomain of `2o7.net` where visitor cookies are stored. Increasing privacy practices in modern browsers make third-party cookies less reliable. With the introduction of the `trackingServer` and [`trackingServerSecure`](trackingserversecure.md) variables, `visitorNameSpace` is no longer needed.

>[!TIP]
>
>Adobe recommends using first-party cookies on your site. First-party cookies do not use this variable.

## Visitor Namespace using the Adobe Analytics extension

[!UICONTROL Visitor Namespace] is a field under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Visitor Namespace] field.

Adobe advises against using this field. Use `trackingServer` and `trackingServerSecure` instead.

## s.visitorNamespace in AppMeasurement and the Analytics extension custom code editor

The `s.visitorNamespace` variable is a string that contains a unique value per organization. Old AppMeasurement libraries automatically included this unique value when downloaded from previous versions of Adobe Analytics. Current AppMeasurement libraries do not use this variable unless `trackingServer` and `trackingServerSecure` are not set.

If your organization still requires this variable, pick a value that represents your organization. You can store this value in a [solution design document](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
