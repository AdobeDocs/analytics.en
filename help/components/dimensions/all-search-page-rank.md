---
title: All search page rank
description: Determine which page on a search engine a visitor clicked through to your site.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
---
# All search page rank

The 'All search page rank' dimension provides insight on which page of search results a visitor clicked through to your site. For example, if your site appears on the second page of a search engine's search results, the dimension item for this variable is "Search Page 2".

## Populate this dimension with data

Getting this dimension to work only requires that your report suite have [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) set up correctly. AppMeasurement automatically populates this dimension without any implementation code changes.

## Dimension items

If a visitor clicks through to your site from a search engine, this dimension's value is "Search Page" followed by the page number they clicked through on. If a hit does not originate from a search engine, this dimension's value is "Unspecified".
