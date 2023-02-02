---
description: A dashboard is a collection of thumbnail reports called reportlets. A dashboard is most useful when it contains related reportlets that give you complete overviews of certain aspects of your site, such as finding methods, visitor profiles, and so on.
subtopic: Dashboards
title: Dashboards and reportlets
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 399765a3-0f90-46b9-b62e-9f41d98eaa9a
---
# Dashboards and reportlets

{{ra-eol}}

A dashboard is a collection of thumbnail reports called reportlets. A dashboard is most useful when it contains related reportlets that give you complete overviews of certain aspects of your site, such as finding methods, visitor profiles, and so on.

## Dashboards and reportlets {#concept_8CD3ACA2830A4994A68A31D8773B57E0}

A dashboard is a collection of thumbnail reports called *`reportlets`*. A dashboard is most useful when it contains related reportlets that give you complete overviews of certain aspects of your site, such as finding methods, visitor profiles, and so on.

You can add most marketing reports to a dashboard, including graphically intense reports like the [!UICONTROL Fallout Report], [!UICONTROL Conversion Funnel Report], and the [!UICONTROL Pathfinder Report].

You can also set a dashboard as your landing page, share dashboards with other users, and schedule them for delivery. If you do not set a dashboard (or a bookmark) as a landing page, the [!UICONTROL My Recommended Reports] dashboard displays. **[!UICONTROL My Recommended Reports]** shows the **[!UICONTROL Key Metrics]** report plus your five most frequently viewed reports. It is dynamic and based on the actual reports that you view the most.

Be aware that some frequently viewed reports cannot be dashboarded and will not show up. These include:

* Anomaly Detection reports 
* Contribution Analysis reports 
* Fallout reports 
* Pathfinder reports 
* Real-time reports 
* Other dashboards

>[!NOTE]
>
>The **[!UICONTROL Site Overview]** dashboard is no longer listed in Reports & Analytics. However, there are still a couple of circumstances where you will see some or all of its reportlets.

* If you have, say, only three frequently viewed reports, Reports & Analytics will take two reports from the Site Overview dashboard to complete the **[!UICONTROL My Recommended Reports]** dashboard.
* Brand new report suites will also initially still feature the Site Overview reportlets, until they gets replaced by your frequently viewed reports. Even so, the dashboard will now be called **[!UICONTROL My Recommended Reports]**.

In addition to the dashboards you create, the following prepackaged dashboards are included for each user: 

**[!UICONTROL Components] > [!UICONTROL All components] > [!UICONTROL Dashboards] > [!UICONTROL Shared Dashboards] > [!UICONTROL Local Sites]**

This customizable dashboard provides you a way to drop reportlets into the template provided.

**[!UICONTROL Components] > [!UICONTROL All components] > [!UICONTROL Dashboards] > [!UICONTROL Shared Dashboards] > [!UICONTROL Site Operations Dashboard]**

This dashboard provides you an overview of key metrics related to your website operations. Reports on this dashboard include:

*   Exit Pages
*   Most Popular Pages
*   Most Popular Site Sections
*   KPI/Gauge Reportlet
*   Text Reportlet
*   Company Summary Reportlet

Use the [!UICONTROL Dashboard Manager] to edit and manage dashboards, and enable them for DirectAccess.

See [Managing Dashboards](/help/analyze/reports-analytics/dashboard-manage.md).

## Create a dashboard {#task_54EFBED59BDC4418A919E6EF84AB9CFF}


<!-- 

t_dashboard_add.xml

 -->

Before adding a report (as a reportlet) to a dashboard, define the dashboard's layout.

To create a dashboard:

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Click **[!UICONTROL Add Dashboard]**.
1. Type a name for the dashboard.
1. Click **[!UICONTROL 3 x 2]** or **[!UICONTROL 2 x 2]** to specify how many reportlets you want on the dashboard page.
1. Configure the dashboard page layout:

   * **[!UICONTROL Add Page]**: Adds a blank page to the dashboard, on which you can drag content to create reportlets.
   * **[!UICONTROL Paper]**: Lets you specify a paper size, such as landscape, portrait, and A4.
   * **[!UICONTROL Find Content]**: Lets you search for content in the [!UICONTROL Add Content] and [!UICONTROL Dashboard Contents] menus.

1. Add available content to the dashboard by dragging items to the reportlet canvas.

   See [Creating a Reportlet](/help/analyze/reports-analytics/dashboard.md#task_EC3AFBBAA51C45CEBAF632F841C305B3) and [Editing Dashboard Settings](/help/analyze/reports-analytics/dashboard.md#task_90D7FAC1CC3E4DB786B4C87CC33B5459).
1. Click **[!UICONTROL Save.]**

   Saving a dashboard makes it available in the **[!UICONTROL Dashboard]** menu. The new dashboard is also available in the [!UICONTROL Dashboard Manager] ( **[!UICONTROL Favorites]** > **[!UICONTROL Dashboards]** > **[!UICONTROL Manager]**), where you can edit, organize, share, schedule, archive dashboards, and more. (See [Managing Dashboards](/help/analyze/reports-analytics/dashboard-manage.md).)

1. (Optional) To set the dashboard as your landing page, click **[!UICONTROL More Options]** > **[!UICONTROL Set as Landing Page]**.

## Create a reportlet {#task_EC3AFBBAA51C45CEBAF632F841C305B3}
After you create a reportlet, it is available to display in a dashboard.

<!-- 

t_dashboard_add_report.xml

 -->

To create a reportlet:

1. Run a report.
1. Click **[!UICONTROL Dashboard.]**
1. On the [!UICONTROL Add Reportlet] page, name the report, then select a dashboard from **[!UICONTROL Place in Dashboard]**.
1. (Optional) Configure the date range.

   * **[!UICONTROL Rolling]**: Changes the date as time passes, according to the time span (daily, monthly, and so on). For example, if today is January 17, you might set the dates for January 15 - 16. Then if you select **[!UICONTROL Rolling]**, on January 27 the reportlet displays data for January 25 - 26.
   * **[!UICONTROL Fixed]**: Prevents the date from moving forward as time passes.

1. (Optional) Override the publishing distribution list.

   **[!UICONTROL Publishing List Override]**: If you enable this option, the report suite referenced in this reportlet is always used when distributed to a publishing list. If you disable this option, the report suite identified in the publishing list replaces the report suite in this reportlet.

1. Click **[!UICONTROL Create New]**.

   The reportlet is added to the **[!UICONTROL Dashboard Contents]** menu in the dashboard editor.

## Add content to a dashboard {#task_90D7FAC1CC3E4DB786B4C87CC33B5459}

You can add content from other dashboards and shared dashboards. You can also add content from custom and external sources, such as text and images.

<!-- 

t_dashboard_content.xml

 -->

To add content to a dashboard:

1. Open a dashboard, then click **[!UICONTROL Layout]**.
1. Click **[!UICONTROL Add Content]**, then drag items to the dashboard.

   The [!UICONTROL Add Content] menu displays reportlet content from other dashboards, legacy dashboards, and shared dashboards.

   >[!NOTE]
   >
   >The current limit to the number of pages in a dashboard is 30.

   **Custom Reportlets**

   *Data Content:*

   *   Company Summary: Displays page views for multiple report suites and metrics that you select.
   *   Metric Gauge: Displays a gauge that tells you where your metrics figures are in relation to the thresholds you specify.
       
       You can select a metric, graph type, color range, and threshold values. If the count of the metric rises above the Greater Than threshold, the gauge indicates this in the reportlet, using the color above the Greater Than field. If the count of the metric is below the Less Than threshold, the gauge indicates this in the reportlet, using the color above the Less Than field. The values you specify in these fields is the countable value of the metric, such as number of page views, dollar amounts, cart views, and so on. (Do not use special characters.)
   *   Report Suite Summary: Displays a selected metric and its total or high and low values for a report suite.
   *   Usage Summary: Shows data on interface access by people in your organization. This reportlet can show data by username access, report access, or report suite access.
       You can create the following User Content reportlets by providing URLs. If an image or other resource URL does not begin with https://, Internet Explorer users might see a warning about mixed content. You can disable the warning for mixed content in your browser security settings.

   *User Content:*

   *   External Report: Lets you add an external report in .xml and .csv formats.
   *   HTML: Lets you add a custom HTML reportlet. The URL must use HTTP or HTTPS. Otherwise, you see a `Specified URL could not be retrieved` error. In the document's content, all tags with attributes using the data: and javascript: protocols are removed. Scripts, frames, applets, event handlers, flash, and other embedded objects are removed. If resources are specified using non HTTPS, IE users are issued a warning about mixed content.
   *   Image: Lets you create a dashboard from an image URL. If the URL uses the HTTP protocol, Internet Explorer issues a mixed content warning. Using a URL with HTTPS removes the warning. All other protocols issue a `Specified URL could not be retrieved` error.
   *   RSS: Lets you add an RSS web feed. Must be HTTP or HTTPS. Otherwise, you see a `Specified URL could not be retrieved` error.
   *   Text: Lets you use XHTML code to create your own data. Use HTTP or HTTPS for a URL. Images used in the text reportlet content that have the HTTP protocol result in IE users receiving a warning about mixed content. Images included using other protocols do not display in the reportlet.

   **My Dashboards**

   Lists your upgraded dashboards from which you can move content to the new dashboard.

   **Legacy Dashboards**

   Lists your shared dashboards from which you can move content to the new dashboard.

   **Shared Dashboards**

   Lists legacy dashboards from which you can move content to the new dashboard. Legacy dashboards are useful if you want to preserve dashboard formatting from previous versions.

   **Dashboard Contents**

   Displays items you already added to the dashboard.

1. Click **[!UICONTROL Save.]**

## Edit dashboard and reportlet data {#task_B460CCD70D9F40FCAC6BBC1C044CC460}

You can change data settings at the dashboard or reportlet level. For example, you can change the report suite, locking the report suite, changing dates, applying segments, and so on. You can also personalize a dashboard by inserting your company's confidentiality statement, and include HTML, XML, Web API, and CSV data in customized reportlets.

<!-- 

t_dashboard_edit.xml

 -->

**To edit dashboard and reportlet data** 

1. Click **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]** > *dashboard name* to open a dashboard.
1. Click **[!UICONTROL Layout]**.

| To  | Do this  |
|--- |--- |
|Change a dashboard's report suite|Click the menu in the Experience Cloud header, then select a report suite.|
|Change a reportlet's report suite|In the reportlet, click the report suite name, then select a report suite from the [!UICONTROL Report Suite] menu.|
|Apply a segment to a dashboard|In the Experience Cloud header, click [!UICONTROL Show Segments], then select a segment.|
|Apply a segment to a reportlet|In the dashboard, click  Layout to edit a dashboard.   In the reportlet, click the report suite name, then select a value from the  Segment field and click  Update.|
|Lock a report suite (prevents changing the report suite in a reportlet)|In the reportlet, click the report suite name, then enable [!UICONTROL Lock Report Suite]. Click  Update.|
|Change a reporting date|For a dashboard, click the calendar. (All the reportlets in the dashboard reflect the change.)<br>For a reportlet, click the date link, then configure the calendar.|
|Name a dashboard|Open a dashboard, then click  [!UICONTROL More] >  [!UICONTROL Rename].|
|View a dashboard archive|Click  [!UICONTROL More] >  [!UICONTROL View Archive].|
|Set the dashboard as a landing page|In a dashboard, click  [!UICONTROL More] > [!UICONTROL Set As Landing Page].|
|Download a dashboard|In a dashboard, click  [!UICONTROL More] >  Download.|
|Print a dashboard|In a dashboard, click  [!UICONTROL More] >  Print.|
|Save a dashboard|In a dashboard, click  Save As, then specify a name.|

## Co-brand a dashboard {#task_603BDE7700B945699AF5514C2DEB81F7}

To upload an image to display in a dashboard:

<!-- 

t_dashboard_branding.xml

 -->

1. **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]**.
1. On the [!UICONTROL Company Settings] page, click **[!UICONTROL Co-Brand the Adobe Experience Cloud]**.
1. Click **[!UICONTROL Enable Co-Branding]**.
1. Browse to upload the image, then click **[!UICONTROL Save.]**

   For best results when viewing the image in a browser, upload a 100px by 30px image. For best results in PDF output, upload a 417px by 125px (300 dpi) image. Oversized images are shrunk to size, while preserving aspect ratio.

## Use segments with dashboards {#concept_ED030C3713D54D03971FB7B209285750}

Dashboards, like most reports in Adobe Analytics, can utilize segments to retrieve desired data.

<!-- 

segments_dashboards.xml

 -->

Segments can be applied on two levels: to an entire dashboard or on a specific reportlet.

* **Reportlet level**: Click **[!UICONTROL Layout]**, then the report suite of the reportlet you want to segment. A modal window appears that lets you add or change what segment(s) the reportlet uses.
* **Dashboard level**: Click the Segment icon in the left navigation, check the segment(s) you want to use, and click Apply. The selected segments override and replace any reportlet-level segments.
