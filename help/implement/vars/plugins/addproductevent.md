---
title: addProductEvent
description: Adds custom events to the products and events variable.
---

# Adobe plug-in: addProductEvent

> [!IMPORTANT] This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `addProductEvent` plug-in adds a numeric or currency event to the `products` variable. Adobe recommends using this plug-in if you want to add a numeric or currency event to the `products` variable without worrying about the product string format. This plug-in is not necessary if you don't use numeric or currency events in the `products` variable.

## Install the plug-in using the Adobe Experience Platform Launch extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvent
1. Save and publish the changes to the rule.

## Install the plug-in using Launch custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using `s_gi`). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `addProductEvent` method uses the following arguments:

* **`en`** (required, string): The event to add to the last entry in the `products` variable. If the `products` variable is empty, then a "blank" product entry is created with the event (and its value) attached.
* **`ev`** (required, string): The value assigned to the numeric or currency event in the `en` argument.  Defaults to `1` when not set.
* **`ap`** (optional, boolean): If the products variable currently contains more than one product entry, a value of `true` (or `1`) adds the event to all product entries.  Defaults to `false` when not set.

The `addProductEvent` returns nothing. Instead, it adds the event and its value to the `products` variable. The plug-in also automatically adds the event to the `events` variable, since it is also required there.

## Cookies

The addProductEvent plug-in does not create or use any cookies

## Example Calls

### Example #1

The following code will set the s.products variable equal to `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```
The above code will also set the s.events variable equal to `"purchase,event35"`
### Example #2


The following code will set the s.products variable equal to `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`


```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```
When the third argument in the addProductEvent call is equal to true (or 1), each product entry will have the event specified in the call added to its value
### Example #3

The following code will set the s.products variable equal to `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```
The above code will also set the s.events variable equal to `"purchase,event2,event33,event34,event35"`

### Example #4
The following code will set the s.products variable equal to `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```
The above code will also set the s.events variable equal to `"purchase,event2,event33,event34,event35"`.

**Note**: The second argument in the call can be either an integer **or** a string representing an integer/number
...and the following code runs...

### Example #5

If s.products isn't already set, the following code will set it equal to `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```
The above code will also append `"event35"` to the end of s.events **or**, if s.events isn't already set, the above code will set s.events equal to `"event35"`

## Version History

### 1.0 (October 7, 2019)

* Initial release.
