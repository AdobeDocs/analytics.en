---
title: trackingServerSecure
description: The domain used to send data to Adobe over HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
---
# trackingServerSecure

The `trackingServerSecure` variable determines the domain that AppMeasurement uses to send data to Adobe over HTTPS. If this variable is not defined correctly, your implementation can experience data loss.

Before the [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/en/docs/id-service/using/home), this variable also determined where third-party cookies were set. Adobe strongly recommends using the ID service in all implementations where possible.

## Edge domain using the Web SDK extension

The Web SDK uses [!UICONTROL Edge domain] to handle both Tracking Server and Secure Tracking Server. You can set the desired [!UICONTROL Edge domain] value when configuring the Web SDK extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Select the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then select the **[!UICONTROL Configure]** button under [!UICONTROL Adobe Experience Platform Web SDK].
1. Set the desired **[!UICONTROL Edge domain]** text field.

See [Configure the Adobe Experience Platform Web SDK extension](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) in the Web SDK documentation for more information.

>[!TIP]
>
>If your organization moves to the Web SDK from an AppMeasurement or Analytics extension implementation, this field can use the same value contained in `trackingServerSecure` (or `trackingServer`).

## Edge domain manually implementing the Web SDK

Configure the SDK using [`edgeDomain`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgedomain). The field is a string that determines the domain to send data to.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## SSL Tracking Server using the Adobe Analytics extension

[!UICONTROL SSL Tracking Server] is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Select the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then select the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL General] accordion, which reveals the [!UICONTROL SSL Tracking Server] field.

If this field is left blank, it defaults to the value in [!UICONTROL Tracking Server]. If both [!UICONTROL SSL Tracking Server] and [!UICONTROL Tracking Server] are blank, it defaults to `[rsid].data.adobedc.net`.

## s.trackingServerSecure in AppMeasurement and the Analytics extension custom code editor

The `s.trackingServerSecure` variable is a string that contains the domain to send data to Adobe. It is domain only; omit protocol, path, port, and slashes. If this variable is blank, it uses the value in the `s.trackingServer` variable. If both `s.trackingServerSecure` and `s.trackingServer` are blank, it defaults to `[rsid].2o7.net`.

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## Considerations determining the value for `trackingServerSecure`

The value that you use for `trackingServerSecure` (or `edgeDomain`) depends on several factors:

* Your participation in the [Adobe-managed certificate program](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert)
* If you have the [Adobe Experience Cloud Identity service](https://experienceleague.adobe.com/en/docs/id-service/using/home) implemented and correctly set up

**If your organization participates in the Adobe-managed certificate program**, set the value to the first-party domain that was selected when setting up the certificate. Typically this value is a subdomain owned by your organization. For example, `data.example.com`. CNAME records in your organization redirect that data to Adobe.

**If not participating in the certificate program**, set the value to a subdomain of `data.adobedc.net`. Adobe recommends using your organization's company ID for consistency. For example, `example.data.adobedc.net`. Use the following steps to determine your company ID:
  
1. Log in to [experience.adobe.com](https://experience.adobe.com) using your Adobe ID credentials.
1. Anywhere in the Experience Cloud interface, press `[Cmd]` + `[I]` (iOS) or `[Ctrl]` + `[I]` (Windows).
1. A **[!UICONTROL User data debugger]** appears. Select the **[!UICONTROL Assigned orgs]** tab.
1. Expand the desired IMS organization.
1. Locate the **[!UICONTROL Tenant]** field. This value is the recommended subdomain of `data.adobedc.net` to use.

>[!NOTE]
>
>Do not use any subdomains deeper than `example.data.adobedc.net`. For example, `custom.example.data.adobedc.net` is not a valid tracking server.

Older implementations might have values like `sc.omtrdc.net` or `2o7.net`. These were primarily used in previous versions of Adobe Analytics and are still valid.

Adobe highly recommends maintaining this information in a [solution design document](../../prepare/solution-design.md) for consistency across your organization.

## Ramifications for not using the Visitor ID service

Adobe strongly recommends using the [Adobe Experience Cloud Identity service](https://experienceleague.adobe.com/en/docs/id-service/using/home) in all implementations. The ID service can be implemented in several different ways:

* Manual AppMeasurement implementations use `VisitorAPI.js` and call the `getInstance` method. See [Implement the Experience Cloud Identity Service for Analytics](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/setup-analytics) for more information.
* Implementations using the Adobe Analytics tag extension use the [Adobe Experience Cloud ID service tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview). Once added, no additional configuration is required.
* Implementations using any form of the Web SDK (`alloy.js` or the Web SDK tag extension) already have the ID service baked in natively. No configuration is required beyond setting the `edgeDomain` value.

**If your implementation does not use the identity service**, consider the following impacts to your implementation:

* If not using the identity service, `trackingServerSecure` determines cookie location. Setting this variable to a third-party domain forces AppMeasurement to use a fallback cookie, as most modern browsers reject third-party cookies.
* Internal link tracking and Activity Map might be less reliable.
