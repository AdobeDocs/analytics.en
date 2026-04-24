---
title: Limit a Virtual report suite to certain dates
description: Understand how to limit a Virtual report suite date range to focus on stitched data only.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/x7zHG4xkSr1yDLZ2dfosn5PaK4JVxiMWC6xksSTLypE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Limit a Virtual report suite to certain dates

{{available-existing-customers}}

When we turn on stitching, the stitching starts on a specific date. Let's assume that date is June 1. The CDA Virtual report suite will contain unstitched data prior to June 1. You may want to hide any data in the Virtual report suite prior to June 1 so that your analysis can focus on date ranges after stitching began.

You can limit the Virtual report suite data to certain dates by doing the following:

## Step 1: Create Virtual report suite with a rolling-daily date range

When you set up the Virtual report suite, under Components, add in a date range that has a fixed start, with a rolling-daily date range. The fixed start should be the day that stitching began.

![](assets/rolling-daily.png)

## Step 2: Create an "exclude-exclude" segment

Next, create a hit segment that puts the date range in an exclude container inside another exclude container. It's an "exclude exclude."

The reason for the "exclude exclude" is that date ranges are intended to override the date range of the report. So if you just include June 1 forward it will always make the report date range June 1 forward. This will lead to undesirable results. When you "exclude exclude", it overrides this behavior and just limits the data you can draw from to the appropriate date range.

![](assets/exclude-exclude.png)

## Step 3: Apply this segment to your Cross-device Analytics Virtual report suite

![](assets/apply-segment.png)

## Step 4: See the results in reporting

Notice that reporting now starts on the desired date, the same day that stitching was first implemented:

![](assets/report-limited-dates.png)
