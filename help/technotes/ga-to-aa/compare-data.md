---
title: Compare Adobe Analytics data to third-party products
description: Understand your options when directly comparing data in Adobe Analytics to data collected by other Analytics solutions.
feature: Third-party Integration
exl-id: b4f85088-7ffd-45dc-bdd1-c0fc8dc3b332
TQID: 'https://experienceleague.adobe.com/I-zMxnrvOOk3NUjeQFbcrIq0nAPO6AAaO0eznskChgQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: a60fda7a-bb0b-4eb6-b9fe-77558cbee1fa
    internal-label: Third party integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Compare Adobe Analytics data to third-party products

There are many analytics solutions available online. Each of these solutions uses its own methods to implement code and collect data. Different products have their own definition on what constitutes a page view, a visit, a unique visitor, and other metrics used in each respective product.

Because of these wildly differing definitions, data structure, and implementation, **Adobe Customer Care does not troubleshoot discrepancies with third-party analytics tools.**

If you see a large discrepancy between Adobe Analytics and a third-party analytics tool, the following resources are available:

* **Self-audit using the debugger**: You can check the pages on your site with [Adobe's debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) or another packet monitor. Using the debugger lets you validate your implementation to make sure image requests are firing correctly with the right variables.
* **Self-audit using data feeds**: Adobe offers your organization the option of receiving [Data feeds](/help/export/analytics-data-feed/data-feed-overview.md) containing all raw data for each day. Your organization can then use this data and compare it with your third-party analytics tools to determine any discrepancies.
* **Assisted audit and data validation with Adobe Consulting**: If you want an official Adobe representative to perform a full implementation audit on your site, contact your Adobe Account Team. They can arrange a meeting with an implementation consultant who can audit your site based on your company's contract.
