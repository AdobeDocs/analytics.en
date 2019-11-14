---
description: Lookup table to determine the source of a hit based on the page_event value.
keywords: Data Feed;hit;source
solution: Analytics
title: Hit Source Lookup
topic: Reports and analytics
uuid: b4ef2366-a7c3-421b-8dc6-279706fe277f
---

# Hit Source Lookup

Lookup table to determine the source of a hit based on the page_event value.

|  ID  | Hit source  |
|---|---|
|  1  | Page view or tracked link with no timestamp passed in (non-timestamped report suites)  |
|  2  | Page view or tracked link with timestamp passed in (timestamped report suites)  |
|  3  | Live log file (not historical log file) with hit timestamps  |
|  4  | not used  |
|  5  | "generic" (sometimes known as ecommerce) data source (like current data source)  |
|  6  | full (historical) log file (not live log file)  |
|  7  | transactionid/customerid data source file  |
|  8  | SCM (SearchCenter+) data sources  |
|  9  | Adobe Social summary metrics  |

