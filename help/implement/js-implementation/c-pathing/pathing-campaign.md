---
description: Helps you answer the question, "After a user clicks into my site from a campaign, where do they go on my site?"
keywords: Analytics Implementation
seo-description: Helps you answer the question, "After a user clicks into my site from a campaign, where do they go on my site?"
seo-title: Pathing by campaign or tracking code
solution: Analytics
title: Pathing by campaign or tracking code
topic: Developer and implementation
uuid: eb6e3484-1b40-4ec6-8017-ac1003cdf636
index: y
internal: n
snippet: y
---

# Pathing by campaign or tracking code

Helps you answer the question, "After a user clicks into my site from a campaign, where do they go on my site?"

To answer this question, you need to set aside an [!UICONTROL sprop] to be used for this report. You then need to structure the data to populate into the prop in such a way that it makes sense when pathing is enabled.

For this example, you are going to use [!UICONTROL prop1] as your campaign pathing prop. Now you want to populate this [!UICONTROL sprop] with the same value you put in the [!UICONTROL page name] variable. See below:

```js
s.prop1=s.pageName;
```

You should do this on all pages unless the person has clicked from a campaign. If they have clicked from a campaign and are on the landing page of the campaign, then you populate the prop with a concatenation of the campaign and the [!UICONTROL pagename]. See below:

```js
 s.prop1=s.campaign + ‘ : ’ + s.pageName;
```

If the campaign they clicked was named "banner1234," and the page it landed on was named "Home Page," the value in that prop would be "banner1234 : Home Page." On every subsequent page you put the [!UICONTROL pagename] in the prop as shown above.

When a user clicks this campaign and views four total pages in that visit, you get the following values in the sprop in this order:

```js
“banner1234 : Home Page” > “Page 2” > “Page 3” > “Page 4”
```

With our data captured in [!UICONTROL prop1] in this way, with pathing enabled on this prop, you can now look at one of various pathing reports to understand how they path through the site after they click from a campaign.

You can specify the start page from which to start the path report. In this case, you selected "banner1234 : Home Page", because you want to know where users went after they clicked from campaign "banner 1234." This report is only an example of one of many path reports. 
