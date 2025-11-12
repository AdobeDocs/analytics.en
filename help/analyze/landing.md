---
description: Explains how the landing page brings together both Analysis Workspace and Reports & Analytics in a single interface and access point under the Workspace umbrella.
title: Adobe Analytics landing page
role: User, Admin
feature: Analytics Basics
exl-id: 0a2fb778-491a-4dc3-aae4-afadb3ab1a1e
---
# Adobe Analytics landing page

The landing page for Adobe Analytics brings together both [!DNL Analysis Workspace] and [!DNL Reports & Analytics] (end-of-lifed) in a single interface and access point under the [!DNL Workspace] umbrella. It features a project manager home page, a templates section, and a learning section to help you with getting started more effectively. 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adobe Analytics landing page](https://video.tv.adobe.com/v/334278/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



The Adobe Analytics landing page is comprised of the following subtabs: Projects, Templates, and Learning.

**[!UICONTROL Projects]** are customized designs that combine data components, tables, and visualizations that you built or that someone else built and shared with you. [!UICONTROL Projects] also refers to blank projects and blank mobile scorecards.

**[!UICONTROL Templates]** includes templates provided by Adobe and any templates specific to your organization.

The **[!UICONTROL Learning]** tab contains hands-on video tours, tutorials, and links to documentation.

## Navigate the [!UICONTROL Projects] tab {#navigate-projects}

The [!UICONTROL Projects] tab serves as the [!UICONTROL Workspace] home page. It displays the Company folder, any personal folders you created, your projects, and Mobile scorecards. Use this page to view, create, and modify folders, projects, and mobile scorecards. For more information, see [About Folders in Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

![Landing all](assets/landing-all2.png)

>[!NOTE]
>
>Several of the following settings persist during the session and across sessions. For example, the tab you selected, the selected filters, selected columns, and the column sort direction. Search results are not persistent.

### Customize table columns

To customize column widths, drag the vertical bar that separates each column. 

To add or remove columns from the list of projects, click the column icon (![Landing all](/help/analyze/assets/select-column.png) ) in the top-right, then select or deselect column titles. 

The available columns are:

| Column name | Description |
|---------|----------|
| [!UICONTROL **Name**] | Identifies the name of the project. |
| [!UICONTROL **Type**] | Indicates whether this type is a Workspace project, a Mobile scorecard, or a folder. |
| [!UICONTROL **Tags**] | Tags projects to organize them into groups. |
| [!UICONTROL **Scheduled**] | Set to [!UICONTROL On] when a project is scheduled or [!UICONTROL Off] when it is not. Clicking the [!UICONTROL On] link lets you see information about the scheduled project. You can also [edit the project schedule](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) if you are the project owner. |
| [!UICONTROL **Project role**] | Identifies the project roles: whether you are the project Owner and whether you have permissions to Edit or Duplicate the project. |
| [!UICONTROL **Report suite**] | Identifies the Report Suites that are associated with the project.<br>Tables and visualizations within a panel derive data from the report suite selected in the top right of the panel. The report suite also determines what components are available in the left rail. Within a project, you can use one or many report suites depending on your analysis use cases. The list of report suites is sorted on relevance. Adobe defines relevance based on how recently and frequently the suite has been used by the current user, and how frequently the suite is used within the organization. |
| [!UICONTROL **Owner**] | Identifies the person who created the project. |
| [!UICONTROL **Shared With**] | Shows who the project is currently shared with. |
| [!UICONTROL **Last Modified**] | The date and time when the project was last modified. |
| [!UICONTROL **Last Opened**] | Identifies the date that a project was last opened by the user who is currently viewing the Projects page. |
| [!UICONTROL **Last Used**] | Helps determine whether a project is valuable to users in your organization by showing the date and time when the project was last opened by any user within the organization.<p>Consider the following when viewing this column:</p><ul><li>Usage information is available starting in September 2023.</li><li>This column is available only to system administrators.</li></ul> |
| [!UICONTROL **Project ID**] | Can be used for debugging projects. |
| [!UICONTROL **Longest Date Range**] | Longer date ranges increase project complexity and may increase processing and load times. |
| [!UICONTROL **Number of queries**] | The total number of requests made to Analytics when the project loads. A higher number of project queries increases project complexity and may increase processing and load times. This data is available only after a project has loaded or a scheduled project was sent. |
| [!UICONTROL **Location**] | Shows the folder where the project is located. |

### Other UI elements on the Projects page

| UI element | Definition |
| --- | --- |
| Edit preferences | Lets you [!UICONTROL View Tutorials], and [Edit user preferences](/help/analyze/analysis-workspace/user-preferences.md). |
| [!UICONTROL Create new] | Opens the project modal where you can create a Workspace project or a Mobile scorecard or open a company template.  |
| [!UICONTROL Show less<br> Show more] | Toggles between not showing and showing the banner: ![Top banner](assets/top-banner.png) |
| [!UICONTROL Workspace project] | Creates a blank [Workspace project](/help/analyze/analysis-workspace/home.md) for you to  design and build. |
| [!UICONTROL Mobile scorecard] | Creates a blank [mobile scorecard](/help/analyze/mobile-app/curator.md) for you to design and build. |
| [!UICONTROL Open Training Tutorial] | Opens the Workspace training tutorial that guides you through the process of building a new starter project in a step-by-step tutorial.|
| [!UICONTROL Open release notes] | Opens the Adobe Analytics section of the latest Adobe Experience Cloud release notes. |
| Filter icon | Filters by tags, report suites, owners, types, and other filters (Mine, Shared with me, Favorites, and Approved)  |
| Search bar | Searches all columns in the table. |
| Selection box | Selects one or more projects to display the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| [!UICONTROL Favorites] | Adds a star next to a favorite project or folder that can be used as a filter. |
| [!UICONTROL Name] | Identifies the name of the project. |
| Pin icon | Pins items so they always appear at the top of your list but you can re-adjust the order by moving them up or down in the order. Use the ellipsis option menu and select **Move Up** or **Move down** in the list. |
| Info (i) icon | Displays the following information about a project: Type, Project Role, Owner, Description, and who it is shared with. It also indicates who can [edit or duplicate](/help/analyze/analysis-workspace/curate-share/share-projects.md) this project. |
| Ellipsis (...) | Displays the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| SHOW: Folders & Projects or All Projects | Changes the view setting on the table to show folders and projects according to your folder organization **or** show all of your projects in an unorganized list. |
| < (Back button) | Returns you to your most recent landing page configuration in a Workspace project or a report. The page configuration you had when you left the landing page will persist when you return. |

## Navigate the [!UICONTROL Templates] tab {#navigate-reports} 

For information about using templates in Adobe Analytics, see the following resources:

* [Use templates](/help/analyze/analysis-workspace/templates/use-templates.md)

* [Create and manage templates](/help/analyze/analysis-workspace/templates/create-templates.md)

## Use the Learning tab {#navigate-learning}

The Learning page contains hands-on video tours, tutorials, and links to documentation.

Use the Learning page in Adobe Analytics to learn beginner, intermediate, or advanced features and use-cases in Adobe Analytics.

### Access the Learning page

1. In Adobe Analytics, select [!UICONTROL **Workspace**] > [!UICONTROL **Learning**].

### Learning page features

* **Filter content:** The Filter icon in the left rail allows you to filter learning content by experience level (Beginner, Intermediate, or Advanced) and by content type (Document, Video, or Tours & tutorials).
* **Track progress:** After you select a piece of content, a **[!UICONTROL Viewed]** tag appears. This tag helps you track your progress through the learning content. You can select the **[!UICONTROL Viewed]** tag to remove it from a piece of content.
* **View additional content:** While viewing any video, select the **[!UICONTROL Learn more]** button to view related documentation content on Experience League. Or, from the Learning page, select either of the following options to view additional content:
  * **[!UICONTROL Visit YouTube]:** View the full Analysis Workspace YouTube playlist.
  * [!UICONTROL **Visit Experience League**]: View the full suite of Adobe Analytics documentation on Experience League. 
* **Fundamentals for new users:** The [!UICONTROL Workspace Fundamentals] tour is recommended for new users. This tour takes you directly to Workspace and walks you through the most common actions. This tour can also be relaunched any time in Workspace via the tooltip pop-over from the panel header.

## Set your landing page {#set-landing}

Users can set their preferred landing page.

1. Go to Analytics > [!UICONTROL Components] > [!UICONTROL Preferences] > [!UICONTROL General].
1. Check which landing page you would prefer:

   ![Set landing page](assets/landing-pref.png)

## Landing page FAQ {#landing-faq}

| Question | Answer |
| --- | --- |
| Where are the templates that I am used to seeing in [!UICONTROL Workspace]? | These templates are grouped under the [!UICONTROL Templates] tab. |
| Does the work I do in the beta program UI carry over to the production [!UICONTROL Workspace] experience? | Yes, any work done in the beta carries over to the old/current [!UICONTROL Workspace] experience. |
| Are my previous Reports & Analytics favorites carried over? | No, they are NOT carried forward. However, any [!UICONTROL Workspace] project favorites are carried over. |
| Is there a maximum number of projects I can pin? | No, there is no limit on the number of projects you can pin. |
| Can admins designate this landing page for their users? | No, admins cannot designate the landing page on behalf of users. Individual users must turn on the toggle themselves. |
