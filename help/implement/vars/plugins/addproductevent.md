---
title: addProductEvent
description: Adds custom events to the products and events variable
---

# Adobe Plugin: addProductEvent

## Plugin Purpose

### What does this plugin do?

The addProductEvent plugin allows you to easily add an Adobe Analytics custom numeric event or custom currency event to the products variable without worrying whether the already-existing contents of the products variable will be changed/moved/deleted.

### Why should I use this plugin?

You should use the addProductEvent plugin if you want to add a custom numeric event or custom currency event to the Adobe Analytics products variable

### Why shouldn't I use this plugin?

You won't need to use the addProductEvent plugin if you don't need to set a custom numeric event or custom currency event within the products variable.  Using the plugin won't be necessary also if you use only custom counter events or you don't use Adobe Analytics in general

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) and the apl/inList plugins to run the addProductEvent plugin

## How to Deploy

You may use one of the following three methods to deploy the addProductEvent plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation.

### Method #1. Edit the Adobe Analytics AppMeasurement file

Copy+ Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires AppMeasurement and the apl v3.1+/inList v2.0+ plugins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires AppMeasurement and inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 (Requires AppMeasurement) */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```
**NOTE:** Adding the comments/version numbers of the code to the AppMeasurement file will help Adobe with troubleshooting any potential implementation issues.

### Method #2. Edit the Adobe Analytics Extension as contained within Adobe Experience Platform Launch

* Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
* Click on the desired property.
* Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
* Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
* Open the custom code editor and paste the plug-in code provided above into the edit window.
* Save and publish the changes to the Analytics extension.

### Method #3. Leverage the Common Analytics Plugin extension contained within Adobe Experience Platform Launch

* Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
* Click the desired property.
* Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
* Install (and publish) the "Common Analytics Plugins" extension
* For any Launch Rule that you want to use the plugin in, add an [!UICONTROL action] with the following configuration:
	* Extension: Common Analytics Plugins
	* Action Type: Initialize addProductEvent
* Save and publish the changes to the rule

## How to Run the Plugin

When calling the addProductEvent plugin (via JavaScript), be sure to pass in the following arguments:

* **en** (required, string) - the event to add to the last entry currently contained in the products variable.  If the products variable is blank, then a "blank" product entry will be created with the event (and its value) attached to the end.
* **ev** (required, string) - the value to be assigned to the custom numeric/currency event specified in the en argument.  Defaults to 1 when not set or I fh
* **ap** (optional, boolean) - If the products variable currently contains more than one product entry, a value of true (or 1) will add the event to all the product entries.  Defaults to false (or 0), which will add the event (and its value) to only the last entry contained in the products variable

## Returns

The addProductEvent plugin returns nothing but adds the event (and its value) as specified in the en argument/ev argument to the Adobe Analytics products variable.  The plugin will also automatically add the event to the s.events variable since all events that are set in the products variable need to be set also in the events variable.

## Cookies

The addProductEvent plugin does not create or use any cookies

## Example Calls

### Example #1

If...
```javascript
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase"
```
...and the following code runs...
```javascript
s.addProductEvent("event35", "25");
```
... the final value of s.products will be:
```javascript
s.products=";product1;3;300,;product2;2;122,;product3;1;25;event35=25"
```
...and the final value of s.events will be:
```javascript
s.events="purchase,event35"
```

### Example #2

If...
```javascript
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
```
...and the following code runs...
```javascript
s.addProductEvent("event35", 25, 1);
```
... the final value of s.products will be:
```javascript
s.products=";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"
```
When the third argument is equal to true (or 1), each product entry will have the event specified in the call added to its value

### Example #3

If...
```javascript
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```
...and the following code runs...
```javascript
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```
... the final value of s.products will be...
```javascript
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
```
...and s.events will be set as follows:
```javascript
s.events="purchase,event2,event33,event34,event35"
```

### Example #4
If...
```javascript
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```
...and the following code runs...
```javascript
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1); //The second argument can be an integer or a string representing an integer/number
s.addProductEvent("event35", "15", 1);
```
... the final value of s.products will be...
```javascript
s.products=";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"
```
...and s.events will be set as follows:
```javascript
s.events="purchase,event2,event33,event34,event35"
```

### Example #5

If s.products isn't set and the following code runs...
```javascript
s.addProductEvent("event35", "25");
```
...the final value of s.products will be:
```javascript
s.products=";;;;event35=25"
```
In this case, event35 will also be appended to the end of s.events

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...

```javascript
s.addProductEvent=function(en,ev,ap)
```
...to this:
```javascript
[objectname].addProductEvent=function(en,ev,ap)
```
Also be sure to change this...
```javascript
s.apl=function(lv,vta,d1,d2,cc){
```
...to this:
```javascript
[objectname].apl=function(lv,vta,d1,d2,cc){
```
And change this...
```javascript
s.inList=function(lv,vtc,d,cc){
```
...to this:
```javascript
[objectname].inList=function(lv,vtc,d,cc){
```

## Version History

### 1.0 (2019-10-07)

* Initial Release