---
title: Use Cached Results for Faster Loading in Analysis Workspace
description: Enable a project setting in Analysis Workspace that caches results for 12 hours so projects load instantly. Refresh anytime to see the latest data.
feature: Workspace Basics
hide: true
role: User
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---

# Use cached results in Workspace projects

>[!CONTEXTUALHELP]
>id="aa_project_cached_results"
>title="Use cached results for faster loading"
>abstract="When enabled, results load instantly for 12 hours after a project is first opened by a user or delivered by a schedule. Anyone who opens the project during that time sees the same results, even though data continues to flow in the background. To load the latest results, refresh individual panels or the entire project."

{{release-limited-testing}}

You can configure Analysis Workspace projects to show cached results for a 12-hour window, allowing results to load instantly for anyone who opens the project after it is initially loaded.

Projects can be initially loaded by a user who opens the project or by a scheduled project delivery.

## Understand cached results in a project

### When results are cached

The first time the project loads, results load at normal speed, and Analysis Workspace caches them for a 12-hour window. This happens when:

* Someone opens the project

* The project runs for a scheduled delivery 

For example, if a project is scheduled for delivery at 6:00 AM, the results are cached until 6:00 PM. Everyone who opens the project between 6:00 AM and 6:00 PM sees results load instantly, including the first person to open it.

After 12 hours, the cached results expire. The next time the project loads, whether a user opens it or a scheduled delivery runs, results load at normal speed and a new 12-hour window starts.

### What results are cached

#### The project is initially cached with its original configuration

Analysis Workspace caches the results of the project as it is originally configured, with its selected report suites, applied segments, date ranges, panel drop-down selections, and so forth. Everyone who opens the project sees these cached results.

If someone changes the project configuration while viewing the cached project, the results load normally (not instantly), and [a new project variation is cached](#project-variations-are-cached-as-the-project-is-modified).

#### Project variations are cached as the project is modified

A new variation of the project is created when someone changes its original configuration, such as by selecting an item from a panel drop-down menu, applying a segment, changing a date range, or changing the selected report suite.

A new variation loads at normal speed the first time. After that, its results are also cached, so anyone who loads the same variation sees results instantly.

Consider the following:

* Analysis Workspace caches each variation of a project that someone loads. It doesn't cache every possible variation of a project. 

* Caching a new variation doesn't overwrite or invalidate results that are already cached. The original project is cached along with other variations that people have loaded.

>[!BEGINSHADEBOX]

**Example scenario**

Suppose a Global Campaign Performance project includes segments for different regions and is scheduled for delivery at 6:00 AM:

| Time | Action | Load speed |
| --- | --- | --- |
| 6:00 AM | Scheduled project delivery | Normal (results are cached for future use) |
| 7:06 AM | User A opens the project | Instant |
| 7:07 AM | User A applies the Americas segment | Normal (results are cached for future use) |
| 8:01 AM | User B opens the project | Instant |
| 8:05 AM | User B applies the Americas segment | Instant |
| 8:12 AM | User B applies the EMEA segment | Normal (results are cached for future use) |

>[!ENDSHADEBOX]

### Changes that cause cached results to refresh with the next project load

The following changes to a project's underlying configuration cause Analysis Workspace to refresh results the next time someone opens the project, even if the 12-hour window hasn't expired:

* Changes to a [calculated metric](/help/components/calculated-metrics/cm-overview.md) definition used in the project

* Changes to a segment definition used in the project

Results load at normal speed and are then cached, which begins a new 12-hour window.

### Who sees cached results

Cached results display by default for everyone who:

* Has access to the project

* Has access to the report suites used in the project

* Is loading a variation of the project that's already cached, such as one with the same segments or panel drop-down selections (for more information, see [What results are cached](#what-results-are-cached))

When viewing cached results, you can see the latest data by [manually refreshing the results](#manually-refresh-results-on-cached-projects).

### When to leave cached results disabled on a project

Some projects depend on results to reflect the latest data every time someone opens them. This is common for projects that rely heavily on same-day data, late-arriving data, or [classifications](/help/components/classifications/classifications-overview.md) that are updated frequently.

Leave cached results disabled on your project if most people who access the project need to see:

* **Data from the current day**

  If a project is cached at 7:00 AM, results don't include data that arrives after 7:00 AM until the cached results expire at 7:00 PM.

* **Late-arriving data right away**

  Late-arriving data has [timestamps](/help/implement/vars/page-vars/timestamp.md) from an earlier time period but arrives after that period has passed. For example, [Data Sources](/help/import/data-sources/overview.md) data from a call center might be uploaded the next day, or a mobile app might send hits that it stored while offline. Cached results don't include this data until they expire.

* **Updated classification values**

  Cached results continue to show the previous classification values, such as old product names, until they expire.

>[!NOTE]
>
>If these needs come up only occasionally, enable cached results and [refresh the project manually](#manually-refresh-results-on-cached-projects) when you need the latest data.

## Enable cached results for a project

Anyone who can update project settings can enable cached results. This includes the project owner and anyone with the **[!UICONTROL Edit original]** role for the project. For more information about project roles, see [Share a specific project role](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

>[!IMPORTANT]
>
>Cached results might not be a good fit if you need to see current-day data, late-arriving data, or updated classification values right away. Before you enable this setting, review [When to leave cached results disabled on a project](#when-to-leave-cached-results-disabled-on-a-project).

In the Workspace project where you want to enable cached results for faster loading:

1. Go to **[!UICONTROL Projects]** > **[!UICONTROL Project info and settings]**.

1. Select **[!UICONTROL Use cached results for faster loading]**.

1. Select **[!UICONTROL Save]**.

## View when cached results are shown in a project

A timestamp displays at the top of the project when cached results are shown. The timestamp specifies whether all results are cached or only some results:

* **[!UICONTROL Showing results from] [_date and time_]**: All panels in the project show cached results from the date and time shown.

* **[!UICONTROL Showing some results from] [_date and time_]**: Some panels show cached results from the date and time shown, while others were refreshed more recently.

![Timestamp on cached project](assets/project-cache-timestamp.png)

Panels also display a timestamp, showing when the results were cached:

* **[!UICONTROL Showing results from] [_date and time_]**: The panel shows cached results from the date and time shown.

  >[!NOTE]
  >
  >This option is not available during the alpha phase of release.

## Manually refresh results on cached projects

Only the results shown in the project are cached. Underlying data continues to flow into Adobe Analytics as usual.

To see the latest data before cached results expire, you can manually refresh results on a project any time during the 12-hour window. When you refresh the entire project, a new 12-hour window begins, and everyone who opens the project during that window sees the refreshed results.

In the Workspace project where you want to view the latest data, you can refresh results for the entire project or for a single panel.

### Refresh results for the entire project

To load the latest results for all panels and start a new 12-hour window:

1. Select the **[!UICONTROL Refresh]** ![Refresh](/help/assets/icons/Refresh.svg) icon at the top of the project next to the project's timestamp.

### Refresh results for a single panel

>[!NOTE]
>
>This option is not available during the alpha phase of release.

To load the latest results for a single panel only:

1. Select the **[!UICONTROL Refresh]** ![Refresh](/help/assets/icons/Refresh.svg) icon next to a panel's timestamp.

