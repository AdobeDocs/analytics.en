---
description: Lists a few considerations you should be aware of before deleting segments.
seo-description: Lists a few considerations you should be aware of before deleting segments.
seo-title: Delete segments
solution: Analytics
title: Delete segments
topic: Segments
uuid: d5ee3a62-404f-4348-9928-13c78e3a68e4
index: y
internal: n
snippet: y
---

# Delete segments

Lists a few considerations you should be aware of before deleting segments.

When you delete a segment,

* Scheduled reports and dashboards that have this segment applied continue to work normally, i.e. the segment or dashboard continues to use the deleted segment. 
* Scheduled reports do not update when you edit a segment with the same name. Here is an example: Let's suppose you have 2 segments with the same name in different report suites:

  ![](assets/duplicate_seg_names.png)

  You have a bookmark that references the segment for the mainprod report suite. Then you delete that segment because it’s a duplicate. The bookmark will continue to run, referencing the definition of the deleted segment. If you change the segment definition for the remaining segment to include Catalina Island and Tijuana Mexico, the segment applied to the bookmark will not change. It will use the old definition. To fix this, update the bookmark to reference the new definition. If you are unsure whether a bookmark, dashboard or scheduled report is using a deleted segment, you could change the name of the remaining segment so it’s more clear whether the bookmark is using the remaining segment.

## Editing Embedded Deleted Segments in Ad Hoc Analysis {#section_976D601DBD2244E38B0A0222E31D2610}

Ad Hoc Analysis now lets you edit embedded deleted segments within the [Calculated Metric Builder](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) and lets you perform a "Save As" operation on that segment.

However, any other deleted segments that reference the deleted segment will remain unchanged. 
