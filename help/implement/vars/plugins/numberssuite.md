---
title: Numbers Suite
description: Produce and manipulate numbers for use in other JavaScript variables.
feature: Variables
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
---
# Adobe plug-in: Numbers Suite

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The Numbers Suite a series of JavaScript functions. It includes the following plug-ins:

* **`zeroPad`**: Add a specific number of zeros to the beginning of a number. This plug-in is useful if a variable requires a certain number of digits, such as if you work with JavaScript date objects and want to format a date's month and day with two digits instead of just one digit. For example, `01/09/2020` instead of `1/9/2020`.
* **`randomNumber`**: Generate a random number with a specific number of digits. This plug-in is useful if you deploy 3rd-party tags and want a cache-busting random number.
* **`twoDecimals`**: Round a number to the closet hundredth. This plug-in is useful for currency purposes, allowing you to round a number to a valid currency value.

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
    * Action Type: Initialize Numbers Suite
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-ins

The `zeroPad` function uses the following arguments:

* **num** (required, integer): The number to pad. The function rounds down the value of this argument if it contains decimals.
* **nod** (required, integer): The number of digits in the final return value. If the number to pad has less digits than the number of digits to pad to, then the plug-in adds zeroes to the beginning of the `num` argument.

The `randomNumber` function uses the following arguments:

* **nod** (optional, integer): The number of digits in the random number that you want to generate. The maximum value is 17 digits. The default value is 10 digits.

The `twoDecimals` function uses the following arguments:

* **val** (required, number): A number (represented by either a string or number object) that you want to round to the nearest hundredth.

## Returns

* The **zeroPad** function returns a string equal to the `num` argument but with a specific number of zeroes added to the beginning of its value, which ensures that the return value has the correct number of digits.
* The **randomNumber** function returns a string equal to a random number with the desired number of digits.
* The **twoDecimals** function returns a number object rounded to the closest hundredth.

## Example Calls

### zeroPad examples

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber examples

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### twoDecimals examples

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Version History

### 1.0 (May 25, 2019)

* Initial release.
