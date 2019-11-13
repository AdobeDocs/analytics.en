---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# purchaseID

The  is used to keep an order from being counted multiple times in reporting.

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  20 bytes  | purchaseID  | Conversion > Purchases > Revenue Conversion  | ""  |

When a visitor purchases an item from your site, *`purchaseID`* is populated on the "Thank You" page at the same place the [!UICONTROL purchase] event is fired. If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. This is critical because many visitors to your site will save the "Thank You" or "Confirmation Page" for their own purposes. The *`purchaseID`* keeps purchases from being counted each time the page is viewed.

In addition to keeping the purchase data from being counted twice, the *`purchaseID`*, when used, keeps all conversion data from being double counted in reports.

**Syntax and Possible Values** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**Examples** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Configuration Settings** {#section_1808631C96674380BF9C4A6D9A2C568E}

None

**Pitfalls, Questions, and Tips** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.
