---
description: Using adobe.com as an example, the implementations described here reference the same visid cookie.
keywords: Analytics Implementation
seo-description: Using adobe.com as an example, the implementations described here reference the same visid cookie.
seo-title: Implementation example
solution: Analytics
title: Implementation example
topic: Developer and implementation
uuid: 3265a689-4e37-4783-b747-2a426581203c
index: y
internal: n
snippet: y
---

# Implementation example

Using adobe.com as an example, the implementations described here reference the same visid cookie.

 **Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**Hardcoded image request:**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 

```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

And if first-party cookies are utilized:

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**Hardcoded image request:**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

