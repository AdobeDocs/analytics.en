---
title: writeSecureCookies
description: Allows AppMeasurement to set cookies with the Secure attribute.
---

# writeSecureCookies

The `writeSecureCookies` variable allows AppMeasurement to set [Secure cookies](https://en.wikipedia.org/wiki/Secure_cookie) for Analytics. This setting applies to both visitor ID cookies set by AppMeasurement, and cookies you set using the `Util.CookieWrite()` method. It requires AppMeasurement 2.18.0 or higher.

>[!IMPORTANT]
>
>If you enable the `writeSecureCookies` variable, make sure that all content on your site is served securely over HTTPS. AppMeasurement does not work if this variable is enabled and you have insecure content on your page.

## Write Secure Cookies in Adobe Experience Platform Launch

[!UICONTROL Write secure cookies] is a checkbox under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Write secure cookies] checkbox.

## s.writeSecureCookies in AppMeasurement and Launch custom code editor

The `s.writeSecureCookies` variable is a boolean that determines if AppMeasurement sets the Secure attribute when creating a cookie. Its default value is `false`. Set this variable to `true` if all content on your site is secure and you would like cookies set by AppMeasurement to have the Secure attribute.

```js
s.writeSecureCookies = true;
```
