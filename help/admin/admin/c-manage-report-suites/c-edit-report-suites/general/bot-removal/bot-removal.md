---
title: Bot removal in Adobe Analytics
description: How to remove bots in Adobe Analytics
feature: Bot Removal
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
---
# Bot removal in Adobe Analytics

In Adobe Analytics, you have multiple options for removing bot traffic from reporting:

## Use Bot Rules

Both standard and custom bot filtering methods are supported in **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**:

| Rule type  | Description  |
|--- |--- |
|Standard IAB bot rules|Selecting **[!UICONTROL Enable IAB Bot Filtering Rules]** uses the [IAB's](https://www.iab.com/) (International Advertising Bureau's) International Spiders & Bots List to remove bot traffic. Most customers select this option at a minimum.|
|Custom bot rules|You can define and add custom bot rules based on user agents, IP addresses, or IP ranges.|

For more detail, see [Bot rules overview](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

## Use the [!UICONTROL websiteBot] plug-in to identify bots

The [!UICONTROL websiteBot] plug-in allows you to dynamically identify if desktop visitors are bots. You can use this data to drive greater accuracy in all types of reporting, which gives you a better way to measure legitimate site traffic.

This plug-in performs two checks:

* First, it determines whether the device is a desktop or mobile device using the navigator.UserAgent variable. Mobile devices are ignored.
* If it is a desktop device, it adds an event listener for mouse movement.

For more information, see the [Adobe Analytics Implementation Guide](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html).

## Use a combination of Adobe Tools

In addition, since bots are morphing quickly, Adobe offers several other powerful features that, when combined properly and on a regular basis, can help drive the removal of these enemies of data quality. Those features are: Experience Cloud ID Service, Segmentation, Data Warehouse, Customer Attributes, and Virtual Report Suites. Here is an overview of how you can use these tools.

### Step 1: Pass your visitors' Experience Cloud ID into a new declared ID

To start, create a new declared ID in the [People Core Service](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html). Pass your visitor's Experience Cloud ID into this new declared ID, which can be done quickly and easily with [tags in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html). Let's use the name "ECID" for the declared ID.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-cust-attr-setup.png)

Here is how this ID can be captured via Data Element. Be sure to populate your Experience Cloud OrgID into the Data Element correctly.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Once this Data Element is set up, follow [these instructions](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) to pass declared IDs into the ECID Tool using tags in Adobe Experience Platform.

### Step 2: Use segmentation to identify bots

Now that you have your visitor's ECID passed into a declared ID, you can use [segmentation in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html) to identify visitors who are acting like bots. Bots are often defined by their behavior: single access visits, unusual user agents, unknown device/browser information, no referrers, new visitors, unusual landing pages, etc. Use the powers of Workspace drill-downs and segmentation to identify the bots that have evaded IAB filtering and your report suite bot rules. For example, here's a screenshot of a segment that you could use:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg1.png)

### Step 3: Export all [!DNL Experience Cloud IDs] from the segment via Data Warehouse

Now that you have identified the bots using segments, the next step is to use Data Warehouse to extract all the Experience Cloud IDs associated with this segment. This screenshot shows how you should set up your [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) request:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-dwh-3.png)

Remember to use Experience Cloud Visitor ID as your dimension and apply the 'Bots' segment.

### Step 4: Pass this list back to Adobe as a Customer Attribute

Once the Data Warehouse report arrives, you have a list of ECIDs that must be filtered from historical data. Copy and paste these ECIDs into a blank .CSV file with just two columns, ECID and Bot Flag.

* **ECID**: Make sure that this column header matches the name you gave to the new declared ID above.
* **Bot Flag**: Add 'Bot Flag' as a Customer Attribute schema dimension.

Use this .CSV file as your Customer Attribute import file, then subscribe your report suite(s) to the Customer Attribute as described in this [blog post](https://theblog.adobe.com/link-digital-behavior-customers).

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-csv-4.png)

### Step 5: Create a segment that leverages the new Customer Attribute

Once your data set has been processed and integrated into Analysis Workspace, create one more segment that leverages your new "Bot Flag" customer attribute dimension and an [!UICONTROL Exclude] container:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg2.png)

### Step 6: Use this segment as your Virtual Report Suite filter

Finally, create a [Virtual Report Suite](/help/components/vrs/vrs-about.md) that uses this segment to filter out the identified bots:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-vrs.png)

This newly segmented Virtual Report Suite will now result in a cleaner set of data, with the identified bots removed.

### Step 7: Repeat steps 2, 3, and 4 regularly

Set at least a monthly reminder to identify and filter new bots, perhaps before a regularly scheduled analysis.
