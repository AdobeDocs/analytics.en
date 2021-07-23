---
title: Cookie support
description: Determines if the browser supports cookies.
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
---
# Cookie Support

The 'Cookie support' dimension reports if the browser supports cookies for a given hit. It is useful to determine the ratio of visitors who use browsers that support cookies, and those who intentionally disable them.

## Populate this dimension with data

This dimension collects data from the [`k` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement tries to set a cookie named `s_cc`, then detects if the cookie exists. The result is the query string parameter value `Y` (if the browser supports and has cookies enabled) or `N` (if the browser has cookies disabled). If you use AppMeasurement (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `k` query string parameter on each hit with the value `Y` or `N`.

## Dimension items

Dimension items include `Enabled`, `Disabled`, and `Unknown`.

* **`Enabled`**: The browser supports cookies, and has them enabled.
* **`Disabled`**: The browser does not support cookies, or the visitor disabled them.
* **`Unknown`**: AppMeasurement could not determine cookie support. The `k` query string was not present in the image request.
