---
description: Create workspace projects based on standard or custom templates.
title: Templates
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
feature: Workspace Basics
role: Business Practitioner, Administrator
exl-id: 751399fe-6d4f-47cc-8827-82c992079b52
---
# Templates

You can choose whether to create a project from:

* **Blank project (default)**: For instructions, see [Create an Analysis Workspace Project](/help/analyze/analysis-workspace/home.md).
* **Standard template**: These templates are created by Adobe and ship with the product.
* **Custom template**: These templates can be created, shared, or deleted by users with admin rights or by non-admins, provided they have been granted the [!UICONTROL Analysis Workspace: Save as Template] permission in the Admin Console. [Learn more...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Create a custom template {#create-custom-template}

Users with admin rights can turn any project they create into a custom template. Here's how: 

1. Open the project.
1. Go to **[!UICONTROL Project]** > **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   The project will be saved under the current project name, followed by the word (Template) in parentheses. Admins can change this name by editing the template.

   >[!NOTE]
   >
   >By default, project templates are visible to everyone in your organization. You can organize them by applying tags. (Go to **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** to edit tags and descriptions.)

### Actions you can perform on custom templates

   ![](assets/custom_templates.png)

| Action | Description |
|--- |--- |
|Edit template|Lets an admin edit the template by changing its data source, modifying components, visualizations, date ranges, etc.  To edit a custom template, either<ul><li>Bring up the list of custom templates in Analysis Workspace, select one, and click  Edit Template, or</li><li>In Analytics, navigate to  Components >  Projects, then filter on  Templates. Click the name of the template you want to edit.</li></ul>**Note:** After editing a template, depending on the situation, you have two options: Save, Save As. Here is how they differ:<ul><li>**Save:** Updates the custom template for all users. When someone else creates a project from this custom template, they will see the changes you have made.</li><li>**Save As:** Creates a copy of the custom template with your changes. (You can tell that you are in edit mode when the  Share >  Share Project menu item is disabled.)</li></ul>|
|Search on templates|In the Custom Templates dialog, click  Search Templates.|
|Sort templates|You can sort templates alphabetically, by relevance, and by creation date.  In the Custom Templates dialog, click Sort:.|
|Apply tags to template|Open the template and go to  Project >  Project Info & Settings. Click  Add Tags.|
|Modify template description|Open the template and go to  Project >  Project Info & Settings. Double-click the description and edit it.|


## Standard templates 

When you first open a Workspace, templates are available in the left rail. Analysis Workspace Templates cover common use cases. They are grouped by the vertical they belong to and are populated with different dimensions, segments, metrics and visualizations, depending on the report suite you have selected.

You can use these pre-populated templates as they are or adapt them to your needs (by adding or replacing metrics or visualizations, for example) and save them under a new name. 

Here is a video tutorial on [Standard Templates in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/standard-templates-in-analysis-workspace.html) (2:46)

Here are available templates and the questions that each template helps answer.

### Training

These standard templates walk you through common terminology and steps for building your first analysis in Workspace. They is available as a standard template in the New Project modal and replace the sample project that exists today for new users that do not have other projects in their list.

* **Training Tutorial - Internal Search Analysis**: The Internal Search tutorial helps you understand what your visitors are looking for on the website or app, but not finding. Analyzing this type of data can surface content optimization opportunities.

* **Training Tutorial - Marketing Analysis**: This tutorial shows you how to put together a marketing analysis for your executives, including what custom dimensions and metrics are important.

### Advertising

>[!IMPORTANT]
>
>Advertising templates are available only if your report suite is enabled for Advertising Cloud.

* **Paid Search Engines**: This template breaks down advertising trends, ad platforms, keywords, accounts, campaigns, and more.

### Commerce

* **Magento: Marketing and Commerce**: This template breaks down your e-commerce conversion by marketing channel attribution, as well as providing insight by search keyword, landing page, geographical location, and more. For a video overview, see:

>[!VIDEO](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/magento/magento-analysis-workspace-template.html)

### Media

* **Audio Consumption**: Which content is being consumed the most and is engaging users? 
* **Recency - Frequency - Loyalty**: Who are my loyal readers?

### Mobile

>[!IMPORTANT]
>
>Mobile templates are available only if your report suite is enabled for Mobile.

* **Messaging:** Focuses on in-app and push messaging performance.
* **Location:** Includes a Map showcasing location data.
* **Key Metrics:** Keep a pulse on the key metrics of your app.
* **App Usage:** How many app users, launches, and first launches did the app have, and what was the average session length? 
* **Acquisition:** See how mobile acquisition links are performing.
* **Performance:** How is the app performing and where are users having problems? 
* **Retention:** Who are my loyal users and what do they do? 
* **Journeys:** What are the prominent usage patterns for my app?

### Retail

* **Campaign Performance:** What campaigns are driving the most revenue? 
* **Products:** Which products are performing the best?

### Web

* **Acquisition:** What are the top traffic drivers to my website? 
* **Content Consumption:** What are the top places people go on my site? 
* **Retention:** What types of users are likely to be loyal users of my site? 
* **Technology:** What technology are people using to access my site?

### People

>[!NOTE]
>
>The People template and its associated People metric is available for use only as part of the [Adobe Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html).

This template is based on the People metric, which is a de-duplicated version of the Unique Visitors metric. The People metric provides a measure of how often consumers using multiple devices interact with your brand. The template lets you

* Segment your data for US/Canada vs. the rest of the world. The Device Co-op is currently available only in North America.
* Compare the People and Unique Visitors metrics side by side.
* See the "compression rate", a calculated metric that calculates how much smaller the People metric is as a percentage of Unique Visitors.
* Compare the device type totals your customers use 
* See how many average devices per person are used.
* Discover how to use segment stacking with the People metric.
* Explore how using the Experience Cloud ID in your environment enhances the effectiveness of the People metric.

### Journey IQ: Cross-Device Analysis template

<!--This content is mirrored in the CDA doc.-->

This template lets you see vital cross-device performance data. It is available only to customers who have access to [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en) (CDA). 

* **Special note for members of the Co-op Graph**: Shows what portion of your report suite contains visitors in regions where the co-op graph is supported, and regions where it is not supported.
* **Identification of users**: Shows how often visitors to your site are identified using methods based on Cross-Device Analytics.
* **Measuring audience size**: Shows a comparison of 'Unique Devices' compared to 'People'. The proportion of these two numbers is known as 'Cross-device compression', a calculated metric visible in this panel. This compression metric depends on a broad range of factors:
  * **Using the Co-op graph or Private graph**: Generally speaking, organizations using the device co-op tend to see better compression rates than organizations using the private graph.
  * **Log-in rate**: The more users log in on your site, the more Adobe can identify and stitch visitors across devices. Sites with a low log in rate also have low compression rates.
  * **Experience Cloud ID coverage**: Only visitors with an ECID can be stitched. A lower percentage of visitors to your site using an ECID correlates to lower compression rates.
  * **Multiple device usage**: If visitors to your site don't use multiple devices, you can see lower compression rates.
  * **Reporting granularity**: Compression by day is typically smaller than compression by month or year. The chances for an individual to use multiple devices becomes smaller within a single day than over an entire month. Segmenting, filtering, or using breakdown dimensions can also show a lower compression rate. 
* **People-based segments**: Contains a segment dropdown that allows you to view device specific data. This panel encourages experimentation with segments to see how including or excluding device types affect reports.
* **Analyzing the cross-device journey**: Provides flow and fallout reports based on device type.
* **Cross-device attribution**: Combine the features of Journey IQ and Attribution IQ together.
* **Other tips and tricks**: Helpful topics around CDA that lets you get more out of using it.
