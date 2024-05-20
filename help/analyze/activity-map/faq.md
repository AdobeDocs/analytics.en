+++How do I grant permissions to activity map?

1. Click **[!UICONTROL Add Users to Group]**.

   This will take you to the product profile page in the [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. If you have not created an [!UICONTROL Activity Map Access] product profile, do so now. The permission items required for this profile are [!UICONTROL Analytics Tools] > [!UICONTROL Activity Map] and [!UICONTROL Analytics Tools] > [!UICONTROL Segment Publishing].

1. Add users to that product profile. This allows your users to download Activity Map from  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

+++

---
description: Frequently asked questions for setting up, configuring, and employing features in Activity Map.
title: Activity Map FAQ
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
---
# Activity Map FAQ

Frequently asked questions for setting up, configuring, and employing features in Activity Map.

+++Do all Analytics customers have access to the Admin Tools ActivityMap Enablement page?
Organizations with a contract for Adobe Analytics Standard, Premium, and Ultimate have access to Activity Map.
+++

+++How does Activity Map support Single-Page Applications (SPA)?
Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the Links On Page table's Present column for that link updates with [!UICONTROL Displayed] or [!UICONTROL Hidden].

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the [!UICONTROL Links On Page] table. Activity Map sends a new data request that includes these new links. The new links should appear in the [!UICONTROL Links On Page] table when the data request is handled by the UI.
+++

+++Does Activity Map provide data on "views"?
No, Adobe does not track links that were viewed.
+++

+++What browsers and versions does Activity Map support?
Activity Map supports the latest version of most modern browsers.
+++

+++Does Activity Map increase server calls?
Activity Map does not send server calls by itself. Instead, Activity Map context data variables are included with Analytics page view calls on the subsequent page.
+++

+++Why are some ranked item overlays missing?
Some ranked links, such as submenu links, are hidden from the page. As a consequence, their corresponding link overlays are not shown. Rank is computed for all links on the page, including hidden links.
+++

+++How is link ranking determined in the All Links report?**
* **In Gradient and Bubble mode**: Rank is determined by the metric column. For links with same metric value, the rank is further based on link ID alphabetical order.
* **In Gainer & Loser mode**: Rank is primarily determined by the % Gain column. For links with the same gain, the rank is further based on the link ID alphabetical order.
+++

+++How does Activity Map work with pages that use multiple report suites?
By default, Activity Map uses the report suite that is associated with the first tag that is sent by the page. You can select a different tagged report suite through the **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]** tab.
+++

+++How long does Activity Map scan for Adobe Analytics on the page?
Activity map scans for the presence of Adobe Analytics for up to 20 seconds after a page complete event.
+++

+++How does Activity Map handle dynamic content?
Activity Map checks every 2 seconds to see if it has found changes in the state of the web page such as:

* HTML content that has become visible
* HTML content that is hidden
* New HTML content that was injected

If content is hidden or shown, the application automatically changes the affected links state (and therefore overlays) from hidden to shown or from shown to hidden. If new content is injected, the application retrieves the associated links, pull analytics data for them, and adds overlays for these links.
+++

+++What metric is the Page Flow report based on?
All data shown is based on page views.
+++

+++Can I export Activity Map context data variables through data feeds?
Yes. The [Data columns](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) that Activity Map uses are `clickmaplink`, `clickmaplinkbyregion`, `clickmappage`, and `clickmapregion`.
+++

+++Do segments work in Live mode?
No, segments do not work in Live mode. 
+++

+++Is Activity Map compatible with virtual report suites?
Yes. However, due to virtual report suite limitations, Activity Map's Live Mode is not compatible with virtual report suites.
+++

+++How can I disable Activity Map?
You have three options:

* Delete the `AppMeasurement_Module_ActivityMap` function from the JS file
* Add custom code that rewrites the function above with an empty body, for example:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

* Configure AppMeasurement by setting `s.trackClickMap` and `s.trackInlineStats` to `false`
+++

+++System requirements?

Activity Map is supported on the following web browsers.

| Supported Browsers | Versions |
|--- |--- |
|Firefox|Latest version|
|Chrome|Latest version. Note:  The Activity Map Chrome plug-in is a "developer mode" plug-in only at this time. When you launch this plug-in, you get a message that encourages you to disable developer mode extensions. This message is displayed each time the plug-in is launched.|

>[!NOTE]
>
>From a link collection perspective, Activity Map supports a much larger list of browsers.

+++

+++Implementation requirements?

Other requirements:

* AppMeasurement code version 1.6 or higher. [More...](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) 
* Adobe Analytics tags extension v1.90 or higher
* Web SDK version 2.15.0 or higher. 
* Cookies and Javascript must be enabled.

+++

# Link tracking FAQ

Frequently asked questions about link tracking in Activity Map.

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be collecting personally identifiable information (PII) data.** This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context. 

Here are some known cases where PII data might be collected using Activity Map Tracking: 

* `Mailto` links. A mailto link is a type of HTML link that activates the default mail client on the computer for sending an e-mail.
* `User ID` links that may show up in the header/footer of a website once the user has logged in.
* For financial institutions, the account number may be shown as a link. Clicking it will collect the text of the link.
* Healthcare websites may also have PII data shown as links. Clicking these links will collect the text of the link, thereby collecting PII data.

## When does link tracking occur?

Activity Map link and region identification occurs when users click on a page.

## What is tracked by default?

If a click event occurs on an element, the element has to pass some checks to determine if AppMeasurement will treat it as a link. These are the checks:
    
* Is this an `A` or `AREA` tag with an `href` property? 
* Is there an `onclick` attribute that sets a `s_objectID` variable? 
* Is this an `INPUT` tag or `SUBMIT` button with a value or child text? 
* Is this an `INPUT` tag with type `IMAGE` and a `src` property? 
* Is this a `BUTTON`? 
    
If the answer is Yes to any of the questions above, then the element is treated as a link and will be tracked. 

>[!IMPORTANT]
>
>Button tags with the attribute type="button" are not considered to be links by AppMeasurement. Consider removing type="button" on the button tags and adding role="button" or submit="button" instead. 

>[!IMPORTANT]
>
>An anchor tag with an "href" that starts with "#" is considered an internal target location by AppMeasurement, not a link (since you do not leave the page.) By default, Activity Map does not track these internal target locations. It tracks only links that navigate the user to a new page.

## How does Activity Map track other visual HTML elements?

a. Via the `s.tl()` function. 
    
  If the click occurred via an `s.tl()` invocation, then Activity Map will also receive this click event and determine if a `linkName` string variable was found. During `s.tl()` execution, that linkName will be set as the Activity Map Link ID. The element clicked that originated the `s.tl()` call will be used to determine the region. Example:

  ```   
  
  <img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>

  ```

b. Via the `s_objectID` variable. Example: 
  
    ``` 

      <img onclick="s_objectID='abc';" src="someimageurl.png"/>
      <a href="some-url.html" onclick="s_objectID='abc';" >
      Link Text Here
      </a> 

    ```

>[!IMPORTANT]
>
>A trailing semicolon (;) is required when using `s_objectID` in Activity Map.

## Can you give me some examples of links that will be tracked?

### Example 1

  ```

    <a href="/home>Home</a>

  ```

### Example 2

  ```

   <input type="submit" value="Submit"/>

  ```

### Example 3

  ```

    <input type="image" src="submit-button.png"/>

  ```

### Example 4

  ```

      <p onclick="var s_objectID='custom link id';">
        <span class="title">Current Market Rates</span>
        <span class="subtitle">1.45USD</span>
      </p>

  ```

### Example 5

  ```
      <div onclick="s.tl(true,'o','custom link id')">
        <span class="title">Current Market Rates</span>
        <span class="subtitle">1.45USD</span>
      </div>

  ```

## Can you give me some examples of links that will NOT be tracked?

1. Reason: Anchor tag does not have a valid `href`:
  `<a name="innerAnchor">Section header</a>`

1. Reason: Neither `s_ObjectID` nor `s.tl()` present:

      ```
      <p onclick="showPanel('market rates')">
        <span class="title">Current Market Rates</span>
        <span class="subtitle">1.45USD</span>
      </p>

      ```

1. Reason: Neither `s_ObjectID` nor `s.tl()` present:

      ```     
      <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
      <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
      <input type="radio" onclick="changeState(this)" name="group1" value="C"/>

      ```  
     
1. Reason: "src" property is missing a form input element:

    `<input type="image"/>`

+++Stop tracking with activity map?

# Stop link tracking

Steps for stopping link tracking in Activity Map or Legacy ClickMap.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> To stop link tracking in... </th> 
   <th colname="col2" class="entry"> Do this... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Remove the following content from the Appmeasurement.js file: 
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/getting-started/get-started-admins/activitymap-enable.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (formerly Visitor ClickMap) </td> 
   <td colname="col2"> <p>Set the <a href="https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/configuration-variables.html"  > trackInlineStats</a> variable to false (this is the default.) The syntax reads as follows: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++PII

>[!CAUTION]
>
>By turning on Activity Map tracking, you may be collecting personally identifiable information (PII) data. This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.

Here are some known cases where PII data might be collected using Activity Map Tracking:

* `Mailto` links. A mailto link is a type of HTML link that activates the default mail client on the computer for sending an e-mail.
* `User ID` links that may show up in the header/footer of a website once the user has logged in.
* For financial institutions, the account number may be shown as a link. Clicking it will collect the text of the link.
* Healthcare websites may also have PII data shown as links. Clicking these links will collect the text of the link, thereby collecting PII data.

+++