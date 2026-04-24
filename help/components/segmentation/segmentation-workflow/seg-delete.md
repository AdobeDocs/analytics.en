---
description: Understand the considerations you should be aware of before you delete segments.
title: Delete Segments
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
TQID: https://experienceleague.adobe.com/G1gycXvzM-mMdpElmelyD204Ts-C2uua5X4rJMM3JNQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Delete segments

This article lists a few considerations you should be aware of before you delete segments.

When you delete a segment:

* Scheduled reports and dashboards that have this segment applied continue to work normally.
* Scheduled reports do not update when you edit a segment with the same name. 

<!--

For example: Assume you have 2 segments with the same name in different report suites:

  | Segment name | Report suite |
  |---|---|
  | Visits from California | mainprod |
  | Visits from California | maindev |

  You have a visualization that references the segment for the **[!UICONTROL mainprod]** report suite. Then you delete that segment because the segment is a duplicate. The bookmark will continue to run, referencing the definition of the deleted segment. If you change the segment definition for the remaining segment to include Catalina Island and Tijuana Mexico, the segment applied to the bookmark will not change. The segment will use the old definition. To fix this, update the bookmark to reference the new definition. If you are unsure whether a bookmark, dashboard or scheduled report is using a deleted segment, you could change the name of the remaining segment to indicate whether the bookmark is using the remaining segment.

-->