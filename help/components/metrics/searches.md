---
title: Searches
description: The number of times a hit matched external search criteria.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
---
# Searches

The 'Searches' metric shows the number of hits that match Adobe's external search detection. This metric is useful when you want to look at non-search dimension items and see how they contributed to search engine traffic.

## How this metric is calculated

This metric counts the number of hits that match Adobe's external search detection. It must match both of the following:

* The hit's referrer value is a search domain recognized by Adobe
* The hit's referring URL contains a keyword query string parameter. Due to modern privacy practices, this query string value is commonly blank. Adobe recognizes blank keyword query strings as part of search detection.
