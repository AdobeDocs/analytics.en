---
title: writeSecureCookies
description: Allows AppMeasurement to set cookies with the Secure attribute.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
---
# writeSecureCookies

The `writeSecureCookies` variable allows AppMeasurement to set [Secure cookies](https://en.wikipedia.org/wiki/Secure_cookie) for Analytics. This setting applies to both visitor ID cookies set by AppMeasurement, and cookies you set using the `Util.CookieWrite()` method. It requires AppMeasurement 2.18.0 or higher.

`writeSecureCookies` applies only to cookies set by AppMeasurement JavaScript (`s_fid`, `s_cc` and `s_sq`). Cookies set by `https` response (`s_vi` and `s_ecid`) can be set to 'secure' by contacting Adobe Customer Care.

Learn more about Analytics cookies [here](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!WARNING]
>
>If you enable the `writeSecureCookies` variable, make sure that all content on your site is served securely over HTTPS. Data collection does not work properly if this variable is enabled and you have insecure content on your page.

## Use secure cookies with the Web SDK

If your site uses HTTPS protocol, the Secure attribute is set for all cookies that the Web SDK sets.

## Write Secure Cookies using the Adobe Analytics extension

[!UICONTROL Write secure cookies] is a checkbox under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Cookies] accordion, which reveals the [!UICONTROL Write secure cookies] checkbox.

## s.writeSecureCookies in AppMeasurement and the Analytics extension custom code editor

The `s.writeSecureCookies` variable is a boolean that determines if AppMeasurement sets the Secure attribute when creating a cookie. Its default value is `false`. Set this variable to `true` if all content on your site is secure and you would like cookies set by AppMeasurement to have the Secure attribute.

```js
s.writeSecureCookies = true;
```
