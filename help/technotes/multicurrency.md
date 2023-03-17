---
description: Describes how to define target currency codes for multi-currency support to work.
title: Multi-currency support
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
---
# Multi-currency support

Adobe offers multiple levels of currency conversion so that your organization can achieve the desired currency in many reports. Conversion happens that three levels:

## Page level

You can use the [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) variable to set the desired currency on each page. If the currency on the page does not match the destination report suite's currency, Adobe performs a currency conversion to the report suite's currency based on the current day's exchange rate. The converted currency is recorded.

## Report suite level

Every report suite has a **base currency**. This currency dictates the context of all currency metrics (such as [Revenue](/help/components/metrics/revenue.md)). All currency data stored is in the report suite's base currency.

## User level

For Reports & Analytics, users can set a different currency than the report suite's base currency under [Report settings](/help/analyze/reports-analytics/report-settings.md). This setting is non-destructive, meaning that it does not alter the underlying data. Instead, it applies basic currency conversion to all reports viewed based on today's exchange rate. If you view the same report on different days, the numbers can change due to different daily exchange rates.

Analysis Workspace currently does not offer user-level currency conversion.
