---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# products

The  variable is used for tracking products and product categories as well as purchase quantity and purchase price. Products is typically set in conjunction with a cart event or a  event.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. This update may cause an increase in *`prodView`* events. *`prodViews`* will increase only when: 
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
>
>1. The *`products`* variable is not empty.
>
>A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

The *`products`* variable tracks how users interact with products on your site. For instance, the products variable can track how many times a product is viewed, added to the shopping cart, checked out, and purchased. It can also track the relative effectiveness of merchandising categories on your site. The scenarios below are common for using the products variable.

The *`products`* variable should always be set in conjunction with a success event.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Max Size </th> 
   <th class="entry"> Debugger Parameter </th> 
   <th class="entry"> Reports Populated </th> 
   <th class="entry"> Default Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>The " <span class="wintitle"> products </span>" string has a maximum size of 64k. </p> </td> 
   <td> products </td> 
   <td> Products <p>Categories (optional) </p> <p>Revenue (optional) </p> <p>Units (optional) </p> <p>Custom Events (optional) </p> <p>eVars (optional) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Syntax**

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

|  Field  | Definition  |
|---|---|
|  Category  | Contains the associated product category. In version 15, products can be associated with multiple categories which fixes a limitation present in version 14. If you were previously not recording a product category, you are encouraged to start populating this field for report suites that are on version 15.  |
|  Product  | (Required) The identifier used to track a product. This identifier is used to populate the Products report. Be sure to use the same identifier through the checkout process.  |
|  Quantity  | The number of units purchased. This field must be set with a purchase event to be recorded.  |
|  Price  | Refers to the combined cost of the total quantity purchased (units x individual unit price), not to the individual price. This field must be set with a purchase event to be recorded.  |
|  Events  | Currency events associated with the specified product. See [Product-Specific Currency Events](https://helpx.adobe.com/analytics/kb/comparing-event-types.html) and [Order-Wide Currency Events](https://helpx.adobe.com/analytics/kb/comparing-event-types.html).  |
|  eVars  | Merchandising eVar values associated with a specific product. See [Merchandising Variables](/help/components/c-variables/c-merch-variables/var-merchandising.md).  |

The values included in the *`products`* variable are based on the type of event you are recording. The category/product delimiter (;) is required as a place holder when omitting Category. Other delimiters are required only if they are necessary to distinguish which parameter you are including, as shown in the examples on this page.

**Setting products with Non-Purchase Events**

The *`products`* variable must be set in conjunction with a success event.

**Setting products with a Purchase Event**

The *`purchase`* event should be set on the final confirmation ("Thank You!") page of the order process. The product name, category, quantity, and price are all captured in the *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**Product-Specific Currency Events**

If a currency event receives a value in the *`products`* variable instead of the events variable, it applies only to that value. This is useful to track product-specific discounts, product shipping, and similar values. For example, if you configured event 1 to track product shipping, a product with a "4.50" shipping charge might appear similar to the following:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

In this example, the value of 4.50 is associated directly with the "Running Shoes" product. If you add event1 to the products report, you'll see "4.50" listed for the "Running Shoes" line item. Similar to Price, this value should reflect the total for the quantity listed. If you have 2 items with a 4.50 shipping charge each, event1 should be "9.00".

**Order-Wide Currency Events**

If a currency event receives a value in the events list instead of the *`products`* variable, it applies to all products in the *`products`* variable. This is useful to track order-wide discounts, shipping, and similar values, without modifying the product price or by tracking it in the product list separately.

For example, if you configured event10 to contain order-wide discounts, a purchase with a 10% discount might appear similar to the following:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

On currency event reports, the report total represents the de-duplicated event total (in this example, the total amount of discounts during the reporting period), not the sum of the event values for each product. For example, you would see "9.95" listed for both "Running Shoes" and "Running Socks", and the total would also be "9.95".

> [!NOTE] if a value for the same Numeric/Currency Event is specified in the *`products`* variable and in the *`events`* variable, the value from the *`events`* is used.

**Pitfalls, Questions, and Tips** 

* The *`products`* variable should always be set in conjunction with a success event (events). If no success event is specified, the default event is prodView.

* Strip all commas and semicolons from product and category names before populating products.
* Strip all HTML characters (registered symbols, trademarks, and so forth).
* Strip currency symbols ($) from the price.

**Examples** 

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

