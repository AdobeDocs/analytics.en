---
description: Tips and Best Practices for new users of virtual report suites.
keywords: Virtual Report Suite
title: Virtual report suite FAQs
feature: VRS
exl-id: ab961bec-5719-4b90-bc10-c929b63dc923
TQID: https://experienceleague.adobe.com/SrY9IK3hWwUuFh7KCkVOIYo1yMgpy7HkDbMpZxAFsZc
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
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Virtual report suite FAQs

Tips and Best Practices for new users of virtual report suites.

| Question | Answer |
| --- | --- |
| **Should I consolidate my implementation from multiple report suites into a single "global" report suite and then use virtual report suites to expose different segments of data to my users?** | Maybe. Here are some circumstances under which you should consider continuing with individual report suites:<ul><li>If you have variables/dimensions with a large number of unique values, consolidating into a single report suite may cause you to exceed monthly unique value limits in this global suite, leading to truncation ("Low Traffic" as a line item in reports).</li><li>If you require real-time or "Current Data" reporting for individual segments (e.g. brands, business units, etc.) of your data.</li><li>Your various report suites might each have unique requirements for tracking (i.e., if they use Adobe Analytics variables and events very differently). If this is the case, note that consolidating to a global report suite will not grant you additional variables or events for tracking.</li></ul>|
| **Which settings on virtual report suites are inherited from the parent report suite?** | A virtual report suite inherits most of the service levels of the parent report suite, such as eVar settings, Processing Rules, Classifications, etc.  The following settings are NOT inherited:<ul><li>Report suite ID</li><li>Report suite name </li><li>Permission groups (virtual report suites can be assigned to their own permission groups)</li></ul>**Note**:  This does not include most user-created entities like Bookmarks, Dashboards, Scheduled Reports, etc.; these items are not inherited from the parent and can be created and used against the Virtual report suite specifically (more detail in the next question).|
| **How does working with a virtual report suite differ from working with a base report suite in the Analytics UI?** | Once created, a virtual report suite is treated just like a base report suite throughout the UI and is generally supported for most extended features. For example:<ul><li>Virtual report suites show up in the Report Suite selector and can be selected individually just like any other base report suite.</li><li>Reports, Bookmarks, Dashboards, Targets, Alerts, Segments, Calculated Metrics, etc. can all be created against a virtual report suite and behave independently of the parent.</li><li>Virtual report suites can be individually permissioned just like any other report suite.</li><li>Segments can still be applied when running reports in the context of a Virtual report suite; they will automatically be stacked with the virtual report suite's segment(s) when the report data is being retrieved.</li></ul> |
| **How are virtual report suites treated in the Admin Console and Admin API? Can I save features against them like base report suites?** | No, virtual report suites are not supported for most Admin features. As mentioned above, a Virtual report suite inherits most service levels and features from the parent (for example, eVar settings, Processing Rules, Classifications, etc.), so to make a changes to these inherited settings on a Virtual report suite, you must alter the parent report suite.<br>As a result, virtual report suites are shown in the UI only here:<ul><li>The Virtual report suite manager, where you create and edit virtual report suites. (Analytics > Components > Virtual report suites)</li><li>The Adobe [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). For using a Virtual report suite in reports or throughout Adobe Analytics, permissions work just like they do for a report suite. That means the Virtual report suites show up in the selection tool for a product profile, and are assigned to product profiles just like report suites.</li></ul>**Note**:  When you use the Web Services API and attempt to save Feature settings against a Virtual report suite, an exception will be thrown. Features can only be set against a base report suite.|
| **I checked "start new visit on launch." Why do I see visits still much higher than launches?** | When "start new visit on launch" is checked, the timeout still applies. So, if a user is using the app for ten minutes with a one minute break in between each action, a new visit starts on launch, then nine additional visits are created when the visit times out. To keep launches and visits as close as possible when using the "start new visit on launch" option, you should use a timeout that is longer than the session timeout set in the SDK. |
| **I set "start new visit on launch" and set a longer timeout than my SDK. Why are my launches still much lower than visits?** | If the timeout is higher than the value set in the SDK, it is very likely that your app is sending in hits while in the background and these hits are registering as new visits. Check for this by using the hit type dimension on the parent report suite to see if there are any background hits.<br>**Note**: Background and foreground hits are only differentiated in version 4.13.6 and higher of the SDK. If you are on a lower version, all hits show as foreground. If you are on the correct version of the SDK, you should enable the "Prevent background hits from starting a new visit" setting.    Note: If you have disabled legacy processing for background hits in the admin console, they will not show up in the parent report suite but will appear in the virtual report suite.|
| **What version of the SDK do I need to have to track background hits?** | You must be on version 4.13.6 or higher of the SDK. |
| **How do I find out a Virtual Report Suite's ID?** | <ul><li>By opening a Workspace project, clicking the Report Suite Selector and searching for the name of a virtual report suite in the search box. The ID appears underneath the name in the search results:<br>![Virtual report suite ID](assets/vrs-id.png)</li><li> Or, programmatically, in the [Virtual report suite API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/vrs.md).</li></ul> |
