---
description: Learn how statistical tests are used in segment comparison.
keywords: Analysis Workspace;Segment IQ
title: Statistical Tests Used In Segment Comparison
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
TQID: https://experienceleague.adobe.com/49kZ6LC9OMizQvqxE2PCq1LtqhUHtf5iKQUgpgqSmmE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Statistical tests used in Segment comparison

Each of the top comparison tables shows a difference score. That score is calculated by several statistical tests depending on the comparison being made. However, no matter which test is used, the difference score is shown as a value between 0 and 1.

A score of 0 means that there is no difference between the two segments and a score of 1 means there was a very large difference between the two segments. There are two types of statistical tests employed to generate these difference scores: 

* For the **[!UICONTROL Top Metrics]** table a Mann-Whitney U test is used, 
* For the **[!UICONTROL Top Dimension Items]** and **[!UICONTROL Top Segments]** table a risk difference comparison is used.

## Top metrics difference score

In the Top Metrics table, the Segment Comparison Tool uses a two sample Mann-Whitney U Test. This test is a nonparametric equality test used to compare the one-dimensional probability distributions of each metric for each considered segment. The difference score in the metrics table is a combination of the p-value from the computed U statistic (which represents how stochastically different the two segments are distributed across a particular metric) and the relative magnitude of the observed difference. A large difference score (close to 1) means that the particular metric has a large relative difference as well as a high statistical confidence that the segments are different.

## Top dimension items and top segments difference scores

To compute the difference score on the Top Dimension Items and Top Segment Difference tables, a relative risk differencing algorithm is used (similar to risk ratio, although using a difference rather than a ratio). A risk difference is calculated by subtracting the cumulative incidences of a dimension item (or overlap with a segment from the segment table) of one selected segment from the other. A high difference score (close to 1) means that the particular dimension item or tertiary segment was very prominent in one of the selected segments and not the other.

>[!NOTE]
>
>In all three tables, the difference statistic is based on an appropriate sample of visitors to make the process run as quickly as possible while remaining statistically accurate. While the difference score is based on a sample, the results presented in the table are not sampled. To ensure statistical significance, each statistical test relies on a dynamic allocation algorithm such that the smaller segment contains a sample size that provides less than 3% margin of error. If a segment contains very few visitors (less than 1,000), all available data is used instead of sample to compute the difference score.
