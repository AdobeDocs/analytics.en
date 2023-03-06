---
title: getResponsiveLayout
description: Determine which layout of a website is currently being viewed.
feature: Variables
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
---
# Adobe plug-in: getResponsiveLayout

{{plug-in}}

The `getResponsiveLayout` plug-in lets you track which version of your responsive design-based website a visitor is currently looking at. Adobe recommends using this plug-in if your site uses responsive design and you want to track the version of the site viewed by a visitor. This plug-in is unnecessary if your site does not use responsive design.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getResponsiveLayout
1. Save and publish the changes to the rule.-->

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getResponsiveLayout` function uses the following arguments:

* **`ppw`** (required, integer): The maximum width of pixels a browser window can have before the page switches from a phone portrait layout to a phone landscape-based layout
* **`plw`** (required, integer): The maximum width of pixels a browser window can have before the page switches from a phone landscape layout to a tablet-based layout
* **`tw`** (required, integer): The maximum width of pixels a browser window can have before the page switches from a tablet layout to a desktop-based layout

Calling this function returns a string containing two parts delimited by a colon (`:`). The first part of the string contains one of the following values, depending on the browser's width and the above arguments:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (for sites that don't have both portrait and landscape layouts)
* `"tablet layout"`
* `"desktop layout"`

The second part of the returned string is the browser's width and height dimensions. For example, `"desktop layout:1243x700"`.

## Examples

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## Version History

### 1.1 (March 19, 2021)

* Added version number as context data.

### 1.0 (May 2, 2018)

* Initial release.
