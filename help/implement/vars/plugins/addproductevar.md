---
title: addProductEvar
description: Adds merchandising eVars to the products varaible
---

# Adobe Plugin: addProductEvar

## Plugin Purpose

### What does this plugin do?

The addProductEvar plugin allows you to easily add an Adobe Analytics merchandising eVar that uses product syntax to the products variable without worrying whether the already-existing contents of the products variable will be changed/moved/deleted. 

### Why should I use this plugin?

You should use the addProductEvar plugin if you want to add a merchandising eVar that uses product syntax to the Adobe Analytics products variable.

### Why shouldn't I use this plugin?

You won't need to use the addProductEvar plugin if you don't use merchandising eVars with product syntax or you don't use Adobe Analytics.

## Prerequisites

You must have AppMeasurement (i.e. the base Adobe Analytics Code) to run the addProductEvar plugin.

## How to Deploy

You may use one of the following three methods to deploy the addProductEvar plugin.  If you use a different tag management system besides Adobe Experience Platform Launch, please consult that product's documentation on how to add plugin code to your implementation. 

### Method #1. Edit the Adobe Analytics AppMeasurement file

* Copy + Paste the following code to anywhere within the Plugins section of the AppMeasurement file
```javascript
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvar v1.0 (Requires AppMeasurement) */
s.addProductEvar=function(en,ev,ap){if("string"===typeof en&&"string"===typeof ev&&""!==ev)if(ap=ap||!1,this.products){var e=this.products.split(","),f=e.length;ap=ap?0:f-1;for(var a;ap<f;ap++)a=e[ap].split(";"),a[5]&&-1<a[5].toLowerCase().indexOf("evar")? a[5]=a[5]+"|"+en+"="+ev:a[5]?a[5]=en+"="+ev:a[5]||(a[4]||(a[4]=""),a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[5]=en+"="+ev),e[ap]=a.join(";");this.products=e.join(",")}else this.products=";;;;;"+en+"="+ev};
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
	* Action Type: Initialize addProductEvar
* Save and publish the changes to the rule
	
## How to Run the Plugin

When calling the addProductEvar plugin (via JavaScript), be sure to pass in the following arguments:

* **en** (required, string) - the eVar to add to the last entry currently contained in the products variable.  If the products variable is blank, then the plugin will create a "blank" product entry with the eVar value attached to the end of the entry 
* **ev** (required, string) - the value to be assigned to the eVar 
* **ap** (optional, boolean) - If the products variable currently contains more than one product entry, a value of true (or 1) will add the eVar to **all** the product entries.  Defaults to false (or 0), which will add the eVar to only the **last** entry contained in the products variable 

## Returns

The addProductEvar plugin returns nothing but adds the eVar (and eVar value) specified in the en argument/ev argument to the Adobe Analytics products variable

## Cookies

The addProductEvar plugin does not create or use any cookies

## Example Calls

### Example #1

If...
```javascript
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
```
...and the following code runs...
```javascript
s.addProductEvar("eVar25", "blue");
```
... the final value of s.products will be:
```javascript
s.products=";product1;3;300,;product2;2;122,;product3;1;25;;eVar25=blue"
```

### Example #2

If...
```javascript
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
```
...and the following code runs...
```javascript
s.addProductEvar("eVar25", "blue", 1);
```
... the final value of s.products will be:
```javascript
s.products=";product1;3;300;;eVar25=blue,;product2;2;122;;eVar25=blue,;product3;1;25;;eVar25=blue"
```
When the third argument is equal to true (or 1), each product entry will have the eVar specified in the call added to its value

### Example #3

If...
```javascript
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar25=blue,;product2;2;122,;product3;1;25"
```
...and the following code runs...
```javascript
s.addProductEvar("eVar23", "medium");
s.addProductEvar("eVar24", "women");
s.addProductEvar("eVar25", "red");
```
... the final value of s.products will be...
```javascript
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar25=blue,;product2;2;122,;product3;1;25;;eVar23=medium|eVar24=women|eVar25=red"
```

### Example #4
If...
```javascript
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar25=blue,;product2;2;122,;product3;1;25"
```
...and the following code runs...
```javascript
s.addProductEvar("eVar23", "medium", 1);
s.addProductEvar("eVar24", "women", 1);
s.addProductEvar("eVar25", "red", 1);
```
... the final value of s.products will be...
```javascript
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar25=blue|eVar23=medium|eVar24=women|eVar25=red,;product2;2;122;;eVar23=medium|eVar24=women|eVar25=red,;product3;1;25;;eVar23=medium|eVar24=women|eVar25=red"
```
The addProductEvar plugin does **not** replace eVars that are already set within an individual product entry; it merely appends the values that you specify in the calls.  Hence, use caution when using the plugin so that product entries that already have eVar values bound to them do not have additional duplicate/unnecessary values bound as well. 

### Example #5

If s.products isn't set and the following code runs…
```javascript
s.addProductEvar("eVar25", "blue");
```
...the final value of s.products will be:
```javascript
s.products=";;;;;eVar25=blue"
```

## s Object Replacement
When instantiating the main AppMeasurement library object with a name other than "s", change the following portion of the plugin code from this...

```javascript
s.addProductEvar=function(en,ev,ap)
```
...to this:
```javascript
[objectname].addProductEvar=function(en,ev,ap)
```

## Version History

### 1.0 (2019-10-07)

Initial Release