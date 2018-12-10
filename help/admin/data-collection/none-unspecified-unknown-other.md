---
description: Various reports in the Adobe Experience Cloud can show None, Unspecified, Other, or Unknown, depending on the specific report viewed. Generally, this breakdown means that the variable was not defined or otherwise unavailable. The following provides a comprehensive list of how each report can have one of these line items.
seo-description: Various reports in the Adobe Experience Cloud can show None, Unspecified, Other, or Unknown, depending on the specific report viewed. Generally, this breakdown means that the variable was not defined or otherwise unavailable. The following provides a comprehensive list of how each report can have one of these line items.
seo-title: None, Unspecified, Unknown, and Other in reporting
solution: Analytics
title: None, Unspecified, Unknown, and Other in reporting
uuid: 8f99f3d3-6294-47e6-aead-4b616088b2e5
index: y
internal: n
snippet: y
---

# None, Unspecified, Unknown, and Other in reporting

Various reports in the Adobe Experience Cloud can show None, Unspecified, Other, or Unknown, depending on the specific report viewed. Generally, this breakdown means that the variable was not defined or otherwise unavailable. The following provides a comprehensive list of how each report can have one of these line items.

## "None" in reporting {#section_A79C236232FC41E88302FAD2B3B56A6A}

This breakdown is one of the most common seen in the Adobe Experience Cloud. Some explanations why these values appear in reporting:

* **A conversion event fires without a conversion variable:** For example, a user comes to your site and makes a purchase without firing eVar1. If you view orders in the eVar1 report, there is no value to attribute this order to. Therefore, it is automatically attributed to "None." To resolve this issue in future reports, always define a conversion variable before a conversion event. 
* **Non-mobile hits in mobile reports:** Any non-mobile hits in mobile reports are listed as 'None'. 
* **Mobile hits in technology reports:** Similarly to non-mobile hits in mobile reports, mobile hits in all Visitor Profile | Technology reports are listed as 'none'. The mobile technology reports and Visitor profile technology reports are mutually exclusive. 
* **Merchandising eVars that do not fire at or before a conversion event:** Similar to events firing without eVars, it is possible to see None in a Merchandising eVar report when that variable is not defined before a success event. Furthermore, you can see more than 100% of a conversion event attributed to "None" if a user purchases multiple products at once.

## "Unspecified" in reporting {#section_89E67EADA7B04B6193FCD91C8D5883EE}

Similar to "None," this result occurs when the breakdown is unobtainable or otherwise unavailable:

* **Unclassified data in classification reports:** When viewing classification data, any value that doesn't have data associated with that particular classification returns "Unspecified." To resolve this issue, create a classification export file and classify the appropriate columns. 
* **Correlation reports where only one variable fired:** Correlation reports must account for every instance of that particular variable value. For example, if you tried breaking down prop1 by prop2 and these two variables don't fire in the same image request, you see a correlation report with a breakdown of "Unspecified." To remove unspecified from correlation reports, it's necessary to define all correlated traffic variables with a value on the same image request. In many situations, this expectation is unrealistic. Therefore, this line item can be ignored as long as the user is aware that it means that the first variable was defined without the second. 
* **Non-browser hits when viewing Technology reports:** Adobe Analytics is heavily dependent on Javascript functions to retrieve Visitor Profile information. Unknown browser sources where JavaScript is not available contributes to this line item (for example, an executable program or a user-created browser). These Technology reports show unspecified to indicate that this information was unable to be gathered. "Unspecified" can also occur if your implementation code is placed into the <head> tags of your web page. Adobe highly recommends that you don't use the <head> tags, as it affects many aspects of reporting. Placing your implementation within the <body> tags resolves this issue. 
* **Hierarchy reports with different amounts of levels:** Similar to correlations, hierarchies must account for all page views across all levels. For example, you have one page with a hierarchy two levels deep and another three levels deep. Viewing the level-three hierarchy report in marketing reports & analytics shows "unspecified" to account for the page with only two levels. It is not advisable to attempt to remove "Unspecified" from hierarchy reports. Doing so requires that every page on your site the same number of levels. Since this practice essentially defeats the purpose of implementing hierarchies in the first place, Adobe recommends that you ignore these breakdowns in reporting.

## "Other" in reporting {#section_E0820EF88D2F4550B363C6B0523AF829}

Though slightly less common in reporting, "Other" can occur under several circumstances:

* **Pages fire outside your internal URL filter**s: When viewing the Pages report, this issue happens when image request URLs do not match your internal URL filters for the report suite. This measure is taken to help guard against data fraud, such as if another organization steals your source code and implements it on their own site. To correct this issue, ensure that all URLs your code is implemented on matches the internal URL filters set up within the Admin Console. 
* **Visitors using an infrequently used browser:** In the Browser Types report, "Other" appears as a breakdown if visitors are using a browser that is not a popular browser type. There are many organizations that produce browsers. So, to prevent the report from being muddled with too much information, all browsers that larger organizations didn't create are bucketed into "Other."

## "Unknown" in reporting {#section_6C530358FC364B2082E478A484D36C61}

"Unknown" can occur under several circumstances:

* **Non-browser hits when viewing Technology reports:** Similar to Unspecified, if the javascript function was unable to fire, "Unknown" is shown in reporting. 
* **Using segments in which a variable in the rule is disabled:** To properly segment, make sure that variables specified in a segment are enabled. Failure to do so lists the segment as 'Unknown'.

## Filtering these values in reporting {#section_5536E2B419D445D39C932E8F12C0070C}

Under most circumstances, it is safe to ignore these line items. However, if you want to remove them, you can filter them out or remove the value from the graph.

**Create a search filter**

1. Navigate to the desired report, and then click **[!UICONTROL Advanced]** next to the data filter. 
1. Create the logic **[!UICONTROL Does not contain]**, followed by the value that you want to exclude (None, Unspecified, Other, or Unknown). 
1. Click **[!UICONTROL Search]**.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. If a search filter fails to exclude data, try using this value (including the colons) or another value listed above such as 'None' or 'Unknown'.

**Exclude from reporting graphs**

1. Navigate to **[!UICONTROL Components]** > **[!UICONTROL Report Settings]**. 
1. Deselect **[!UICONTROL Show 'None,' 'Unspecified' and 'Typed/Bookmarked' data in report graphs]**. 
1. Click **[!UICONTROL Save]**.

If you see one of these values that is not explained in any of the above scenarios, ask an [Adobe expert in the community](https://help-forums.adobe.com/content/adobeforums/en.html). 
