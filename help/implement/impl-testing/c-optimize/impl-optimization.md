---
description: Analytics deployment is organized into three major steps.
keywords: Analytics Implementation
seo-description: Analytics deployment is organized into three major steps.
seo-title: Optimization overview
solution: Analytics
subtopic: Troubleshooting
title: Optimization overview
topic: Developer and implementation
uuid: 8e8ecc5b-d4b1-4d13-8525-39e4924df247
---

# Optimization overview

Analytics deployment is organized into three major steps.

1. This involves pasting a snippet of HTML code onto each page (or page template) of a website. The HTML code snippet is very small (400 to 1,000 bytes) and contains JavaScript variables and other identifiers that facilitate the data collection process.
1. The code snippet calls a JavaScript library file, which contains JavaScript functions specific to Analytics used during metrics collection. If the Analytics code is implemented correctly, the time required for the browser to execute the JavaScript library file is usually negligible.

1. The library file makes an image request to an Adobe data collection server. The server collects the data being submitted and returns a 1x1 transparent image to the visitor's browser. This third step adds an insignificant increment to the total page download time.

> [!NOTE] Customers can take additional steps to minimize Analytics overhead.

