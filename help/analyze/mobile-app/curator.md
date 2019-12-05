---
description: Instructions for setting up the mobile app scorecards.
title: Adobe Analytics Mobile App Curator Guide
---


# BETA: Curator’s Guide for Analytics Mobile App


## Introduction

The Adobe Analytics Mobile App provides anytime, anywhere insights from Adobe Analytics.   The app allows users mobile access to intuitive scorecards, that you create and share from Adobe Analytics’ desktop UI. Scorecards are a collection of key metrics and other components presented in a tiled layout that you can tap for more detailed breakdowns and trended reports. You can tailor Scorecards according to the data most important to you. The mobile app is supported on both iOS and Android operating systems.

## About this guide

This guide is intended to help curators of Adobe Analytics data configure Scorecards for their executive users on the Analytics Mobile App. Curators may be organizational administrators or persons in other roles who are responsible for setting up app Scorecards, which allow executive users to view a broad rendering of important summary data quickly and easily on their own mobile devices. Although executive users are the end-users for the Analytics Mobile App, this guide will help data curators set up the app effectively for those users.


## Glossary of terms

The following table describes the terms for understanding the audience, functions, and operation of the Analytics Mobile App.

|Term|Definition|
|--|--|
|Consumer| Executive persona viewing key metrics and insights from Analytics on a mobile device|
|Curator|Data literate persona who finds and distributes insights from Analytics and configures the Scorecards to be viewed by consumer|
|Curation|The act of creating or editing a mobile scorecard containing relevant metrics, dimensions and other components for the consumer|
|Scorecard|A Mobile App View containing one or more tiles|
|Tile|A rendering for a metric within a Scorecard View|
|Breakdown|A secondary view accessible by tapping a tile in the Scorecard. This view expands on the metric displayed on the tile and optionally reports on additional breakdown dimensions.|
|Date Range|The primary date range for Mobile App reporting|
|Comparison Date Range|The Date Range that is compared with the primary date range|

 
## Create a Scorecard for executive users

A mobile Scorecard displays key data visualizations for executive users in a tiled layout, as shown below:


![Example scorecard](/help/analyze/mobile-app/assets/intro_scorecard.png)


As a curator of this Scorecard, you can use the Scorecard Builder to configure which tiles appear on the Scorecard for your consumer. You also configure how the detailed views, or the Breakdowns, can be adjusted once the tiles are tapped. The Scorecard Builder interface is shown below:

![Scorecard Builder](help/analyze/mobile-app/assets/scorecard_builder.png)


To create the Scorecard, you will need to do the following:

1. Access the Blank Mobile Scorecard template.
2. Configure the Scorecard with data and save it.


### Access the Blank Mobile Scorecard template

You can access the Blank Mobile Scorecard template in one of the following ways:

**Create a new project**

1. Open Adobe Analytics and click the **Workspace** tab.
2. Click the **Create New Project** button and select the **Blank Mobile Scorecard** project template.
3. Click the **Create** button.

![Scorecard template](help/analyze/mobile-app/assets/new_template.png)


*Note: If you do not see the Blank Mobile Scorecard template, as shown below, your company has not yet been activated for Beta. Please contact your Customer Service Manager.*


**Add a project**

From the **Projects** screen, under the **Components** tab, click the **Add** button and select **Mobile Scorecard**.

![Add projects](help/analyze/mobile-app/assets/add_project.png)

**Use Analytics tools**

In Analytics, click the **Tools** menu and select **Mobile App**. On the subsequent screen, click the **Create Scorecard** button.

### Configure the Scorecard with data and save it

To implement the Scorecard template:

1. Under **Properties** (in the right-hand rail), specify a **Project Report Suite** from which you want to use data.

    ![Report suite selection](help/analyze/mobile-app/assets/properties_save.png)

2. To add a new tile to your Scorecard, drag a metric from the left panel and drop it into the **Drag and Drop Metrics Here** Zone. You can also insert a metric between two tiles using a similar workflow.

    ![Add tiles](help/analyze/mobile-app/assets/build_list.png)


    *From each tile, you can access a detailed view that displays additional information about the metric, such as top items for a list of related dimensions.*


3. To add a related dimension to a metric, drag a dimension from the left panel and drop it onto a tile. For example, you can add appropriate dimensions (like **DMA Region**, in this example) to the **Unique Visitors** metric by dragging and dropping it onto the tile; dimensions you add will appear under the breakdown section of the tile-specific **Properties**. You can add multiple dimensions to each tile.

    ![Add dimensions](help/analyze/mobile-app/assets/layer_dimensions.png)

    *Note: You can also add a dimension to all tiles by dropping it onto the Scorecard canvas.*

    When you click on a tile in the Scorecard Builder, the right-hand rail displays the properties and characteristics associated with that tile. In this rail, you can provide a new **Title** for the tile and alternatively configure the tile by specifying components instead of dragging and dropping them from the left-hand rail. 


    Also, if you click on tiles, a dynamic pop up will display how the Breakdown view appears to the executive user in the app. If no dimension has been applied to the tile, the breakdown dimension will be **hour** or **days**, depending on the default date range.

    ![Breakdown_view](help/analyze/mobile-app/assets/break_view.png)

    *Note how each dimension added to the tile will show up in a drop-down list in the detailed view of the app. The executive user can then choose among the options listed in the drop-down list.*

4. To apply segments to individual tiles, drag a segment from the left panel and drop it directly on top of the tile. If you want to apply the segment to all the tiles in the Scorecard, drop the tile on top of the scorecard.

5. Similarly, to remove a component that is applied to the entire Scorecard, click anywhere on the Scorecard outside of the tiles and then remove it by clicking the **x** that appears when you hover over the component, as shown below for the **Mobile Customers** segment:

    ![Remove_components](help/analyze/mobile-app/assets/new_remove.png)

6. Under Scorecard **Properties**, you also can optionally specify the following:

    * A **Default Date Range**. The ranges you specify here will be the same ones applied to the executive user’s first access to the Scorecard in their app.

    * A **Comparison Date Range**

    * Any **Segments** to apply to the whole Scorecard

7. To name the Scorecard, click the namespace in the upper-left of the screen and type the new name.

    ![Naming_scorecards](help/analyze/mobile-app/assets/new_name.png)

## Share the Scorecard

To share the Scorecard with an executive user:

1. Click the **Share** menu and select **Share Scorecard**.

2. In the **Share** form, complete the fields by:

    * Providing the name of the Scorecard
    * Providing a description of the Scorecard
    * Adding relevant tags
    * Specifying the recipients for the Scorecard
    * Select the option to **Share Embedded Components with Recipients** to ensure that the executive user has access to all the components in the Scorecard.

3. Click **Share**.
 
![Share_Scorecards](help/analyze/mobile-app/assets/new_share.png)


After you have shared a Scorecard, your recipients can access it on their Analytics Mobile App. If you make subsequent changes to the Scorecard in the Scorecard Builder, they will be automatically updated in the shared Scorecard. Executive users will then see the changes after refreshing the Scorecard on their app.

*Note: If you update the Scorecard by adding new components, you may want to share the scorecard again (and check the **Automatically Share embedded components with recipients** option) in order to make sure that your executive users have access to these changes.*

## Setup executive users with the app

In some cases, executive users may need some additional assistance to access and use the app. This section provides information to help you provide that assistance.

### Help executive users gain access

To assist executive users access your Scorecards on the app, ensure that:

    * The minimum mobile OS requirements on their devices are iOS version 10 or higher, or Android version 4.4 (KitKat) or higher 
    * They have a valid login into Adobe Analytics
    * You have correctly created mobile Scorecards for them and share these Scorecards with them.
    * They have access to Analysis Workspace and the report suite that the Scorecard is based on
    * They have access to the Components that the Scorecard includes. Note: You can select an option when sharing your Scorecards to **Automatically Share embedded components with recipients**.
 
### Help executive users use the app

During the beta phase, and before the app is unveiled to the public, you can control who has access to the app. 

1. Help executive users download and install the app. To do this, provide the following steps to extend access to your executive users, depending on whether they use an iOS or an Android device.

    **For executive users on iOS:**

    1. Click the following public link (It is also available in Analytics under **Tools** > **Mobile App**): 

        [iOS link](https://testflight.apple.com/join/WtXMQxlI): `https://testflight.apple.com/join/WtXMQxlI`

        After clicking the link, the following Testflight screen appears:

        ![Testflight screen](help/analyze/mobile-app/assets/testflight1.png)

    2. Tap the **View in App Store** link on the screen to download the Testflight app.

    3. After installing the Testflight app, find and install the Adobe Analytics Mobile App from within Testflight as shown below:

    ![Testflight screen](help/analyze/mobile-app/assets/testflight2.png)

    **For executive users on Android:**

    1. Tap the following Play Store link on the user's device (It is also available in Analytics under **Tools** > **Mobile App**):


        [Android](https://play.google.com/apps/testing/com.adobe.analyticsmobileapp): `https://play.google.com/apps/testing/com.adobe.analyticsmobileapp`

        After tapping the link, tap the Become a Tester link on the following screen:

        ![Play Store screen](help/analyze/mobile-app/assets/play.png)

    2. Tap the **download it on Google Play** link on the following screen:

        ![Download link](help/analyze/mobile-app/assets/playnext.png)

    3. Download and install the app.

Once downloaded and installed, executive users can sign into the app using their existing Adobe Analytics credentials; we support both Adobe and Enterprise/Federated IDs.

    ![App welcome screen](help/analyze/mobile-app/assets/welcome.png)

2. Help them access your Scorecard. After executive users sign into the app, the Choose a company screen appears. This screen lists the login companies to which the executive user belongs. To help them get to the Scorecard: 

* Tap the name of the login company or Experience Cloud Org that applies to the Scorecard you shared. The Scorecard list then shows all Scorecards that have been shared with the executive under that login company. 
* Help them sort this list by Most recently modified, if applicable. 
* Tap the name of the Scorecard to view it.


1. Choose a company by tapping it.
2. Tap a Scorecard from the Scorecard List.

    Note: If the executive user logs in and sees a message saying that nothing has been shared:

    * The executive user may have selected the wrong Analytics instance
    * The Scorecard has not been shared with the executive user

3. Show how tiles appear in the Scorecard you share. 



    Additional information on tiles:

        * The granularity of the sparklines is dependent on the length of the date range: 
            * One day shows an hourly trend
            * More than one day and less than a year shows a Daily trend
            * One year or more shows a weekly trend
        * Percent value change formula is metric total (current date range) – metric total (comparison date range) / metric total (comparison date range).
        * You can pull the screen down to refresh the Scorecard.


4. Tap a tile to show how a detailed breakdown or trended report for the tile works.


5. To change date ranges for your Scorecard:
 
 

    *1. Tap the Date header. 2. On the Date range screen, tap the span of time you want to work with.*

    Depending on the interval you tap (Day, Week, Month, or Year), you will see two options for date ranges—either the present span of time or the one immediately preceding it. Tap one of these two options to select the first range. Under the COMPARE TO list, tap one of the presented options to compare the data of this time period with the first date range you selected. Tap Done in the upper right of the screen. The Date Ranges field and the Scorecard tiles are updated with the new comparison data from the new ranges you selected.


6. To leave feedback on this app:


    1. Tap the user icon in the upper right of the app screen. 
    2. On the My Account screen, tap the Feedback option. 
    3. Tap to view the options for leaving feedback.



*Tap the User icon in the upper right. 2.Tap the type of feedback. 3. Tap the applicable feedback option.*


 





To report a bug:

Tap the option and choose a sub-category of the bug. In the form for reporting a bug, provide your email address in the top field and your description of the bug in the field below it. A screen shot of your account info is automatically attached to the message, but you can delete this if you want by tapping the X in the attachment image. You also have options for taking a screen recording, adding more screenshots, or attaching files. To send the report, tap the paper plane icon in the upper right of the form.














To suggest an improvement:

Tap the option and choose a sub-category for the suggestion. In the suggestion form, provide your email address in the top field and your description of the bug in the field below it. A screen shot of your account info is automatically attached to the message, but you can delete this if you want by tapping the X in the attachment image. You also have options for taking a screen recording, adding more screenshots, or attaching files. To send the suggestion, tap the paper plane icon in the upper right of the form.

To ask a question:

Tap the option and provide your email address in the top field and your question in the field below it. A screen shot is automatically attached to the message, but you can delete this if you want by tapping the X in the attachment image. You also have options for taking a screen recording, adding more screenshots, or attaching files. To send the question, tap the paper plane icon in the upper right of the form.
