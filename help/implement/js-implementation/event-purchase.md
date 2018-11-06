---
description: For the purchase event, Analytics variables are used to capture specific purchase information. The s.purchaseID variable is used to serialize (de-duplicate) the event.
keywords: Analytics Implementation
seo-description: For the purchase event, Analytics variables are used to capture specific purchase information. The s.purchaseID variable is used to serialize (de-duplicate) the event.
seo-title: Purchase events
solution: Analytics
title: Purchase events
topic: Developer and implementation
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
index: y
internal: n
snippet: y
---

# Purchase events

For the purchase event, Analytics variables are used to capture specific purchase information. The s.purchaseID variable is used to serialize (de-duplicate) the event.

The *`purchaseID`* is limited to 20 characters. The *`purchaseID`* variable serializes all events passed in the variable [!UICONTROL s.events], and overrides any serialization value for events. If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

If a purchase event is called without a *`purchaseID`*, a unique one is automatically generated based on the *`s.products`* and *`s.events`* variables. This automatically generated *`purchaseID`* is stored locally as a cookie value within the visitor's browser, and is not sent to any report suite tables. Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

When a visitor makes any purchase, the following checks are made:

* Does the *`purchaseID`* match any of the five cookie values? If so, the image request is considered a duplicate purchase. All conversion variables, including the purchase event, do not appear in reporting. 
* If *`purchaseID`* is defined, does it match any value in the report suite's back-end table? If so, the image request is considered a duplicate purchase. All conversion variables, including the purchase event, do not appear in reporting. 
* If the *`purchaseID`* is unique to both the last 5 stored values in the cookie and the report suite's *`purchaseID`* table, the image request is unique and included in reporting. For example, if five purchases are already included in the local cookie, the oldest one is overwritten.

Specific server-side code can be used to generate the unique number (alphanumeric value) embedded in the HTML source. Usually the Order ID, or similar alphanumeric value, is used for this purpose. This value should not change if the user refreshes the page. The following is a short example (note the *`purchaseID`* code in bold):

## Syntax {#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 

```

## Examples {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## Additional Notes {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* Be sure to use server-side code to generate the unique identifier for the event. Do not use a JavaScript randomization function to generate a number, which generates unique numbers each time the page is loaded (each [!UICONTROL instance]/ [!UICONTROL pageview] counts). 

* The unique identifiers are applicable to all users across all sessions. Therefore, ensure the identifier is unique across users and sessions. For instance, if the Order ID repeats after 30 days, append the date of the order to make the [!UICONTROL Order ID] sufficiently unique. 
* The serialization value may be alphanumeric values up to 20 characters in length. This is identical to the limitations of [!UICONTROL s.purchaseID] (replace s. with s_ for G Code). 
* The [!UICONTROL s.purchaseID] variable serializes all events passed in the variable [!UICONTROL s.events], and overrides any serialization value for events. Do not use [!UICONTROL Event serialization] for any events if the [!UICONTROL s.purchaseID] variable is used on the current page (replace s. with s_ for G Code).

