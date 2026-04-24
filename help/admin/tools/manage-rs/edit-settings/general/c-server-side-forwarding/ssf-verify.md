---
description: To verify that Server-side forwarding is properly enabled, you'll need to inspect the HTTP response from the Analytics tracking request. These instructions illustrate which indicators must be present to ensure server-side forwarding is properly enabled.
solution: Analytics
title: How to verify your server-side forwarding implementation
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# How to verify your server-side forwarding implementation

To verify that Server-side forwarding is properly enabled, you'll need to inspect the HTTP response from the Analytics tracking request. This can be done using a browser's developer tools or by using a proxying tool such as the Charles Web Debugger. The following instructions illustrate which indicators must be present to ensure server-side forwarding is properly enabled.

To check the status of server-side forwarding:

1. Load a test page that contains updated AppMeasurement code.
1. In your browser's debugging tools or using your proxy software, inspect the HTTP response from Analytics' tracking request (you can easily filter this by selecting any path containing "b/ss").
1. Inspect the HTTP response. If the response contains Audience Manager data (as illustrated below), then server-side forwarding is working.

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. Please ensure that the Identity Service is properly deployed, you've deployed the App Measurement module, that the applicable report suite has been mapped to the correct organization ID, and that server-side forwarding has been enabled in Analytics Admin Tools.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
