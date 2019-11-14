---
description: Following these guidelines results in using the same cookie domains, which lets visits be tracked between various types of implementations.
keywords: Analytics Implementation
solution: Analytics
title: Implementation guidelines
topic: Developer and implementation
uuid: 2917f4af-19bd-4666-ae4b-056e7e33f642
---

# Implementation guidelines

Following these guidelines results in using the same cookie domains, which lets visits be tracked between various types of implementations.

* **RSID:** The [!UICONTROL report suite ID]
* **VNS:** Visitor name space, the subdomain of [!DNL 2o7.net] or [!DNL omtrdc.net] used to store the [!UICONTROL visitor ID] cookie
* **COOKIEDOMAIN:** Your VNS + trackingServer. Depending on your data center and RDC configuration, these can greatly vary. [Contact Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) if you are unsure about you data collection domain.

## Javascript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## Hardcoded image request

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->

```

If using a first-party cookie implementation, `VNS.COOKIEDOMAIN.net` can be replaced with the first-party cookie domain used. For example, first-party cookies on `adobe.com` would be replaced with something similar to `metrics.adobe.com`.
