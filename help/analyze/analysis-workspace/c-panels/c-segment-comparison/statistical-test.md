---
description: Each of the top comparison tables show a difference score that is calculated by several statistical tests depending on the comparison being made;however, no matter which test is used, the difference score is shown as a value between 0 and 1.
keywords: Analysis Workspace;Segment IQ
title: Statistical tests used in segment comparison
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
---
# Statistical tests used in segment comparison

Each of the top comparison tables show a difference score that is calculated by several statistical tests depending on the comparison being made;however, no matter which test is used, the difference score is shown as a value between 0 and 1.

A score of 0 means there is no difference between the two segments and a score of 1 means there was a very large difference between the two segments. There are two types of statistical tests employed to generate these difference scores: for the Top Metrics table a Mann-Whitney U test is used, and for the Top Dimension Items and Top Segments table a risk difference comparison is used.

## Top metrics difference score {#section_5E8047464EB945C78543B25F8F30F17A}

In the Top Metrics table, the Segment Comparison Tool uses a two sample Mann-Whitney U Test, which is a nonparametric equality test used to compare the one-dimensional probability distributions of each metric for each considered segment. The difference score in the metrics table is a combination of the p-value from the computed U statistic (which represents how stochastically different the two segments are distributed across a particular metric) and the relative magnitude of the observed difference. A large difference score (close to 1) means the particular metric has a large relative difference as well as a high statistical confidence that the segments are different.

## Top dimension items and top segments difference scores {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

To compute the difference score on the Top Dimension Items and Top Segment Difference tables, a relative risk differencing algorithm is used (similar to risk ratio, although using a difference rather than a ratio). A risk difference is calculated by subtracting the cumulative incidences of a dimension item (or overlap with a segment from the segment table) of one selected segment from the other. A high difference score (close to 1) means the particular dimension item or tertiary segment was very prominent in one of the selected segments and not the other.

>[!NOTE]
>
>In all three tables, the difference statistic is based on an appropriate sample of visitors to make the process run as quickly as possible while remaining statistically accurate. While the difference score is based on a sample, the results presented in the table are not sampled. To ensure statistical significance, each statistical test relies on a dynamic allocation algorithm such that the smaller segment contains a sample size that provides less than 3% margin of error. If a segment contains very few visitors (less than 1,000), we use all available data and do not sample in computing the difference score.
