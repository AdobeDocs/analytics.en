---
title: Activity Map FAQ
description: Frequently asked questions related to Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
---
# Activity Map FAQ

Frequently asked questions related to Activity Map.

+++How do I grant permissions to Activity Map?

Permissions to use Activity Map and its associated dimensions are handled in the [Adobe Admin Console](/help/admin/admin-console/home.md).

The [permission items](/help/admin/admin-console/permissions/product-profile.md) required for Activity Map include:

* **[!UICONTROL Analytics Tools]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Analytics Tools]** > **[!UICONTROL Segment Publishing]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Scroll Reach]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Link By Region]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Region]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Link]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Page]**

See [Product profile permissions for Analytics Tools](/help/admin/admin-console/permissions/analytics-tools.md) for more information.

+++

+++Do all Analytics customers have access to Activity Map?

Organizations with a contract for Adobe Analytics Standard, Premium, and Ultimate have access to Activity Map. These contract types represent the majority of Adobe Analytics customers.

+++

+++How does Activity Map support Single-Page Applications (SPA)?

Every few seconds, Activity Map scans the web page looking for changes. Activity Map finds new content on the page without requiring a reload, but this new content is always attributed to the first page dimension value.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the Links On Page table's Present column for that link updates with [!UICONTROL Displayed] or [!UICONTROL Hidden].

* When user interaction creates new content, any new elements that AppMeasurement determines as a link are added to the [!UICONTROL Links On Page] table. Activity Map sends a new data request that includes these new links. The new links appear in the [!UICONTROL Links On Page] table when the data request is returned.

+++

+++Does Activity Map provide data on links that are viewed but not clicked?

No, Adobe does not automatically track links that were only viewed.

+++

+++What browsers and versions does Activity Map support?

Activity Map supports the latest version of most modern browsers.

+++

+++Does Activity Map increase server calls?

Activity Map does not send server calls by itself. Instead, Activity Map context data variables are included with Analytics page view calls on the subsequent page. However, some previous versions of Activity Map on the Web SDK send a separate call for Activity Map data. If you are on the latest version of the Web SDK, Activity Map data is merged with the following event.

+++

+++Why are some rank numbers missing from the overlay?

Some links, such as those contained within menus, are hidden from the page. As a result, their corresponding link overlays are not shown. Rank is computed for all links on the page, including hidden links.

+++

+++How is link ranking determined in the All Links report?

* **In Gradient and Bubble mode**: The metric column determines rank. For links with the same metric value, the rank is further based on link ID alphabetical order.
* **In Gainer & Loser mode**: The percent gained column determines rank. For links with the same gain, the rank is further based on the link ID alphabetical order.

+++

+++How does Activity Map work with pages that use multiple report suites?

By default, Activity Map uses the report suite that is associated with the first tag on the page. You can select a different report suite through the **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]** tab.

+++

+++How long does Activity Map scan for Adobe Analytics on the page?

Activity map scans for the presence of Adobe Analytics for up to 20 seconds after a page complete event.

+++

+++How does Activity Map handle dynamic content?

Activity Map checks every 2 seconds to see if it has found changes in the state of the web page such as:

* HTML content that has become visible
* HTML content that is hidden
* New HTML content that was injected

If content is hidden or shown, the extension automatically changes the affected links state (and therefore overlays) from hidden to shown or from shown to hidden. If new content is injected, the application retrieves the associated links, pulls analytics data for them, and adds overlays for these links.

+++

+++What metric is the Page Flow report based on?

All data shown is based on page views.

+++

+++Can I export Activity Map data through data feeds?

Yes. The [Data feed columns](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) that Activity Map uses are:

* Activity Map link: `clickmaplink`
* Activity Map page: `clickmappage`
* Activity Map region: `clickmapregion`
* Activity Map link by region: `clickmaplinkbyregion`

+++

+++Do segments work in Live mode?

No, segments do not work in Live mode. 

+++

+++Is Activity Map compatible with virtual report suites?

Yes. However, due to virtual report suite limitations, Activity Map's Live mode is not compatible with virtual report suites.

+++

+++How can I disable Activity Map?

The method to disable Activity Map depends on your implementation type:

* **Web SDK extension**: In the extension configuration settings, uncheck the boxes **[!UICONTROL Collect internal link clicks]**, **[!UICONTROL Collect external link clicks]**, and **[!UICONTROL Collect download link clicks]**.
* **Web SDK JavaScript library**: Set [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) to `false`.
* **Analytics extension**: In the extension configuration settings, uncheck the box labeled **[!UICONTROL Use Activity Map]**.
* **AppMeasurement**: Remove or comment out the Activity Map module within `AppMeasurement.js`, or overwrite the module function call with an empty body:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++What are the system requirements to use the Activity Map overlay?

You can use the latest version of Chrome, Edge, or Firefox with the Activity Map extension.

+++

+++What must I consider when using Activity Map for personally identifiable information?

Consider the following scenarios where personally identifiable data can be collected using Activity Map: 

* **Email links**: If an email address can be clicked to open the user's mail client, Activity Map can collect the email address that was clicked.
* **User ID links**: After a visitor logs in, Activity Map can record any links that contain the visitor's user ID.
* **Sensitive information links**: For financial institutions, sensitive information like account number can be tracked if they are a link and the visitors clicks them.
* **Links containing personal information**: For healthcare websites, links can contain personal information. If a visitor clicks these links, Activity Map collects that link text.

+++

+++What data does Activity Map track by default?

Activity Map tracks the following elements:
    
* An `<a>` or `<area>` tag with an `href` property. Anchor tag links (`#`) are not tracked by default.
* An `onclick` attribute that sets a `s_objectID` variable
* An `<input>` tag or `submit` button with a value or child text
* An `<input>` tag with type `image` and a `src` property
* A `<button>` tag without the attribute `type="button"`. If you want to track `<button>` tags, consider using attributes like `role="button"` or `submit="button"` instead.
    
+++

+++What are some examples of links that Activity Map automatically tracks?

The following are some examples where Activity Map has all of the required information to track a link.

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++What are some examples of links that Activity Map does NOT automatically track?

The following are some examples where Activity Map does not track clicks.

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
