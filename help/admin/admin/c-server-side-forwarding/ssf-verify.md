---
description: To verify that Server-side forwarding is properly enabled, you'll need to inspect the HTTP response from the Analytics tracking request. This can be done using a browser's developer tools or by using a proxying tool such as the Charles Web Debugger. The following instructions illustrate what indicators must be present to ensure server-side forwarding is properly enabled.
solution: Analytics
title: How to verify your server-side forwarding implementation
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
---
# How to verify your server-side forwarding implementation

To verify that Server-side forwarding is properly enabled, you'll need to inspect the HTTP response from the Analytics tracking request. This can be done using a browser's developer tools or by using a proxying tool such as the Charles Web Debugger. The following instructions illustrate what indicators must be present to ensure server-side forwarding is properly enabled.

To check the status of server-side forwarding:

1. Load a test page that contains updated AppMeasurement code.
1. In your browser's debugging tools or using your proxy software, inspect the HTTP response from Analytics' tracking request (you can easily filter this by selecting any path containing "b/ss").
1. Inspect the HTTP response. If the response contains Audience Manager data (as illustrated below), then server-side forwarding is working.

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. Please ensure that the Identity Service is properly deployed, you've deployed the App Measurement module, that the applicable report suite has been mapped to the correct organization ID, and that server-side forwarding has been enabled in the Analytics admin console.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
