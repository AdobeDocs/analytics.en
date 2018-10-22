---
description: This information is intended for advanced users who are well-versed in both reporting and implementation. Do not attempt to edit your implementation without understanding the consequences. If you require implementation changes, contact your organization's Account Manager.
keywords: Analytics Implementation
seo-description: This information is intended for advanced users who are well-versed in both reporting and implementation. Do not attempt to edit your implementation without understanding the consequences. If you require implementation changes, contact your organization's Account Manager.
seo-title: Track across different implementation types
solution: Analytics
title: Track across different implementation types
topic: Developer and implementation
uuid: 0cc2b087-0264-4898-8256-0d741dbbbf06
index: y
internal: n
snippet: y
---

# Track across different implementation types

This information is intended for advanced users who are well-versed in both reporting and implementation. Do not attempt to edit your implementation without understanding the consequences. If you require implementation changes, contact your organization's Account Manager.

If you use more than one type of implementation (such as JavaScript and hardcoded image requests), ensure that the following variables are specified and match each other:

* *`s_account`* 
* *`s.visitorNamespace`* 
* *`s.trackingServer`* 
* *`s.trackingServerSecure`* (if using SSL)

If each of these do not match across implementations, users may be tracked as separate visitors. 
