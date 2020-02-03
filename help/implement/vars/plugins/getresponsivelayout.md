---
title: getResponsiveLayout
description: Determine which layout of a website is currently being viewed.
---

# Adobe plug-in: getResponsiveLayout

## Purpose of This Plugin

### What does this plug-in do?
The getResponsiveLayout plug-in allows you to track which version of your responsive design-based website a visitor is currently looking at

### Why should I use this plug-in?
You should use the getResponsiveLayout plug-in if your site uses responsive design and you want to track which version of the website a visitor is currently experiencing while browsing on his/her desktop/mobile device/etc.

### Why shouldn't I use this plug-in?

You won't need to use the getResponsiveLayout plug-in if your site doesn't use responsive design

## Prerequisites
None

## How to Deploy

You may use one of the following three methods to deploy the getResponsiveLayout plug-in.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plug-in code to your implementation.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install (and publish) the "Common Analytics Plugins" extension
1. For any Launch Rule that you want to use the plug-in in, add an [!UICONTROL action] with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvar
1. Save and publish the changes to the rule

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided above into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in
When calling the getResponsiveLayout plug-in (via JavaScript), be sure to pass in the following arguments:
* **ppw** (required, integer) - Set this equal to the maximum width of pixels a browser window can have before the page switches from a phone portrait layout to a phone landscape-based layout
* **plw** (required, integer) - Set equal to the maximum width of pixels a browser window can have before the page switches from a phone landscape layout to a tablet-based layout
* **tw** (required, boolean) - Set equal to the maximum width of pixels a browser window can have before the page switches from a tablet layout to a desktop-based layout

## Returns
The getResponsiveLayout plug-in returns one of the following values (depending on the browser's width and the arguments you pass into the plug-in) ...
* "phone portrait layout"
* "phone landscape layout"
* "phone layout" (for sites that don't have both portrait and landscape layouts)
* "tablet layout"
* "desktop layout"
...ALONG WITH the browser's width/height dimensions (e.g. "desktop layout:1243x700")

## Cookies
The getResponsiveLayout plug-in does not create or use any cookies

## Example Calls

### Example #1
If...
* Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
* Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
* Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels

...the following code will set eVar10 equal to the current responsive design layout as experience by the visitor as well as the browser's width and dimensions

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```
### Example #2
If...
* Your site has only a phone mode, a tablet mode, and a desktop mode
* Your site switches from phone mode to tablet mode when the browser width is greater than 500 pixels
* Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels

...the following code will set eVar10 equal to the current responsive design layout as experience by the visitor as well as the browser's width and dimensions

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Version History

### 1.0 (May 2, 2018)

* Initial release.
