---
title: Browser
description: The name and version of the browser used.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
---
# Browser

The '[!UICONTROL Browser]' dimension reports the name and version of the browser sending the hit. This dimension is useful to understanding the most common browsers visitors use. When testing new versions of your site, you can run those tests on the top browsers in this dimension to maximize quality control efforts.

## Populate this dimension with data

This dimension references a lookup table internal to Adobe. The lookup value is based on the `User-Agent` HTTP header in image requests. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box.

## Dimension items

Dimension items include the browser names and versions used. Different versions of the same browser are separate dimension items.

Some dimension items contain `"(unknown version)"` instead of their version number. This dimension item references a recent browser release that Adobe has not added to their lookup tables. Since browsers frequently update, the `"(unknown version)"` for a given browser is common and temporary. Adobe typically updates lookup tables during monthly maintenance releases.

## Changes in labeling and definition

Below is a list of changes to how browsers are represented in reporting. These changes may impact your reporting or any logic, such as segments, that depends on these values. 

### Removing company from browser

Starting with version 100 for Chrome, Edge and Firefox browsers, the company name will no longer appear before the browser. This could impact users if they have segment definitions based on the name of he browser. For example, a segment including a definition that "browser contains "Google" will no longer identify Chrome browsers starting with version 110.

Examples:

Version 109 of Chrome will appear as "Google Chrome 109".
Version 110 of Chrome will appear as "Chrome 109".

### Removing the distinction between mobile and non-mobile for Chrome

Starting with Chrome 110, both mobile and non-mobile versions of Chrome will be labeled the same. Currently, mobile and non-mobile versions are separately labeled. Importantly, this changes the meaning of the name without "mobile". "Chrome 109" is non-mobile (i.e. desktop) "Chrome 110" is mobile and non-mobile. Again, if you have segment definitions referencing "mobile" in the browser name, these may no longer work as expected. You can use use mobile segmentation and breakdowns to compare mobile to non-mobile traffic.

Examples: 

Mobile Chrome 109 will appear as "Chrome Mobile 109".
Non-Mobile Chrome 109 will appear as "Chrome 109".

Mobile Chrome 110 will appear as "Chrome 110".
Non-Mobile Chrome 110 will appear as "Chrome 110".
