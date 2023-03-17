---
description: Various reports in Adobe Analytics can show Unspecified, None, Other, or Unknown, depending on the specific report viewed. Generally, this line item means that the variable was not defined or otherwise unavailable.
title: Unspecified, None, Other, and Unknown in reporting
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
---
# "Unspecified", "None", "Other", and "Unknown" in reporting

Various reports in Adobe Analytics can show "Unspecified", "Other", or "Unknown", depending on the specific report viewed. Generally, this line item means that the variable was not defined or otherwise unavailable. The following provides a comprehensive list of how each report can have one of these line items.

## "Unspecified" (or "None") in reporting

"Unspecified" is a fairly common line item in reports. It is also frequently referred to as "None".

* **An event fires without a conversion variable:** For example, a user comes to your site and makes a purchase without any eVar1 value. If you view orders using the eVar1 dimension, there is no value to attribute this order to. Therefore, it is automatically attributed to "Unspecified".
* **Unclassified data in classification reports:** When viewing classification data, any value that doesn't have data associated with that particular classification returns "Unspecified". To resolve this issue, classify the parent variable value.
* **Breakdown reports where only one variable fired:** When you apply a breakdown to a variable, every instance of that variable must be accounted for. If the second variable was not seen or if it persisted from a previous hit, the dimension item is "Unspecified".
* **Non-mobile hits in mobile reports:** Any non-mobile hits in mobile reports are listed as "Unspecified" ("Non Mobile" in Reports and Analytics).

## "Other" in reporting

Though somewhat rare in reporting, "Other" can occur under several circumstances:

* **Pages fire outside internal URL filters:** This value is in place to help guard against data fraud, such as if another organization steals your source code and implements it on their own site. To correct this issue, ensure that all URLs your code is implemented on matches the internal URL filters in your report suite settings.
* **Visitors using an infrequently used browser:** In the Browser Types report, "Other" appears as a breakdown if visitors are using a browser that is not a popular browser type. There are many organizations that produce browsers. All browsers that larger organizations didn't create are bucketed into "Other" to prevent report clutter.

## "Unknown" in reporting

"Unknown" can occur under several circumstances:

* **Non-browser hits when viewing Technology reports:** If an AppMeasurement library is unable to determine if a feature is supported, "Unknown" is shown in reporting.
* **Using segments where components are not accessible:** Make sure that variables used in a segment are enabled and that users can access them. If a user does not have access to a segment component, or if a variable is disabled, "Unknown" is shown.

## Filtering these values in reporting {#section_5536E2B419D445D39C932E8F12C0070C}

Under most circumstances, it is safe to ignore these line items. The search filter can be used to remove them if desired.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. If a search filter fails to exclude data, try using this value (including the colons).
