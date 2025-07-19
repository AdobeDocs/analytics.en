---
title: Technical documentation updates for Adobe Analytics
description: Notable updates to the Adobe Analytics documentation set.
short-title: Analytics documentation updates
feature: Release Notes
exl-id: fe8e3c4c-6782-46f7-8e28-4f8f54807788
mini-toc-levels: 3
---
# Technical documentation updates for Adobe Analytics

Content updates for the Adobe Analytics documentation set since January, 2019.

* For information on [!UICONTROL Customer Journey Analytics], go [here](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html).
* For information on the Streaming Media Collection, see [Measuring audio and video in Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html).

## Details on major documentation updates

### 2025 {#year2025}

| Feature | Description |
| --- | --- |
| **July 2025** | |
| Processing rules| The documentation for processing rules has been fully redone, providing more details on the interface and current use cases. |
| Debugger | New article on how to enable, use and disable the project debugger in Analysis Workspace. |
| Flow visualization performance recommendation | Added information stating that leaving more than 10 nodes expanded in a single flow visualization can affect reporting time. |
| Review and updates | Review and update of Analysis Workspace documentation. Where appropriate, the documentation is now in sync with the Customer Journey Analytics documentation on Analysis Workspace. | 
| **June 2025** | |
| New shortcut actions | New keyboard shortcuts in Analysis Workspace now allow you to [move Workspace panels](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md#move-panel-actions) up and down in a project.  | 
| **March 2025** |  |
| Analytics inventory | [Analytics Inventory](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) provides a comprehensive overview of your Adobe Analytics environment, including the number of projects and components, report suites, users, and more. | 
| Customer Journey Analytics upgrade guide | Lets you generate a [step-by-step guide](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations?lang=en#recommended-upgrade-steps-for-most-organizations) for upgrading from Adobe Analytics to Customer Journey Analytics. |
| Clarified date formatting in Data Warehouse exports | Time-based dimension values in Data Warehouse exports have non-standard date formatting. Added information explaining how to interpret date values from Data Warehouse exports. <p>See [Dimensions supported in a different way (non-standard date formatting)](/help/export/data-warehouse/component-support.md#dimensions-supported-in-a-different-way-non-standard-date-formatting) in [Component support in Data Warehouse](/help/export/data-warehouse/component-support.md).</p> |
| Updated information about IP exclusions | Added information explaining that [IP exclusions](/help/admin/admin/exclude-ip.md) can take up to 5 minutes before they take effect, and that changes apply only to new hits (data captured prior to the exclusion being set is not affected). <p>Also updated the layout of content to improve readability.</p>  |
| **February 2025** |  |
| Updated information about pausing and reactivating a data feed | When [pausing and reactivating a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#activate-a-data-feed), clarified the behavior for live feeds. Data processing does not occur from the time the feed is paused to the time it is reactivated.  |
| Changed Transaction ID retention period |  The Transaction ID retention period of 90 days was extended to 25 months. The transactionID variable uniquely identifies a transaction so the hit can tie to data uploaded through Data Sources. Learn more [here](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid?lang=en) and [here](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid?lang=en). |
| Livestream API - Client implementation | Use the [Livestream client implementation](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) to consume Livestream data. |
| Update to Classifications API  |  You can now [remove individual classification fields or keys from the server](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/). This provides an alternative to deleting an entire classification dataset with the DELETE method. |
| **January 2025** |  |
| Data Feeds API reference  |  The [reference for the Data Feeds API](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) is now available.|
| New documentation on Scheduling in the new Report Builder | [Scheduling](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/schedule-reportbuilder) not only allows you to schedule your new Report Builder workbooks. In addition, it lets you retrieve the metadata on old scheduled tasks when you convert legacy workbooks. |
| Improvements to Reports (also known as Templates) in Analysis Workspace | Various improvements are now available for Reports (also known as [Templates](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/templates/use-templates?lang=en)) | 


### 2024 {#year2024}

| Feature | Description |
| --- | --- |
| **October 2024** |  |
| New information about Request factors in Analysis Workspace Performance | A new [Request factors](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md#request-factors) section in the [Optimize Analysis Workspace performance](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md) article explains how requests are processed and the various factors that influence processing times. |
| New Report Builder | [New documentation](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview) for the streamlined Report Builder add-in that is supported on Mac, Windows, and web browsers. |
| **August 2024** | |
| Alerts manager | Streamlined documentation about the [Alerts manager](/help/components/c-alerts/alert-manager.md). Updated for clarity and accuracy. | 
| **July 2024** | |
| Success events | Streamlined documentation about [success events](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md). Updated for clarity and accuracy. | 
| At least one account type must be selected when managing locations | Clarified that when administrators are [limiting the account types that are used for export and import](/help/components/locations/locations-manager.md#limit-the-account-types-that-are-available-to-users), at least one account type must be selected. |
| Added information about quick calculated metrics | Updated information in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md) to clarify the difference between [calculated metrics that are created in the calculated metrics builder](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and [those that are created as quick calculated metrics within a single project](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). Also added more details about hose to create quick calculated metrics.<p>Calculated metrics that are created in the calculated metrics builder are available in the component list and can be applied to projects throughout the organization, while calculated metrics that are created as quick calculated metrics are available only within the project where they were created.</p><p>Also updated information in [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) to make similar clarifications.</p> |
| Added threads.net to the 'Referrer type' dimension | Added threads.net to the list of social networks that are used in the ['Referrer type' dimension](/help/components/dimensions/referrer-type.md). |
| Updated documentation for managing data feeds | Updated information in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md) to improve clarity. <p>Updates include:</p><ul><li>Created separate sections for various tasks in order to make the information easier to scan and consume.</li><li>Added information about changes to the behavior of live feeds that are reactivated. These changes are currently in Limited Availability and are not yet available to all customers.</li><li>Added information stating that data feeds must have a status of Active before they can be deleted.</li>  | 
| Updated common error messages | Made minor updates to the [common error messages](/help/analyze/analysis-workspace/workspace-faq/error-messages.md). |
| **June 2024** | |
| Updated product name that refers to streaming media features | Replaced instances of "Media Analytics" and "Streaming Media" with the name "Streaming Media Collection Add-on" and "Streaming Media Collection" when referring to the set of streaming media features that collect streaming media data and surface it in Analysis Workspace. <p>These updates are available throughout the Adobe Analytics documentation as well as the [Streaming Media Collection documentation](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-overview).</p> |
| Improved alerts documentation | Updated and improved documentation about alerts. These updates include information about [creating alerts](/help/components/c-alerts/alert-builder.md), [managing alerts](/help/components/c-alerts/alert-manager.md), and [overview information](/help/components/c-alerts/intellligent-alerts.md). |
| Deprecated `cookieDomainPeriods` | Now that AppMeasurement automatically detects the correct domain to set cookies on, the [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) variable is deprecated. | 
| Retire Data Connectors documentation | Moved the Data Connectors end-of-life page to [Discontinued products](https://experienceleague.adobe.com/en/docs/discontinued/using/data-connectors). |
| **May 2024** | |
| Required information when using organization policy constraints with Google Cloud Platform in Data Feeds and Data Warehouse | Added the Adobe-owned Google Cloud Platform organization ID to the [Data Feeds](/help/export/analytics-data-feed/create-feed.md) and [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) documentation. <p>This information is required only for organizations that are using [Organization policy constraints](https://cloud.google.com/storage/docs/org-policy-constraints) in Google Cloud Platform.</p> | 
| Documentation about adding components to projects | Added general information about how to [add the various types of components to projects in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md). |
| Updated Advertising Analytics documentation | Updated documentation in line with updates made to the [Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-workflow.md) user interface. | 
| Explicit map XDM object variables to context data variables | Documented the capability to [explicitly set context data variables using XDM object variable mapping](/help/implement/aep-edge/xdm-var-mapping.md#explicit-mapping). | 
| New documentation for upgrading from Adobe Analytics to Customer Journey Analytics | For organizations upgrading from Adobe Analytics to Customer Journey Analytics, there are multiple upgrade options and many considerations to keep in mind based on an organization's current Adobe Analytics implementation and long-term goals.<p>New documentation resources are now available to help you better understand:</p><ul><li>The various upgrade paths that exist</li><li>Which upgrade paths are available based on an organization's current Adobe Analytics implementation</li><li>The advantages and disadvantages of each upgrade path</li><li>Step-by-step guidance for each upgrade path</li><li>Considerations for handling historical data</li><li>And more!</li></ul><p>[Get started with the upgrade to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted).</p> |
| Updated documentation about custom date ranges |  Updated screenshots and procedures related to [creating custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) in order to match the current product features and design.  | 
| **April 2024** | |
| Removed documentation related to "Owner" in Classification sets |  The "Owner" filter and column was removed from the [Classification set manager](/help/components/classifications/sets/manage/set-manager.md) and the "Owner" field was removed from the [Classification set settings](/help/components/classifications/sets/manage/settings.md). <p>The documentation was updated to remove this filter, column, and field.</p>  | 
| Removed collapsible sections in documentation about configuring cloud import and export locations | Removed collapsible sections in [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md) for information explaining cloud account types. | 
| **March 2024** | |
| AppMeasurement update | [Release notes](/help/implement/appmeasurement-updates.md) on AppMeasurement update v2.26.0.<br/>Includes reference to and update of [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) config variable documentation. | 
| Usage information regarding the "Used in" column is available only starting in September 2023.| Clarified that usage information regarding the **Used in** column on the [projects landing page](/help/analyze/landing.md) goes back only as far as September 2023.  | 
| **February 2024** | |
| Updates to information about managing Data Warehouse requests | Clarified that, by default, users can view only the requests they create when [managing Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). |
| Updates to project sharing documentation | Added information about how to [view shared projects](/help/analyze/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>Also streamlined information about [sharing individual or multiple projects](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).</p> |
| Added permission requirements for uploading files to Azure SAS and Azure RBAC in Data Warehouse and Data Feeds | Added exact permission requirements for uploading files to Azure SAS and Azure RBAC when [configuring destinations for Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) and [when configuring destinations for Data Feeds](/help/export/analytics-data-feed/create-feed.md). |
| Added permission requirements for uploading files to Amazon S3 and GCP buckets in Data Warehouse and Data Feeds | Added exact permission requirements for uploading files to Amazon S3 and Google Cloud Platform buckets when [configuring destinations for Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) and [when configuring destinations for Data Feeds](/help/export/analytics-data-feed/create-feed.md). |
| **January 2024** | |
| Component migration applies to individual IMS orgs | Clarified that [component migration](/help/admin/admin/component-migration/component-migration.md) does not support cross-IMS org migration. |
| Clarified that certain information is available only to administrators  | Added information stating that the "Last used" and "Used in" columns that are described in [Calculated metrics manager](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) and [Segments manager](/help/components/segmentation/segmentation-workflow/seg-manage.md) are available only to system administrators. |
| Updates to Media average minute audience documentation | Updated information in [Media average minute audience panel](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md) to improve clarity.<p>Improvements include:</p> <ul><li>Improved organization of information</li><li>Added steps to indicate task-based information</li></ul> |

### 2023 {#year2023}

| Feature | Description |
| --- | --- |
| **December 2023** | |
| Improved bot rules documentation | Updated information in [Understand and configure bot rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) to improve clarity.<p>Improvements include:</p> <ul><li>Updated article title to be more descriptive</li><li>Improved organization of information</li><li>Added steps to indicate task-based information</li><li>Added more details about CSV file requirements when uploading bot rules</li></ul> |
| New Reports section | Added a new Reports section that includes information about [Use templates](/help/analyze/analysis-workspace/templates/use-templates.md) and [creating company templates](/help/analyze/analysis-workspace/templates/create-templates.md). |
| Updates to Anomaly Detection and Contribution Analysis documentation | The documentation for Anomaly Detection and Contribution Analysis was previously located in a section about Virtual Analyst. The following changes were made: <ul><li>The term Virtual Analyst was removed from the documentation.</li><li>The section about [Anomaly Detection](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) was moved directly beneath the Analysis Workspace section.</li><li>The Contribution Analysis documentation was merged into the Anomaly Detection documentation.</li></ul> |
| "Attribution IQ" changed to "Attribution" | Changed all instances of "Attribution IQ" to "[Attribution](/help/analyze/analysis-workspace/attribution/overview.md)" throughout the documentation. |
| **November 2023** | |
| Updates to Activity Map activation/enablement topic | Added [Web SDK](/help/analyze/activity-map/getting-started.md) (both manual and via Adobe Experience Platform tags extension) content. |
| **October 2023** | |
| Added log information to Reporting Activity Manager | Added information that any [cancellations and subsequent restrictions of reporting activity](/help/admin/admin/reporting-activity-manager/reporting-activity-cancel-requests.md) in the Reporting Activity Manager are captured in the [Logs](/help/admin/admin/logs.md). |
| Updates to Data Warehouse component support | Added availability for some components and removed availability for others for Data Warehouse. These changes are reflected in [Component support in Data Warehouse](/help/export/data-warehouse/component-support.md). <ul><li>Added support for the Visit Depth dimension (removed Visit Depth from the list of dimensions not supported)</li><li>Removed support for Participation metrics (added Participation metrics to the list of metrics not supported)</li><li>Added support for the following time-based dimensions: Year, Quarter, Month, Week, Day, Hour, and Minute (removed these dimensions from the list of dimensions not supported) <p>Previously, Data Warehouse supported these dimensions only in the first column of a Freeform table when Granularity was selected. Now these dimensions are always supported.</p><p>However, the output of dates is non-standard when using these dimensions. The year is offset by 1900, and months are zero-based.</li></ul> |
| **September 2023** | |
| Updated structure of articles for the Media Playback Time Spent panel | Removed the folder called Media Playback Time Spent, and combined the contents of the folder into a single article: [Media Playback Time Spent panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md). <p>This change is more in line with the documentation for other panels.</p> |
| Get started content enhancements | Added information outlining key getting-started tasks and resources for administrators, analysts, end users, and developers. The following new articles are now available: <ul><li>[Get started (by role)](/help/analyze/get-started/get-started-by-role.md)</li><li>[Understand the Analytics interface](/help/analyze/get-started/analytics-interface.md)<li>[Use cases](/help/analyze/get-started/use-cases.md)</li></ul> |
| Improvements to Reporting documentation for the Streaming Media Collection | Reorganized some of the content in the Reporting section of the the Streaming Media Collection guide, including consolidating the API documentation in its own section and adjusting the order of some articles. <p>Renamed the Media Workspace Templates article to [Media reports in Workspace](https://experienceleague.adobe.com/docs/media-analytics/using/media-reports/media-workspace-templates.html) to better align with the in-product naming. </p> |
| **August 2023** | |
| Data feed clarification | Updated [the definition of Start & End dates](/help/export/analytics-data-feed/create-feed.md) to clarify that when processing data feeds for historical data, you can set the start date to any date in the past when data is being collected. |
| Adobe Experience Platform Edge Network data handling | Added content around how Adobe Analytics [handles data from the Edge Network](../implement/aep-edge/overview.md). |
| Media Playback Time Spent panel | Updated content for  [Media Playback Time Spent panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) to improve readability. |
| Moved content about managing scheduled projects | Created a new article in the Analytics Components Guide called [Scheduled projects](/help/components/scheduled-projects-manager.md). This content was previously located in the [Schedule projects](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) article in the Analytics Tools Guide. |
| Compare implementation methods | Updated documentation that compares different implementation methods. [Learn more](../implement/prepare/comparison.md) | 
| Clarified that configuring SFTP for Data Feeds does not require Adobe Customer Care | Clarified in [Send Adobe data to an external FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-transfer.md) that customers do not need to engage Adobe Customer Care in order to configure SFTP for Data Feeds. <p>Also added a note that SFTP is no longer recommended, and that customers should use a cloud destination when configuring Data Feeds.</p> | 
| Documentation improvements for the Streaming Media Collection | The following documentation improvements were made for the Streaming Media Collection: <ul><li>Updated the [general overview](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html) to improve clarity and to include information related to Customer Journey Analytics.</li><li>Updated the [implementation overview](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html) to clearly differentiate between Edge implementations and Analytics-only implementations. Also included diagrams to illustrate the various implementation methods.</li><li>Added prerequisites specific to [Edge implementations](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/edge-recommended/prerequisites-edge.html) and [Analytics-only implementations](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/analytics-only/prerequisites-analytics.html). Also updated the [general prerequisites](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/prereqs.html).</li><li>Updated tables in the [Get Media SDKs, Extensions using Tags, and OTT SDKs](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/download-sdks.html) article to include new columns for *Supported solutions* and *Implementation method*.</li><li>Streamlined content and organization of articles in the [Implementation](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html) area of the documentation. This included categorizing implementations by Edge implementations and Analytics-only implementations.</li><li>Removed an extra level of hierarchy that wasn't needed under [Tracking](https://experienceleague.adobe.com/docs/media-analytics/using/tracking/track-core-overview.html) and added redirects for changed URLs in this section.</li><ul> |
| **July 2023** | |
| Adobe Experience Platform Edge Network API | Added more comprehensive documentation on when and how to implement data collection with Adobe Analytics using the [Adobe Experience Platform Edge Network API](../implement/aep-edge/api/overview.md). For example, implementing data collection with Adobe Analytics in desktop applications, IoT devices, set top boxes. | 
| Global company ID | Documented [how to find the global company ID](../admin/admin/company/web-services-admin.md) for the Analytics company you are logged into. This ID is required for Analytics 2.0 APIs. |
| Updated FTP size limit | Changed the default [FTP data storage limit](/help/export/ftp-and-sftp/ftp-limits.md) to 100 GB. |
| New AppMeasurement variable | The variable `decodeLinkParameters` accommodates edge cases where implementations encode multi-byte characters in link tracking variables. [Learn more](../implement/vars/config-vars/decodelinkparameters.md) | 
| Configuring cloud account storage locations for ingesting classification data | You can now manage cloud account storage locations that are used for classification set automation. [Learn more](/help/components/locations/configure-import-accounts.md)| 
| Data Repair filter enhancements | Three filtering improvements were added to Data Repair. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)|
| **June 2023** | |
| New features for classification sets | [Classification sets](/help/components/classifications/sets/overview.md) have been updated with several new features:<ul><li>**Consolidations**: Combine classification sets into a single consolidated classification set. The consolidated classification set can be used like other classification sets or as a lookup data set in Customer Journey Analytics. [Learn more](../components/classifications/sets/consolidations/manage.md)</li><li>**Rules**: Automatically classify values based on rules in the classification set. [Learn more](../components/classifications/sets/manage/rules.md)</li><li>**Automated import**: Automatically import classification data from cloud storage destinations. [Learn more](../components/classifications/sets/manage/schema.md)</li></ul> |
| Calculated metrics updates | Updates were made to various articles related to calculated metrics, including updating screen shots and steps in procedures. These changes were made to bring documentation inline with current Adobe Analytics functionality. |
| Secure destinations for data feed export | Data feeds can now be sent to the following cloud storage destinations:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Destinations that were previously available (FTP, SFTP, S3, and Azure Blob) are no longer recommended. [Learn more](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) | 
| Bot reporting in Workspace | Bot reporting is now available in Analysis Workspace. This feature comes with several additions:<ul><li>A new dimension: [Bot name](/help/components/dimensions/bot-name.md)</li><li>Two new metrics: [Bot page views](/help/components/metrics/bot-page-views.md) and [Bot occurrences](/help/components/metrics/bot-occurrences.md).</li><li>A new calculated metric template: [Bot page views ratio](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>A new Workspace report: Bot reporting</li></ul>The new dimension and metrics contain data that is backfilled starting in March 2023. | 
| **May 2023** | |
| Deep Linking (Mobile App) documentation | Allows users to send links to scorecards that will lead them directly to the scorecard project in the app. [Learn more](/help/analyze/mobile-app/create-scorecard.md#shareable-link) |
| Documentation for updated Home screen for the Analytics dashboards app (Mobile App)| The new updated Home screen allows you to view all of your scorecards in one consolidated scorecard list. [Learn more](/help/analyze/mobile-app/executive.md#use-dashboards) |
| Spectrum icons | Replaced, where appropriate, screenshots of user interface icons in the documentation with references to the equivalent icons in [Adobe's Spectrum Design System](https://spectrum.adobe.com/page/icons/). |
| Reporting Activity Manager | Updated this beta documentation, specifically the section on [Viewing reporting activity for individual report suites](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html#view-reporting-activity-for-individual-report-suites). |
| Analysis Workspace overview | Updated [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md) to include more general overview information and links to relevant content. |
| Create projects | Created a new article that explains in detail how to [Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) in Analysis Workspace. |
| Sort components in the left rail | Added information about sorting the list of components in the left rail. See the "Search, filter, and sort the component list" section in [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
| Delete rows containing dynamic dimensions from a Freeform table | Added information about how to quickly delete specific rows that contain dynamic dimensions using the x icon. See the "Quickly exclude specific rows from a table" section in [Filter and sort tables](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).|
| Button to add a visualization within a panel | Added information about a new button at the bottom of each panel in Analysis Workspace that allows you to quickly add a visualization. See the "Add visualizations to a panel" section in [Visualizations overview](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md). |
| **April 2023** | |
| Transfer user assets and set account expirations | Added information about how to [transfer user assets and set account expirations](/help/admin/admin/user-management2/users-assets.md). |
| 2 new endpoint guides for the Adobe Analytics 2.0 API |<ul><li>[Analytics Dimensions API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[Analytics Metrics API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> |
| Project segments (Ad hoc and quick segments) | Streamlined docmentation about project segments and removed duplicated information. The steps for creating ad hoc segments are now combined with the steps for [creating quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md).|
| Dynamic lookups | Additional information around [Dynamic lookups](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md) is added. Previously, Information only existed for mobile attributes, which is one of several dynamic lookups. |
| **March 2023** | |
| Web SDK support for Activity Map | Updated [Implement Adobe Analytics](/help/implement/home.md). |
| Traffic variables (props) overview | Added sections and step-by-step procedures to clarify and improve article content. Merged content from an article titled, "Enable traffic variable reports" and removed that article. See [Traffic variables (props) overview](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md). |
| Internal URL filters | Added sections and step-by-step procedures to clarify and improve article content. See [Internal URL filters](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). |
| Create data stories in mobile scorecards | A [data story](/help/analyze/mobile-app/create-scorecard.md#create-data-stories) is a collection of supporting data points, business context, and related metrics built around a central theme or metric. |
| Default calculated metrics | Added content explaining the [default calculated metrics provided by Adobe](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md). |
| Data Dictionary | <p>Added new documentation for the Data Dictionary, including an [Overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md), [Viewing](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md), [Editing](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md), and [Monitoring](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md) the Data Dictionary.</p><p>Information in [Adding component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md) was updated to account for Data Dictionary functionality.</p>  |
| Link sharing for projects (no login required) | <p>Updated existing documentation to explain how to share a read-only link of a project with people who do not have access to Analysis Workspace.</p> <p>Updated user documentation includes [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md) and [Create shareable links](/help/analyze/analysis-workspace/curate-share/shareable-links.md).</p> <p>Options for administrators were added to [Preferences](/help/analyze/analysis-workspace/user-preferences.md).</p>  |
| **February 2023** | |
| Implementation | Updated content on how to [implement Adobe Analytics for web and mobile](../implement/home.md). |
| Workspace calendars and date ranges | Updated content to describe relative date ranges, formula calculation updates, and calendar UI changes. See [About relative panel date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md). |
| Mobile scorecards | New documentation section to describe how to show and hide comparison date ranges. See [Show comparison date ranges](/help/analyze/mobile-app/create-scorecard.md) in Customer Journey Analytics.  |
| 1.4 API | The [Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/) received a full rewrite, and is now published on Adobe Developer. |
| Tracking across implementation types | Updated the use case [Track across different implementation types](../implement/use-cases/cross-type-implementation.md) to accommodate the Experience Cloud ID Service. |
| **January 2023** | |
| Filter and sort tables | Updated content (including adding procedures and explaining available options) in the [Filter and sort tables](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) article. Renamed this article from "Pagination, filtering and sorting tables." |
| Folders | Dedicated pages for [Folders management](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).  |
| User preferences | Many additional user preferences are now available in [Preferences](/help/analyze/analysis-workspace/user-preferences.md).  |
| Auto-save for projects | Updated content to include auto-save functionality in [Save projects](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).  |
| Landing page | New [landing page updates](/help/analyze/landing.md) |

### 2022 {#year22}

| Feature | Description |
| --- | --- |
| **November 2022** | |
| Consent management variables | Dedicated pages for [Consent management opt-in](/help/components/dimensions/cm-opt-in.md) and [Consent management opt-out](/help/components/dimensions/cm-opt-out.md). |
| Multi-currency refresh | Pages around [Multi-currency support](/help/implement/vars/config-vars/currencycode.md) are updated. |
| **October 2022** |  |
| Data Workbench | [End-of-life announcement](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) |
| Client hints | New [overview and FAQ](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html). |
| Key Metric Summary | New topic on the [Key metric summary](/help/analyze/analysis-workspace/visualizations/key-metric.md) visualization. |
| Classification sets |  The new user [Classification sets](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html) experience provides a single interface to manage classifications and rules and improves visibility of customer-owned classification data. |
| Mobile app: Custom detail views | New topic on [custom detail views](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html). |
| VISTA | New page explaining the basics of [VISTA rules](/help/technotes/vista.md). |
| **September 2022** | |
| Combo charts | New topic on the [combo charts](/help/analyze/analysis-workspace/visualizations/combo-charts.md) visualization. |
| Updated plug-in | Updated version of the [getvalonce](/help/implement/vars/plugins/getvalonce.md) implementation plug-in. |
| New configuration variable | Documentation on [collectHighEntropyUserAgentHints](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) |
| High-entropy client hints | New topic on how Adobe is using [client hints](/help/technotes/client-hints.md) in addition to User-Agent to determine device information. |
| Processing order | Various help pages have been aggregated to provide a single help topic on [Processing order](/help/technotes/processing-order.md). |
| **August 2022** | |
| Support for List Variables in XDM for Edge Collection | Enables customers collecting data using the Web SDK to use XDM to specify list variable contents. [Learn more](../implement/vars/page-vars/list.md#list-variables-using-the-web-sdk)| 
| Use of SKU field in XDM for Edge Collection when setting product string Variables | Enables customers collecting data using the Web SDK to use the SKU value to set the product field in the products variable. [Learn more](../implement/vars/page-vars/products.md#products-using-the-web-sdk) |
| **June 2022** |  |
| Merchandising variables in XDM for Edge Collection |  Documentation on [support for Merchandising variables in XDM for Edge Collection](/help/components/dimensions/evar-merchandising.md) |
| Experience Platform Edge documentation | New articles on Adobe Analytics implementation via [Web SDK](/help/implement/aep-edge/web-sdk/overview.md), [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md), and [Edge API](/help/implement/aep-edge/api/overview.md). |
| Updated Flow visualization documentation | Based on the [new UI](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) |
| Documentation on sharing annotations in Mobile scorecards | You can display [annotations that are created in Workspace in Mobile Scorecards](/help/analyze/analysis-workspace/components/annotations/mobile-annotations.md). |
| **May 2022** | |
| Populate Lifecycle dimensions and metrics through the Edge Network | Mobile Lifecycle data sent to the Edge Network now appears in Analytics reporting. See [Analytics variable mapping](/help/implement/aep-edge/xdm-var-mapping.md) for details on which XDM fields map to existing mobile Lifecycle reporting. |
| **April 2022** | |
| Adobe Analytics landing page updates | Updates to the joint [Workspace/Reports & Analytics landing page](/help/analyze/landing.md) that improves usability and ease of navigation. |
| New topic on [!UICONTROL Page Summary] panel | [Page summary panel](/help/analyze/analysis-workspace/c-panels/page-summary.md) |
| New topic on [!UICONTROL Next/Previous item] panel | [Next/previous dimension item panel](/help/analyze/analysis-workspace/c-panels/next-previous.md) |
| **March 2022** | |
| New topic on supported HTTPS encryption algorithms | Supported HTTPS encryption algorithms for customers with cipher security level set to "High". |
| New documentation on Annotations in Workspace | [Annotations in Workspace](/help/analyze/analysis-workspace/components/annotations/overview.md) enable you to effectively communicate contextual data nuances and insights to your organization. |
| Adobe Analytics landing page updates | [Updates](/help/analyze/landing.md) to the joint Workspace/Reports & Analytics landing page that improves usability and ease of navigation. |
| [!UICONTROL Next item] or [!UICONTROL Previous item] Workspace panel | This panel allows you to explore items that follow or precede a dimension item of your choice. |
| [!UICONTROL Page Summary] Workspace panel | This panel provides a deep-dive analysis for a page of your choosing. |
| New topic on pausing older scheduled reports | Effective **April 15, 2022**, Adobe intends to pause all scheduled reports that have a creation date greater than two years|
| **February 2022** | |
| Mobile scorecard project preview mode | The [preview mode](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#preview) allows you to preview the experience before you save and share a scorecard.  |
| API projects endpoint | Add, edit or delete Analysis Workspace projects using the API. [Learn more](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 
| Updated topic on pausing older scheduled Report Builder tasks |  **Effective April 15, 2022**, Adobe intends to [pause all scheduled Report Builder tasks that were created more than two years ago](/help/analyze/legacy-report-builder/r-arb-scheduled-reports.md). |

### 2021 {#year2021}

| Feature | Description |
| --- | --- |
| **October 2021** |  |
| October 21, 2021 | New documentation on [Quick Segments](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html) in Analysis Workspace |
| October 21, 2021 | New documentation on the [Media Playback Time Spent](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-playback-timespent/media-playback-time-spent.html) panel in Analysis Workspace. |
| October 7, 2021 | New documentation on [visualizations for mobile scorecards](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#apply-visualizations) |
| **August 2021**|  |
| August 18, 2021 | Revised top-level structure and consolidated to a single [Landing page](https://experienceleague.adobe.com/docs/analytics.html) |
| August 18, 2021 | New topic on [A4T and virtual report suites](/help/components/vrs/vrs-a4t.md) |
| August 18, 2021 | New topic on [Attribution best practices](/help/analyze/analysis-workspace/attribution/best-practices.md) |
| August 5, 2021 | New topic on [Count repeat instances](https://experienceleague.adobe.com/docs/analytics/components/metrics/count-repeat-instances.html) |
| August 5, 2021 | Updated classifications documentation on [templates](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-download-saint-data.html), [browser import](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html), and [browser export](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-export.html) to indicate options unavailable for report suites that are enabled for the New Classification Architecture. |
| August 2, 2021 | Updated multiple pages to reflect the re-branding of [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html) |
| **July 2021** |  |
| July 23, 2021 | New in-depth discussion of [Merchandising eVars](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html) |
| July 15, 2021 | Added new documentation on the new [Adobe Analytics landing page](/help/analyze/landing.md) |
| **June 2021** |  |
| June 15, 2021 | Updated [Marketing Channels best practices](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html) |
| June 3, 2021 | Updated the documentation to better explain [Data Feed Implementation](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) and [here](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html#BucketOwnerFullControl). |
| May 25, 2021 | Updated the documentation on [eVar case sensitivity in reporting](https://experienceleague.adobe.com/docs/analytics/components/dimensions/evar.html). |
| May 13, 2021 | Updates to [Data Warehouse API requests](https://developer.adobe.com/analytics-apis/docs/1.4/guides/reporting/data-warehouse/). They now support "Hours". |
| **March 2021** | |
| March, April 2021 | Updates to Adobe Analytics dashboards [Executive guide](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/executive.html) and [Curator guide](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html) |
| March 25, 2021 | New documentation on the [!UICONTROL Components] > [!UICONTROL User preferences] page. It enables you to manage [!UICONTROL Analysis Workspace] settings and its related components for your user. [!UICONTROL User preferences] applies to all new projects and panels. <br>**Note:** the following settings have moved to the [!UICONTROL User preferences] page:<ul><li>Report Settings: Thousands separator (now called _Number format_)</li><li>Report Settings: CSV separator</li><li>Workspace projects: Help > Enable tips</li><li>Workspace projects: Blank panel _Start new projects with this panel_ option</li></ul> |
| March 25, 2021 |[!UICONTROL Histogram Smart Bucket Prediction] helps with high-cardinality-metrics histograms by automatically identifying the right width and number of buckets for your data spread. For low-cardinality metrics, the visualization behaves the same as it did previously. |
| March 25, 2021 | [Data Repair API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) updates (filtering for URLs, query strings, at signs, and more) |
| March 25, 2021 | New [Usage Log API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/usage-logs.md) documentation |
| **February 2021** | |
| February 4, 2021 | Component Selection: The drop-down/drop zone component found in [!UICONTROL Quick Insights] was added to all drop zones in [!UICONTROL Workspace]. This enhancement lets you pick from a drop-down list of compatible components or continue to use the space as a drop zone. |
| **January 2021** | |
| January 14, 2021 | Added language selection option to Analytics dashboards documentation. |
| January 14, 2021 | Added documentation on how you can add images to Workspace projects by referencing a public image URL. |
| January 14, 2021 | Combined source & settings manager for Workspace visualizations: The [!UICONTROL Data Source] manager (dot) and settings manager (gear) for visualizations have been combined into a single popover, so you can easily manage your source and settings from the same location. |

### 2020 {#year2020}

| Feature | Description |
| --- | --- |
| **December 2020** | |
| December 7, 2020 | Amended all relevant pages to include or substitute the "adobedc.net" endpoint. |
| December 8, 2020 | Updates to the [Create new project](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html) page in Workspace. |
| **November 2020** | |
| November 24, 2020 | Updates to [Panel Overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) page in Workspace. |
| November 24, 2020 | New implementation review documents: <ul><li>[Full Implementation Review](https://experienceleague.adobe.com/docs/analytics/implementation/review/full-review.html)</li><li>[Focused Implementation Review](https://experienceleague.adobe.com/docs/analytics/implementation/review/focused-review.html)</li></ul> |
| November 24, 2020 | Updated Analysis Workspace [Visualizations overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) page. |
| November 12, 2020 | New page on [Inherited Adobe Analytics Implementation](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/existing-implementation.html). |
| November 2, 2020 | Updated document on [FTP for classifications](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html). |
| **October 2020** | |
| October 23, 2020 | Workspace Line visualization: [Moving average trendline option](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html): This setting was added to [!UICONTROL Line] visualization trendline settings. Also known as a rolling average, a moving average uses a specific number of data points (determined by a **[!UICONTROL Periods]** selection), averages them, and uses the average as a point in the line. |
| October 23, 2020 | The Workspace [Performance Help page](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html) shows the different factors that impact project performance and links to tips for optimization. |
| October 23, 2020 | Added enhancements to Adobe Analytics dashboads documentation. In the mobile scorecard in Workspace, the styling of the scorecard now matches the app. |
| **September 2020** | |
| September 17, 2020 | [Download 50K items for a single dimension](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html#download-items): You can now download 50,000 items for a single dimension in a freeform table, with segments and filters applied. This allows you to access more than the 400 rows of data outside of Analysis Workspace. |
| September 17, 2020 | [Enhancements to Line visualization](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html): <ul><li>You can show or hide the X-axis and Y-axis of any [!UICONTROL Line] visualization. This can be especially helpful when your [!UICONTROL Line] visualizations are more compact.</li><li>You can overlay a minimum and maximum value label on any Line visualization to quickly highlight the peaks and valleys in a metric.</li><li>You can overlay different regression trend lines on any Line visualization to more easily see the trend in the data. Options include [!UICONTROL Linear], [!UICONTROL Logarithmic], [!UICONTROL Exponential], [!UICONTROL Power] and [!UICONTROL Quadratic].</li></ul> |
| September 17, 2020 | New date ranges in Workspace: We added 5 new date ranges so you can choose from date ranges that do not include partial day data from today: Last 7 full days, Last 14 full days, Last 30 full days, Last 60 full days, Last 90 full days |
| September 17, 2020 | New documentation on [Media Concurrent Viewer panel in Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers.html) |
| **August 2020** | |
| August 31, 2020 | Added enhancements to [field-based stitching documentation](https://experienceleague.adobe.com/docs/analytics/components/cda/field-based-stitching.html) in Cross-Device Analytics. |
| **July 2020** | |
| July 21, 2020 | Major updates and revisions to [Cross-Device Analytics](/help/components/cda/overview.md). Added [Field-based stitching](/help/components/cda/field-based-stitching.md). |
| July 16, 2020 | New date range presets in Workspace. Added 4 new date ranges: ([!UICONTROL This week/month/quarter/year (excluding today)]). This lets you choose from date ranges that do not include partial-day data from today. |
| **June 2020** | |
| June 25, 2020 | New documentation for [Quick Insights panel](/help/analyze/analysis-workspace/c-panels/quickinsight.md) in Workspace. It provides guidance for non-analysts and new users of Analysis Workspace to learn how to answer business questions quickly and easily. |
| June 25, 2020 |  New documentation for [Analytics for Target panel](/help/analyze/analysis-workspace/c-panels/a4t-panel.md) in Workspace. It lets you analyze your Adobe Target activities and experiences, with lift and confidence. |
| June 18, 2020 | New documentation on [Attribution: Algorithmic Attribution](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html) |
| June 18, 2020 | New documentation on [Attribution: Custom Lookback windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html#lookback-windows) |
| June 18, 2020 | New documentation for [Project roles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) for shared Workspace projects. When sharing a Workspace project, you can now place recipients in one of three project roles, depending on the project experience you want them to have: Edit, Duplicate and View. |
| June 18, 2020 | New documentation on ["View only" Workspace projects](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/view-only-projects.html). Projects can be shared to users as "Can view" only. When a View recipient opens the shared project, they receive a more restrictive project experience, with no left rail and limited interactions. |
| June 18, 2020 | New documentation on [Project roles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) for shared Workspace projects. When sharing a Workspace project, you can now place recipients in one of three project roles, depending on the project experience you want them to have: Edit, Duplicate and View. |
| June 18, 2020 | New documentation on [Co-editing Workspace projects](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html). Recipients added to the "Can edit" role can save over a project that has been shared to them. This extends to both admins and non-admins. |
| **May 2020** |  |
| May 31, 2020 | New documentation on [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) |
| May 21, 2020 | New documentation for [Adobe Analytics dashboards](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html) |
| May 21, 2020 |  New documentation on [accessibility improvements](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/aw-accessibility.html) to Analysis Workspace, including improved keyboard navigation, color contrast, and screen reader support. |
| **April 2020** |  |
| April 28, 2020 | Added documentation for the [Content Velocity](/help/components/metrics/content-velocity.md) metric. |
| April 16, 2020 | Documentation on how to automatically build [!UICONTROL Freeform Tables] from a blank state. Previously, you could not drop components directly into a blank project or blank panel; you had to add a freeform table first. You can now drop components directly into a blank project or panel, and a freeform table will automatically be built for you in a recommended format. Additionally, improvements were made to how mixed component types (e.g. dimensions & metrics) are handled when dropped into a blank [!UICONTROL Freeform Table] together.|
| **March 2020** |  |
| March 12, 2020 | Added updates to [Publish segments to the Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-publish.md). |
| March 12, 2020 | Updates to CDA stitching latency.|
| March 12, 2020 | Support for multiple report suites in Workspace. You can now bring in data from multiple report suites into a single project to view side by side. [Learn more...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html)|
| March 12, 2020 | Training Tutorial template in Workspace. This new standard template walks you through common terminology and steps for building your first analysis in Workspace. It is available as a standard template in the New Project modal and replaces the sample project that exists today for new users that do not have other projects in their list. [Learn more...](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)|
| **February 2020** |  |
| February 27, 2020 | Added documentation for [Adobe Analytics Labs](/help/analyze/labs.md). |
| February 25, 2020 | Added [`useLinkTrackSessionStorage`](/help/implement/vars/config-vars/uselinktracksessionstorage.md) variable. |
| February 20, 2020 | New Workspace template for organizations using Cross-Device Analytics. This template shows how effective CDA is at stitching visits together and educates you on CDA-exclusive dimensions and metrics. A report suite using CDA is required. See [Set up Cross-Device Analytics](/help/components/cda/setup.md) for more information. |
| February 20, 2020 | New hotkeys in Workspace:<ul><li>Collapse/Expand All panels: `alt + m`</li><li>Collapse/Expand Active panel: `alt + ctrl + m`</li><li>Search left rail: `ctrl + /`</li><li>Move to next panel: `alt + Right Key`</li><li>Move to previous panel: `alt + Left Key`</li></ul>[Learn more...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html)|
| February 20, 2020 | Workspace enhancements: <ul><li>When a panel or visualization is dropped into Workspace, the left rail will now auto-switch to components for a more seamless workflow.</li><li>Template components can now be actioned upon (e.g. tagged, favorited, approved).</li><li>Filtered metric and segment lists offer the + button to add a new component if you don't find what you need.</li></ul>|
| February 20, 2020 | Workspace debugger was added to the Help menu, giving you a more seamless way to enable it for debugging Workspace requests. [Learn more...](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md)|
| February 18, 2020 | Added [`writeSecureCookies`](/help/implement/vars/config-vars/writesecurecookies.md) variable. |
| February 12, 2020 | Updates to and reorganization of the [Marketing Channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md) documentation.|
| February 12, 2020 | Added new hotkeys to [this Workspace page](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) |
| February 7, 2020 | Updates to [Setting up Cross-Device Analytics](/help/components/cda/setup.md) and [FAQ](/help/components/cda/faq.md) |
| February 4, 2020 | Complete rewrite of the [Implementation user guide](/help/implement/home.md). |
| January 22, 2020 | Updated Freeform Table page to include information on the new [Freeform Table Builder](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). |
| **January 2020** | |
| January 24, 2020 | Updates to the [Row Settings](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/table-settings.html#cja-workspace) page in Workspace. |
| January 16, 2020 | New documentation on [Freeform Table Builder](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html). With Table Builder enabled, you can drag and drop in many dimensions, breakdowns, metrics and segments to build tables that answer more complex business questions. Data will not update immediately. Instead, updates occur after you click **[!UICONTROL Build]**, saving you time once you know what table you want to construct. Additionally, this feature offers:<ul><li>**Preview**: You can preview the format of a table before spending time to render real data.</li><li>**Flexible Row and breakdown settings**: You can set your row and breakdown levels for every dimension row. Previously, Workspace imposed defaults that could not be changed until after the data was returned.</li><li>**Breakdown by position**: You can set dimension rows to always _breakdown by position_ instead of _by specific item_ (the default).</li><li>**Manual static row ordering**: You can manually order static rows so that the table rows are displayed exactly as you need them. Previously, static rows could be sorted only by a metric column or alphabetically.</li></ul> |
| January 13, 2020 | Added [Adobe Analytics and browser cookies](/help/technotes/cookies/cookies.md). |
| January 13, 2020 | Modified the [Which Adobe Analytics Tool should I use](/help/analyze/get-started/which-analytics-tool.md) page. |

### 2019 {#year2019}

| Feature | Description |
| --- | --- |
| December 19, 2020 | Changed the default [FTP data storage limit](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-limits.html) to 10 GB. |
| November 29, 2019 | Overhaul to the [Data feed documentation](/help/export/analytics-data-feed/data-feed-overview.md) |
| November 25, 2019 | New topic on End-of-life for Enforce IP login restrictions. |
| November 21, 2019 | New documentation set for [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html) |
| November 21, 2019 | Updated [Audience Analytics Workflow FAQ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) to indicate availability in LiveStream. |
| October 25, 2019 | Updated [Adobe Analytics Key Concepts](/help/technotes/terms.md) page. |
| October 10, 2019 | Update to Freeform table totals: they now include two totals, a **[!UICONTROL Table total]** and a **[!UICONTROL Grand total]**. The Table total row accounts for [report filters](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html) applied. Previously, only segmentation impacted totals. [Learn more](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html)<br/>In addition, **[!UICONTROL Show Totals]** and **[!UICONTROL Show Grand Total]** options have been added to **[!UICONTROL Column Settings]**.<br/>With this change to Freeform totals, dependent visualizations will be updated (e.g. linked **[!UICONTROL Summary Number]** visualizations), as well as exported CSV and PDF data. |
| October 10,2019 | In Workspace, the ability to easily remove 'Unspecified (None)' was added as an option to report filters.|
| October 10,2019 | In Workspace, purple granularity components (Minute, Hour, Day, Week, Month, Quarter, Year) were deprecated. **No action** needs to taken if you previously used one of the purple time components.<br/>With this change, the purple **[!UICONTROL Time]** section has also been renamed to **[!UICONTROL Date Ranges]**. |
| October 1, 2019 | New article on [Workspace totals](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/workspace-totals.html#cja-workspace). |
| September 28, 2019 | New articles on [configuration variables for Javascript implementation](/help/implement/vars/config-vars/configuration-variables.md) |
| September 19, 2019 | Revised segmentation documentation to explain [Logic Group containers](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html#logic-group-containers). |
| September 12, 2019 | New documentation for [Cross-Device Analytics](/help/components/cda/overview.md) |
| September 12, 2019 | Update [Calculated metrics totals](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html) document. |
| August 28, 2019 | New article on [Progressive Web Apps (PWAs) for Analytics](/help/technotes/pwa.md) |
| August 8, 2019 | New article on [Calculated Metrics Totals](/help/components/c-calcmetrics/cm-totals.md) |
| August 8, 2019 | Clarification on [timestamp-enabled session data](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md) | 
| August 8, 2019 | In Workspace, Adobe increased the limit of items that can be placed in a static drop-down filter from 50 to 200. This enhancement accommodates a variety of use cases, such as adding all countries (195) to a filter, or all US states and provinces (52). |
| August 2, 2019 | Major update to [Analytics glossary](/help/technotes/terms.md) |
| July 22, 2019 | Added Magento: Marketing and Commerce template to the [Analysis Workspace templates](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) documentation. |
| July 18, 2019 | Updated [Cohort Table settings](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).|
| July 18, 2019 | In the left rail in Workspace, users now have the option to _Show items from last 18 months_. Previously, the lookback period was a maximum of 6 months. This makes it easier to compare to pages or campaigns from last year, up to 18 months ago. |
| July 18, 2019 | Documentation on a new Workspace template called ["Magento: Marketing & Commerce"](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) to Analysis Workspace. It is designed specifically for Magento e-commerce customers, but any retailer can use it to get unique insights into their commerce activities. |
| June 13, 2019 | Added new out-of-the-box filters to the left rail search in Workspace. Beyond what you see today (Dimensions, Metrics, Approved, etc.), new filters such as Calculated Metrics, Customer Attributes, eVars, Props, Video, etc. were added to make it easier to find the components you need. |
| June 4, 2019 | New guide authored, titled [Transitioning from a third-party analytics platform to Adobe Analytics](/help/technotes/ga-to-aa/home.md). |
| May 30, 2019 | Overhaul to the [Data Feed Column Reference](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| May 09, 2019 | A new setting was added to the Flow visualization settings: Include Repeat Instances. See [Flow Settings](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)|
| April 11, 2019 | Enhancements to Workspace optimization best practices: Optimizing Performance|
| April 11, 2019 | Updates to [Optimize Workspace Performance](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). |
| March 14, 2019 | Major Update to Regional Data Collection. |
| February 7, 2019 | Minor update to the "Replace the last octet of IP addresses with 0" and the "IP Obfuscation" settings in [General Account Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md). |
| February 1, 2019 | Major update to the [getPercentPageViewed](../implement/vars/plugins/getpercentpageviewed.md) implementation plug-in. |
| January 17, 2019 | [Cohort Analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) - Major improvements to Cohort Analysis let you:<ul><li>Apply a segment inclusion and return metrics separately. </li><li>Show churn instead of retention.</li><li>Show latency tables (time elapsed before and after an inclusion event).</li><li>Customize cohort dimension (to group visitors based on an eVar, not just time).</li><li>Do a rolling cohort calculation: calculate retention/churn based on prior time period, not original cohort. </li><li>Add in multiple metrics in inclusion & return fields, as well as apply segments. (Calculated metrics are not supported)</li></ul> |
| January 17, 2019 | [View Density](/help/analyze/analysis-workspace/build-workspace-project/view-density.md). This new setting lets you see more data on a single screen by reducing the vertical padding of the left rail, freeform tables and cohort tables. Accessible via Project > Project Info & Settings.|
| January 17, 2019 | [Support for multi-valued variables in Attribution](/help/analyze/analysis-workspace/attribution/overview.md). Some dimensions in Analytics can contain multiple values on a single hit, such as listVars, the product variable, list props, or merchandising eVars. Analysis Workspace lets you apply Attribution to any of these types of variables at the hit level.|
