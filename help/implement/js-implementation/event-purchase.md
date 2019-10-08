---
description: For the purchase event, Analytics variables are used to capture specific purchase information. The s.purchaseID variable is used to serialize (de-duplicate) the event.
keywords: Analytics Implementation
seo-description: For the purchase event, Analytics variables are used to capture specific purchase information. The s.purchaseID variable is used to serialize (de-duplicate) the event.
seo-title: Purchase events
solution: Analytics
title: Purchase events
topic: Developer and implementation
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
---

# Purchase events

For the purchase event, Analytics variables are used to capture specific purchase information. The `s.purchaseID` variable is used to serialize (de-duplicate) the event.

If a purchase event is called without a `purchaseID`, a unique one is automatically generated based on the `s.products` and `s.events` variables. This automatically generated purchase ID is stored locally as a cookie value within the visitor's browser, and is not sent to Adobe. Manually defined purchase IDs on the other hand are sent to Adobe. The last five purchases made by a visitor (with or without purchase ID) are stored in the local cookie.

When a visitor makes any purchase, the following checks are made:

* Does the purchase ID match any of the five cookie values? If so, the image request is considered a duplicate purchase. All conversion variables, including the purchase event, do not appear in reporting.
* If `s.purchaseID` is defined, does it match any value already collected in the report suite? If so, the image request is considered a duplicate purchase. All conversion variables, including the purchase event, do not appear in reporting.

Specific server-side code can be used to generate the unique number (alphanumeric value) embedded in the HTML source. Usually the Order ID, or similar alphanumeric value, is used for this purpose. This value should not change if the user refreshes the page.

## Syntax

```js
s.purchaseID="12345678";
```

## Examples

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## Additional Notes

* Do not use a JavaScript randomization function to generate a number, which generates unique numbers each time the page is loaded. Adobe recommends using a data layer to store a given purchase ID.
* The unique identifiers are applicable to all users across all sessions. Make sure all purchase ID's are truly unique.
* Valid values are alphanumeric values up to 20 characters in length.
* The `s.purchaseID` variable serializes all events passed in the `s.events` variable, and overrides any serialization value for events. Do not use [!UICONTROL Event serialization] for any events if the `s.purchaseID` variable is used on the current page.
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.
