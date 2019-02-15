---
description: Describes how to enable and implement a merchandising variable.
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
seo-description: Describes how to enable and implement a merchandising variable.
seo-title: Implement a merchandising variable
solution: Analytics
title: Implement a merchandising variable
topic: Developer and implementation
uuid: 49e97dd0-e56b-4d34-b274-8113b24cb905
---

# Implement a merchandising variable

Describes how to enable and implement a merchandising variable.

## Enable a Merchandising Variable {#section_331B41FF5AED42F2AEFE043DD60238C7}

Merchandising can be enabled for any custom eVar on the **[!UICONTROL Admin Tools]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Conversion Variables]** page (you no longer need to call Adobe): 

![](assets/merch-enable.png)

| Setting | Description |
|--- |--- |
|Expire After|Determines how long merchandising values should persist.|
|Merchandising|Product Syntax : The value is set within s.products.    Conversion Variable Syntax : The value is set in the designated merchandising  s.eVar.|
|Merchandising Binding Event (Conversion variable syntax only)|Indicates when a product should be tied to the current merchandising category. Multiple events may be selected by holding down Ctrl and clicking on multiple items in the list.   Note:  When "Product Syntax" is selected, you can not choose an event (it is disabled, but not grayed out). You can select an event only when the "Conversion Variable Syntax" is selected.|

## Implementing Using Product Syntax {#section_2774578D09CE40A093CB0D0A294DBF7C}

When Product Syntax is enabled, the merchandising category is populated directly within the products variable, so selecting and setting a binding event is not required. This is the recommended method and should be used unless the value is not available to set in `s.products` when the success event takes place.

* **Syntax** 

```js
  s.products="category;product;quantity;price;event_incrementer; 
<codeph outputclass="syntax">
  eVarN=merch_category| 
 <codeph outputclass="syntax">
   eVarM=merch_category2" 
 </codeph outputclass="syntax"> 
</codeph outputclass="syntax">
```

* **Example** 

```js
  s.events="prodView" 
  s.products=";Fernie Snow Goggles;;;; 
<codeph outputclass="syntax">
  eVar1=goggles" 
   In 
</codeph outputclass="syntax">
```

The value "goggles" for eVar1 is assigned to the product "Fernie Snow Goggles". All subsequent success events (product adds, checkouts, purchases, and so on) that involve this product are credited to "goggles".

## Implementing Using Conversion Variable Syntax {#section_6AE10F69F4A14636AB050BEA89A34E4E}

Conversion Variable Syntax should be used when the eVar value is not available to set in `s.products`. This typically means that your page has no context of the merchandising channel or finding method. In these cases you must set the merchandising variable before you arrive at the product page, and the value persists until the binding event occurs.

When the binding event selected during configuration occurs, the persisted value of the eVar is associated with the product. For example, if prodView is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. Only subsequent binding events can update a merchandising eVar that has already been assigned to a product.

* **Syntax** On the same or previous page before the binding event:

  ```js
  s.eVar1="merchandising_category"
  ```

  On the page where the binding event occurs:

  ```js
  s.events="prodView" 
  s.products="category;product"
  ```

* **Example** Page 1 of the visit:

  ```js
  s.eVar1="Outdoors:Ski Goggles"
  ```

  Page 2 of the visit:

  ```js
  s.events="prodView" 
  s.products=";Fernie Snow Goggles"
  ```

  The value "Outdoors:Ski Goggles" for eVar1 is assigned to the product "Fernie Snow Goggles". All subsequent success events (product adds, checkouts, purchases, and so on) that involve this product are credited to "goggles".

Additionally, the current value of the merchandising variable is tied to all subsequent products until one of the following conditions is met:

* eVar expires (based on the "Expire After" setting) 
* The merchandising eVar is overwritten with a new value.

For more information, see " [Advanced Conversion Syntax Merchandising](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/)" at [!DNL analyticsdemystified.com]. 
