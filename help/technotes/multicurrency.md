---
description: Describes how to define target currency codes for multi-currency support to work.
title: Multi-currency support
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Multi-currency support

Adobe offers multiple levels of currency conversion so that your organization can achieve the desired currency in many reports. Conversion happens that three levels:

## Page level

You can use the [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) variable to set the desired currency on each page. If the currency on the page does not match the destination report suite's currency, Adobe performs a currency conversion to the report suite's currency based on the current day's exchange rate. The converted currency is recorded.

## Report suite level

Every report suite has a **base currency**. This currency dictates the context of all currency metrics (such as [Revenue](/help/components/metrics/revenue.md)). All currency data stored is in the report suite's base currency.

