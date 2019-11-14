---
title: VRS and project curation
description: Learn how to curate vrs components and projects
---

# VRS and project curation

When you curate projects or virtual reports suites (VRSs), you essentially filter out components so that your audience sees only those project/VRS components (dimensions, metrics, segments, date ranges) that you want them to use.

>[!Note]
>Component permissions are the primary mechanism governing which components a user can see. They are managed through the Admin Tools. Curation is a secondary filter.

We have recently improved the curation experience. Here is an overview of what the **[!UICONTROL Show All]** button reveals, in addition to the curated components already available, in different curated experiences and by permission level:

|Curation Type|Admins|Non-Admin project owners|Non-Admins|
|---|---|---|---|
|Curated VRS|All non-curated VRS components|Non-curated VRS components that this role owns or that have been shared with them|Non-curated VRS components that this role owns or that have been shared with them|
|Curated Project|All non-curated project components|All non-curated project components|Non-curated project components that this role owns or that have been shared with them|
|Curated Project in a Curated VRS| All non-curated components, shown under **[UICONTROL Non-Curated Project Components]** and **[UICONTROL Non-Curated VRS Components]**| All non-curated project components AND non-curated VRS components that this role owns or that have been shared with them|Non-curated VRS and project components that this role owns or that have been shared with them|

>[!IMPORTANT]
>VRS curation is always applied before project curation, so even if your curated project includes certain components, they will be filtered out if the curated VRS does not include them.
