---
title: Java enabled
description: Determines if Java is enabled in the browser.
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
---
# Java enabled

The 'Java enabled' dimension determines if the browser at the time has Java enabled. It is helpful in cases where you want to introduce Java-based functionality on your site and want to know how many visitors already have Java enabled. For those who have Java disabled, you can provide an alternative or instructions on how to enable it.

## Populate this dimension with data

This dimension retrieves data from the [`v` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data by detecting if Java is enabled in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `v` query string parameter containing "Y" or "N" if you would like to use this dimension.

## Dimension items

Dimension items include "Enabled", "Disabled", and "Unknown".

* **Enabled**: Java is enabled in the browser. The `v` query string contained the value "Y".
* **Disabled**: Java is disabled in the browser, or otherwise does not support Java. The `v` query string contained the value "N".
* **Unknown**: AppMeasurement was unable to determine Java support. The `v` query string was not present in the image request.
