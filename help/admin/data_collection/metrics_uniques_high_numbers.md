---
description: When a report has a large number of unique values, marketing reports provide functionality to ensure that the most important values appear in your report.
seo-description: When a report has a large number of unique values, marketing reports provide functionality to ensure that the most important values appear in your report.
seo-title: Reporting high numbers of unique values (low-traffic)
solution: Analytics
title: Reporting high numbers of unique values (low-traffic)
topic: Metrics
uuid: 69bb8496-9aa3-4214-b6fe-0647e80320f9
index: y
internal: n
snippet: y
---

# Reporting high numbers of unique values (low-traffic)

When a report has a large number of unique values, marketing reports provide functionality to ensure that the most important values appear in your report.

At the beginning of each calendar month, Analytics reports include the first 500,000 values received for any single variable in reports. This includes page names, and other traffic and commerce variables. For example, each unique page name on your site counts toward this total.

After 500,000 unique values are received, Analytics reports begin to optimize which values are displayed in reports. When new values are received after this threshold, the system initially groups these values in a single line item in reports titled "(Low-Traffic)". (note: this line item was previously titled "Uniques Exceeded".)

If one of these values begins to receive significant traffic, the value is reported as a separate line item along with the first 500,000 values for the remainder of the month (the first 500,000 values are always reported separately regardless of traffic).

If a variable value receives enough traffic so that it's no longer listed as (Low-Traffic), the first values bucketed in this line item don't move to its respective line item. Those first 10-100 instances stay under (Low-Traffic).

If the number of unique values exceed 1 million in a single month, a second threshold is applied which requires more traffic before a value is reported as a separate line item. For example, a new page that starts to receive 100 hits per day will be reported as a separate line item, but a new page that receives fewer than 10 hits might not.

Threshold limits are 500,000 and 1 million unique values by default. All values, including each unique value in "(low-traffic)", are available in DataWarehouse reports.

If you have a custom unique value limit, the following applies:

* If you have a uniques limit set to less than 500,000, your limit is used for both the lower and upper thresholds. 
* If you have a uniques limit set between 500,000 and 1,000,000 today, your limit is used for the lower threshold and 1,000,000 for the upper threshold. 
* If you have a uniques limit set above 1,000,000 today, your limit is used for both the lower and upper thresholds.

## Segments {#section_AB991804902848778D8A2DBB60012C0F}

Low-traffic values are always included in data warehouse segments, but are not included in ad hoc analysis or marketing reports & analytics segments.

If a value receives enough traffic to appear in reports, values received from that time until the end of the month appear in ad hoc analysis and marketing reports & analytics segments. For example, if a value is low-traffic on Monday but is in reports on Tuesday, the segment will only include the Tuesday data.

## Classifications {#section_8F1352C1DBA44199A85D272FC201BFF7}

Low-traffic values cannot be classified. If a value receives enough traffic to appear in reports, it can be classified from that point until the end of the month. 
