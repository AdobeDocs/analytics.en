---
description: Lists a few considerations you should be aware of before deleting segments.
title: Delete segments
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
---
# Delete segments

This article lists a few considerations you should be aware of before you delete segments.

When you delete a segment:

* Scheduled reports and dashboards that have this segment applied continue to work normally. For example, the segment or dashboard continues to use the deleted segment.
* Scheduled reports do not update when you edit a segment with the same name. Here is an example: Assumee you have 2 segments with the same name in different report suites:

  | Segment name | Report suite |
  |---|---|
  | Visits from California | mainprod |
  | Visits from California | maindev |

  You have a bookmark that references the segment for the [!UICONTROL mainprod] report suite. Then you delete that segment because the segment is a duplicate. The bookmark will continue to run, referencing the definition of the deleted segment. If you change the segment definition for the remaining segment to include Catalina Island and Tijuana Mexico, the segment applied to the bookmark will not change. The segment will use the old definition. To fix this, update the bookmark to reference the new definition. If you are unsure whether a bookmark, dashboard or scheduled report is using a deleted segment, you could change the name of the remaining segment to indicate whether the bookmark is using the remaining segment.
