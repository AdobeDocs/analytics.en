---
description: The Activity Map Setting Panel lets you modify the settings and properties for all types of overlay visualizations.
title: Configure Activity Map settings
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
---
# Configure Activity Map settings

The Activity Map setting panel lets you modify the settings and properties for all types of overlay visualizations.

**[!UICONTROL Activity Map overlay]** > **Show settings (gear icon)** > **[!UICONTROL Settings]**

## General settings

Change general settings for the extension and overlays.

* **[!UICONTROL Companies]**: Shows the current Analytics organization that you are logged in to.
* **[!UICONTROL Page name]**: Shows the name of the current page.
* **[!UICONTROL Language]**: Changes the language for Activity Map extension labels. Does not change content on your web site or link names in reports. Supported languages include English, French, Chinese (simplified), Chinese (traditional), German, Japanese, Korean, Spanish, and Portuguese.
* **[!UICONTROL Label overlays with]**: Determines what the bubble or gradient text is. The default setting is [!UICONTROL Rank]. Options include:
  * **[!UICONTROL No label]**: No text within the labels, making them colored boxes
  * **[!UICONTROL Value]**: Displays the number of link clicks ([Occurrences](/help/components/metrics/occurrences.md))
  * **[!UICONTROL Percent]**: Displays the proportion of link clicks compared to the total number of link clicks on the page
  * **[!UICONTROL Rank]**: The numeric rank of the link by number of link clicks.
* **[!UICONTROL Label font size]**: Determines the size of the text within the bubble or gradient.
* **[!UICONTROL Gradient color]**: Allows you to change the gradient color when the visualization type is [!UICONTROL Gradient].
* **[!UICONTROL Bubble color]**: Allows you to change the bubble color when the visualization type is [!UICONTROL Bubble].
* **[!UICONTROL Color gradient based on]**: Determines which metric a link's color intensity is based on when the visualization type is [!UICONTROL Gradient].
  * **[!UICONTROL Top 30 rankings]**: Color intensity is normalized for the top 30 links.
  * **[!UICONTROL Absolute metric value]**: Color intensity is a function of the absolute metric value.
* **[!UICONTROL Gradient transparency]**: Determines the transparency of gradient overlays when the visualization type is [!UICONTROL Gradient]. This slider allows you to make the color overlay completely transparent, completely opaque, or anywhere in between.

## Standard settings

Adjust settings for standard view.

* **[!UICONTROL Dynamic data filtering]**: Allows you to change which links are displayed. 
  * **[!UICONTROL Top]**: Displays the most popular links. Use the numeric drop-down list on the right to determine the number of top links to display. Options include 1, 10, 50, and 100.
  * **[!UICONTROL Bottom]**: Displays the least popular links based on the number drop-down list. Use the numeric drop-down list on the right to determine the number of bottom links to display. Options include 1, 10, 50, and 100.
  * **[!UICONTROL All links]**: Do not apply dynamic data filtering. The numeric drop-down list does not apply when this option is selected.
* **[!UICONTROL Hide overlays for links that received no hits]**: If this box is checked, then links on the page with zero link clicks do not show an overlay and are not considered in dynamic data filtering.

## Live settings

* **[!UICONTROL Display top]**: Display the top number of gainers or losers based on the numeric drop-down list on the left.
* **[!UICONTROL Exclude bottom (%)]**: Filter out the bottom percentage of link changes to view only the links with enough data to show relevant gains or losses. The percentage is computed based on the number of links on that page. For example, filtering out the bottom 10% of a list of 200 links would filter out the bottom 20 links.
* **[!UICONTROL Auto update data]**: Determines if the Analytics data shown in the overlay automatically updates when a new period is computed.
* **[!UICONTROL Auto update period]**: When checked, refreshes the page with each new data retrieval so the links on the page are more closely synced with collected data.
