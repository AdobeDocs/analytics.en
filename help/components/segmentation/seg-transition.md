---
description: Frequently asked questions around segmentation.
title: Frequently Asked Questions for segmentation
feature: Segmentation
exl-id: 316e2a2e-55d3-4c23-9985-9a6d90390e86
---
# Frequently Asked Questions

Answers frequent questions on segmentation features, access, permissions, best practices, and managing legacy segments.

## Segmentation features {#features}

* Segmentation in Analysis Workspace:

  * You can [compare segments](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html).
  * Use [segments as dimensions](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) in a comparison.
  * Use segments in [fallout analysis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.html).

* You can [apply multiple segments to a report or project](/help/components/segmentation/segmentation-workflow/seg-workflow.md).
* Segments are universal to all report suites.
* The [Segment Builder](/help/components/segmentation/segmentation-workflow/seg-workflow.md) simplifies segment creation.
* The [Segment Manager](/help/components/segmentation/segmentation-workflow/seg-workflow.md) lets you set up [workflows](/help/components/segmentation/segmentation-workflow/seg-workflow.md) with segment sharing, tagging, verification, and approval features.
* You can [tag segments](/help/components/segmentation/segmentation-workflow/seg-workflow.md) to organize and search later instead of using folders.
* You can create [Sequential Segments](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
* The Page View container was renamed to the Hit container to indicate that this container segments all types of data and not just page views. For example, link tracking calls, and trackAction calls from the mobile SDKs are all included or excluded by the hit container. Note that there wasn't a change to the way this container functions - it was simply renamed.

See the [Improving Segmentation in Adobe Analytics](https://blog.adobe.com/en/publish/2014/05/20/improving-segmentation-adobe-analytics.html) post on the Adobe Blog for more details.

## Access the Segmentation Tools {#access}

**How do I get to the Segment Builder?**

You can access the Segment Builder by:

* Displaying an existing report and clicking the Segments icon  ![Segment icon](assets/segment_icon.png) in the left navigation. In the segment rail that displays, then click **[!UICONTROL Add]**, or 

* At the top of the Segment Manager, clicking **[!UICONTROL + Add]**.  ![Add button](assets/add_button.png)

  or 

* Clicking an existing segment title in the Segment Manager to edit the segment in the Segment Builder.

**How do I get to the Segment Manager?**

Access the Segment Manager by:

* Going to  **[!UICONTROL Analytics]** > **[!UICONTROL Components]** in the top navigation. Then click **[!UICONTROL Segments]**, or 

* Displaying an existing report and clicking the Segments icon  ![Segment icon](assets/segment_icon.png) in the left navigation. Then click **[!UICONTROL Manage]**, or 

* Pressing the slash key '/' anywhere in the interface and searching for segment manager.

## Permissions {#section_648DFA3A882146C485A84ED014EEC707}

+++ **What rights and privileges do I need to use, create, and manage segments?**

By default, all users can create and edit personal segments. However, Admins can decide who should have [permissions to create segments](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html) and can assign them to specific groups. These segments can be shared directly with any other Analytics user.

Admins can edit any segment, and share segments with groups and with everyone in the organization. [More...](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **Can I see all segments in my company?**

Yes, Admins can see all segments within the [!DNL Analysis Workspace] and [!DNL Reports & Analytics] user interfaces.

Report Builder displays segments that you own and segments that are shared with you.

+++

+++ **Can I manage all Analytics segments in the Segment Manager?**

Yes, all segments can be managed in the Segment Manager. Segment Manager displays segments that are visible to the owner (user who created the segment), shared users, and admin users. The segment selector displays segments that are owned by and shared with the user.

Admins can see all segments within the Analysis Workspace and [!DNL Reports & Analytics] user interfaces.

Report Builder displays only segments built by you or segments that have been shared specifically with you.

+++

+++ **Why can't I delete this segment?**

If the segment was [published to the Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-workflow.md), you cannot delete it or edit it. However, you can copy it and edit the copied version.

+++

## Best Practices {#best-practices}

+++ **What should I do with duplicate segments that have the same name but may have different definitions?** 
Now that segments work in multiple report suites, you might find that you have multiple segments with the same name. We recommend that you either

* Rename segments that have the same name, but different definitions, or 
* Delete segments that are no longer necessary.

+++

+++ **What does Adobe recommend with regards to cleaning up segments?**

* Tag all segments with legacy tag.
* Review the segments that you have.
* Add them to the segment library where applicable.
* Approve segments that are canonical.
* Tag segments according to [best practices](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

+++

## Managing Legacy Segments {#legacy}

+++ **What happened to my existing segments?**

Your existing segments will continue to work as they did before. Any reports that have these segments applied will continue to work correctly. [More...](/help/components/segmentation/seg-transition.md)

Most former pre-defined and suite segments will be migrated over as segment templates into the Segment Builder. Segment templates are used to quickly build custom segments with common audiences. Segment templates can't be applied to a report directly, but they can be easily saved to a custom segment.

Segment templates are marked with a special icon in Segment Builder: 

![](assets/seg_templates.png)

+++

+++ **What happened to scheduled reports that have segments applied?**

Scheduled reports continue to run properly with the segments that you defined.

When you delete a segment, scheduled reports and dashboards that have this segment applied continue to work normally, i.e. the segment or dashboard continues to use the deleted segment.

Scheduled reports do not update when you edit a segment with the same name. Here is an example: Let's suppose you have 2 segments with the same name in different report suites:

![](assets/duplicate_seg_names.png)

You have a bookmark that references the segment for the mainprod report suite. Then you delete that segment because it's a duplicate. The bookmark will continue to run, referencing the definition of the deleted segment. If you change the segment definition for the maindev segment to include Catalina Island and Tijuana Mexico, the segment applied to the bookmark will not change. It will use the old definition. To fix this, update the bookmark to reference the new definition. If you are unsure whether a bookmark, dashboard or scheduled report is using a deleted segment, you could change the name of the remaining segment so it's more clear whether the bookmark is using the remaining segment.

+++

+++ **What happened to Data Warehouse segments?**

All existing Data Warehouse segments still work in Data Warehouse. Most Data Warehouse segments will also work in other components such as Analysis Workspace and Reports & Analytics.

You can create or edit a new Data Warehouse segments in the segment builder/manager. The Product Compatibility mechanism in the Segment Builder automatically determines whether a segment is compatible with Data Warehouse.

+++

**What happened to Pre-Configured Segments?**

* **Single Page Visits**
* **Visits from Mobile Devices**
* **Visits from Natural Search**
* **Visits from Paid Search**
* **Visits with Visitor ID Cookie**

These segments will be migrated over as segment templates into the Segment Builder. Existing reports that have these segments applied will continue to work correctly.

+++

+++ **What happened to Experience Cloud (Suite) segments:**

* Non-Purchasers
* Purchasers
* First Time Visits
* Visits from Social Sites
* Visits of More than 10 Minutes*
* Visits with 5+ Previous Visits*
* Visits from Facebook*

Most of these segments (except the ones marked with an asterisk *) were migrated over as segment templates into the segment builder. Additionally, several new segment templates have been added.

Existing reports that have these segments applied continue to work correctly.

+++

+++ **What happens to Admin segments (also known as "Global" segments)?**

**Admin** segments will be migrated into the new segment interface and will show up as segments shared with everyone.

The owner of these segments is set to the admin with the oldest account in the login company's list of admin users, however, all Admins can delete, edit and share these segments.

The segment management interface in the Admin Console where Admins created and managed these global segments is no longer available. Admins should now use the new segment builder to create segments and share them with appropriate groups or individuals or with everyone.

<!-- 

seg_definition.xml

 -->

Existing segments that use logic that has changed as described in this document continue to work correctly, though they must be updated before they can be saved again. For example, if you have an existing segment where US States contains 'New York', it continues to work correctly, though the next time you edit the segment you'll need to update it to use the enumerated type with an equals condition.

+++

### Migration tips

The following tips will help you migrate common dimensions:

* Geo-city/region/country - search for and select specific cities, regions or countries instead of using a partial match.
* Browsers - use the Browser Types dimension to get all browsers in a type, e.g. Google Chrome 
* Operating Systems - use the OS Types dimensions to get all operating systems in a type, e.g. Microsoft Windows.

* [New and Renamed Dimensions](/help/components/segmentation/seg-transition.md#section_73CF121B64A24DEF8E6499F3167BF742) 
* [Changes to Contains](/help/components/segmentation/seg-transition.md#section_1A9EDEE5CBC44B5AA6262560052ABE77) 
* [Changes to Less Than and Greater Than](/help/components/segmentation/seg-transition.md#section_84A8AAD0344148AD9F9211D3EB271903)

## New and Renamed Dimensions {#renamed}

The following table contains a list of dimensions that were renamed in Segment Builder.

|New Dimension Name|Previous Name|Notes|
|--- |--- |--- |
|Operating System Types|New|Added in Spring 2015.|
|Browser Width - Bucketed|Browser Width|This dimension is compatible with all interfaces, and is split into an enumerated list of ranges instead of specific integer values. If you need to segment specific values, use the granular version of this dimension in a data warehouse segment.|
|Browser Height - Bucketed|Browser Height|This dimension is compatible with all interfaces, and is split into an enumerated list of ranges instead of specific integer values. If you need to segment specific values, use the granular version of this dimension in a data warehouse segment.|
|Browser Width - Granular|Browser Width|This was renamed and is now compatible with data warehouse only. When defining segments that are compatible with all interfaces, use the enumerated type, Browser Width - Bucketed.|
|Browser Height - Granular|Browser Height|This was renamed and is now compatible with data warehouse only. When defining segments that are compatible with all interfaces, use the enumerated type, Browser Height - Bucketed.|
|Cookie Support|Cookies|-|
|Color Depth|Monitor Color Depth|-|
|-|"App - *"|the "App -" prefixes were removed from a number of dimension types. Since mobile app data is typically captured in a report suite that does not contain web data, these prefixes were not necessary.|
|Entry Page Original|Original Entry Page|-|
|Java Enabled|Java|-|
|Mobile Max Browser URL Length|Mobile Browser URL Length|-|
|Mobile Mail Decoration|Mobile Decoration Mail Support|-|
|Mobile Device|Mobile Device Name|-|
|Mobile Max Bookmark Length|Mobile Max Bookmark URL Length|-|
|Mobile Max Email Length|Mobile Max Mail URL Length|-|
|Mobile Operating System (Deprecated)|Mobile OS|Use the Operating System dimension and apply a visits from mobile devices segments instead.|
|Mobile Push To Talk|Mobile PTT|-|
|Survey Views|Total Survey Views|-|
|Survey Responses|Total Survey Responses|-|
|Visit Depth|Path Length|-|
|Zip Code|Zip/Postal Code|-|

{style="table-layout:auto"}

## Changes to String-Based Dimensions that have Known Values {#string-based-dims}

String-based dimensions that have a known set of values were changed to enumerated types. When creating a segment using these dimensions, the list is pre-populated with all known values and the only operator supported is equals. This lets you quickly segment the exact values you were looking for without selecting unintended values when using less restrictive matching.

The following dimensions were changed to enumerated lists: 

|  mobile manufacturer  | mobile email length  | color depth  |
|---|---|---|
|  mobile screen size  | mobile device number  | monitor resolution  |
|  mobile screen height  | mobile push to talk  | plugin  |
|  mobile cookie support  | mobile mail decoration  | operating system  |
|  mobile image support  | mobile information services  | referrer type  |
|  mobile color depth  | mobile device type  | search engine  |
|  mobile audio support  | browser type  | state  |
|  mobile video support  | browser  | geo country  |
|  mobile drm  | connection type  | geo region  |
|  mobile net protocols  | mobile carrier  | geo city  |
|  mobile os  | cookie  | geo dma  |
|  mobile java vm  | customer loyalty  | persistent cookie  |
|  mobile bookmark length  | java enabled  | paid search  |
|  mobile url length  | language  |  |

## Changes to Integer-Based Dimensions that have Known Values {#integer-based-dims}

Integer-based dimensions (such as browser width) with a known set of values were split into enumerated ranges so you can quickly define segments for a specific range. These enumerated lists are appended with " - Bucketed" after the dimension name. The following screen demonstrates how these dimensions are segmented using the previous and new segment builder interfaces: 

![](assets/seg_browser_dimension.png)

The less than, greater than, and similar operators are now compatible with Data Warehouse segments only. Segments intended to be compatible with all reporting interfaces should use the "Bucketed" version of the metric with the equals operator.
