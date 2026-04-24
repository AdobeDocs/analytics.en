---
title: Searches
description: The number of times a hit matched external search criteria.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
TQID: https://experienceleague.adobe.com/bcK-h9tkOKRHFoZ5EbX05ppNtV5S8Kok8dhMJZxf-ao
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Searches

The 'Searches' [metric](overview.md) shows the number of hits that match Adobe's external search detection. This metric is useful when you want to look at non-search dimension items and see how they contributed to search engine traffic.

## How this metric is calculated

This metric counts the number of hits that match Adobe's external search detection. It must match both of the following:

* The hit's referrer value is a search domain recognized by Adobe
* The hit's referring URL contains a keyword query string parameter. Due to modern privacy practices, this query string value is commonly blank. Adobe recognizes blank keyword query strings as part of search detection.
