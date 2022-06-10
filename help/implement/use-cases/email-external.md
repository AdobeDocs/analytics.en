---
title: External email tracking
description: Use Adobe Analytics to track email content.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
---
# External email tracking

Companies use Analytics to determine the success of an email campaign.

 [!DNL Analytics] can report email campaign analysis data in several key metrics, including the following: 

|  Metric  | Description  |
|---|---|
|  Click-throughs  | Displays the number of click-throughs tracked from the email to the landing page.  |
|  Purchases and/or Successes  | Displays the number of purchases resulting from the email.  |
|  Orders  | Displays the number of orders placed as a result of the email.  |
|  Yield  | Displays the dollar amount per visit generated from the email.  |
|  Conversion  | Displays the number of leads, registrations, or any other success event generated from the email.  |

Modifications to the HTML email body and the JavaScript library are required in order to capture the key metrics shown above.

## Implementation {#section_8A42A8F4A6CD4A1BAF4B9F99F709AF7A}

There are several steps to follow in order to successfully display email campaign analysis data. The steps are described as follows:

1. Create unique tracking codes.

   Often, users ask for tracking recommendations for each unique campaign. This is entirely up to them, based on what works best. Each user is different. Adobe recommends that each user generate friendly tracking codes, as shown in the example below:

    * sc_cid=A1123A321 > "A" flags affiliate campaign 
    * sc_cid=EM033007 > "EM" flags email campaign 
    * sc_cid=GG987123 > "GG" signifies Google and is a paid search campaign

   Contact Adobe [!DNL Customer Care] for details on setting up and using tracking codes.

1. Add query string parameters to HTML email links.

   In order to track a user click-through and subsequent success events, a query string parameter needs to be added to each link within the HTML email. You can choose to track each link separately or track all links together. Each link can have a unique tracking code, or all links can have the same tracking code. Consider the following hypothetical link within the email to a website:

   ```js
   <a href="https://www.example.com/index.asp">Visit our home page</a>
   ```

   The following query string parameters ?sc_cid=112233B should be added to the link above:

   ```js
   <a href= "https://www.example.com/index.asp?sc_cid=112233B">Visit our home page</a>
   ```

1. Update the JavaScript library.

   Altering code in the JavaScript file, [!DNL s_code.js], lets you capture how many users (and which users) clicked-through from the email and participated in subsequent success events. There are two steps to updating the JavaScript library.

    1. Customize [!DNL s_code.js] by calling [!UICONTROL getQueryParam].

       The [!DNL s_code.js] file should be placed in a location on the Web server where each Web page can access it. The *`doPlugins`* function within this file should be altered so it captures the query string parameters on the email links. For example:

       ```js    
       /* Plugin Config */ 
       s.usePlugins=true 
       function s_doPlugins(s) { 
        /* Add calls to plugins here */ 
        // External Campaigns 
       s.campaign=s.getQueryParam('source') 
       } 
       s.doPlugins=s_doPlugins 
       
       ```    
    
       Each query string parameter that needs to be copied into a variable should have one [!UICONTROL getQueryParam] call. In the example above, the query string parameter [!UICONTROL sc_cid] is copied into *`campaign`*.

       Only the first call to [!UICONTROL getQueryParam] is required to capture click-throughs. Contact Adobe [!DNL Customer Care] to implement this function and ensure that your version of the JavaScript file contains the [!UICONTROL getQueryParam] plug-in.
    
    1. Make sure the Code to Paste JavaScript tags are on all landing pages. This Code to Paste must reference the version of [!DNL s_code.js] altered in Part A.

       The following points are important to remember when updating the JavaScript library. These points are listed below.

        * The query string parameter [!UICONTROL sc_cid] must be visible in the URL on the final landing page otherwise no click-through conversion is recorded.
        * The [!UICONTROL sc_cid] parameter is an example of a query string parameter. Any query string parameter can be used and captured by the [!UICONTROL getQueryParam] plug-in. Make sure that the query string parameters are used only for campaign tracking. Any time the parameters appear in a query string, their values are copied into *`campaign`*.

1. Use [!UICONTROL SAINT] to classify campaign tracking codes.

   The [!UICONTROL SAINT Campaign Management Tool] can be used to convert tracking codes into user-friendly names. It can also be used to summarize the success of each email campaign. Step 5, below, outlines the process required to set up an email campaign.

1. See pathing by email campaign (optional).

   Pathing analysis by email campaign can be accomplished similarly to pathing by another campaign. You can use a variable to show pathing by campaign, as explained in the following steps:

    1. Consult Adobe [!DNL Customer Care] about turning on pathing for a [!UICONTROL Custom Insight] variable (prop) 
    
    1. On all pages, copy the page name into the designated [!DNL s.prop].
    1. On the email landing page, append the name of the email campaign to the prop. The result displays as shown below:     
    
       ```js    
       s.prop1="Home Page : 123456"
       ```    
    
       When pathing is enabled for the [!UICONTROL Custom Insight] variable, you can use [!UICONTROL Path] reports (such as [!UICONTROL Next Page Flow] or [!UICONTROL Fallout]) to see visitor navigation from the landing page.
