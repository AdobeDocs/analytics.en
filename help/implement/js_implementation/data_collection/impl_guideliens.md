---
description: Following these guidelines results in using the same cookie domains, which lets visits be tracked between various types of implementations.
keywords: Analytics Implementation
seo-description: Following these guidelines results in using the same cookie domains, which lets visits be tracked between various types of implementations.
seo-title: Implementation guidelines
solution: Analytics
title: Implementation guidelines
topic: Developer and implementation
uuid: 8c9640cc-d30c-4621-b1d0-34ea12d19e1f
index: y
internal: n
snippet: y
---

# Implementation guidelines

Following these guidelines results in using the same cookie domains, which lets visits be tracked between various types of implementations.

* ** RSID:** The [!UICONTROL report suite ID] 

* ** VNS:** Visitor name space, the subdomain of [!DNL 2o7.net] or [!DNL omtrdc.net] used to store the [!UICONTROL visitor ID] cookie 

* ** COOKIEDOMAIN:** Your VNS + trackingServer. Depending on your data center and RDC configuration, these can greatly vary. See [Correctly populate the trackingServer and trackingServerSecure variable](https://marketing.adobe.com/resources/kb/en_US/analytics/kb/determining-data-center.html) or [contact Client Care](contact_and_legal.md#concept_34A1CA16F2244D42930BB77846A5ABBB) if you are unsure about you data collection domain.

**Javascript:**

```js
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
 
<b>Hardcoded image request:</b>
```

**AppMeasurement:**

```js
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
 
<b>Hardcoded image request:</b>
```

**Hardcoded image request:**

```
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 
<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! --> 

```

If using a first-party cookie implementation, [!DNL VNS.COOKIEDOMAIN.net] can be replaced with the first-party cookie domain used. For example, first-party cookies on [!DNL adobe.com] would be replaced with something similar to [!DNL metrics.adobe.com]. 
