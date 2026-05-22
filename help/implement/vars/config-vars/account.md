---
title: account
description: (Retired) Determine the report suite where data is sent to.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/ICQkj-Eo29jve35GewuZUKOPIr01g-WjhbyztrAO0jI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
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
---
# account

>[!IMPORTANT]
>
>This variable is retired. Use the [`s.sa()`](../functions/sa-method.md) function if your implementation requires that you modify the report suite destination.

In previous versions of Adobe Analytics, the `account` variable determined the report suite you want to send data to. A report suite ID is required to send data to Adobe Analytics.

* If you use the Web SDK, report suites are in the Adobe Analytics service settings within the Datastream that the Web SDK sends data to.
* If you use the Adobe Analytics extension, report suites reside under the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension.
* If you use the [`s_gi()`](../functions/s-gi.md) function to instantiate an Analytics tracking object, the report suite ID(s) already exist as a required argument in the function.
