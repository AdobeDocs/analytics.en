---
title: account
description: Use the account variable to determine the report suite where data is sent to.
---

# account

> [!IMPORTANT] This variable is retired. Use the [`s.sa()`](../functions/sa-method.md) function if your implementation requires that you modify the report suite destination.

In previous versions of Adobe Analytics, the `account` variable determined the report suite you want to send data to. A report suite ID is required to send data to Adobe Analytics.

* If you use Adobe Experience Platform Launch, report suites reside under the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension.
* If you use the `s_gi()` function to instantiate an Analytics tracking object, the report suite ID's already exist as a required argument in the function.
