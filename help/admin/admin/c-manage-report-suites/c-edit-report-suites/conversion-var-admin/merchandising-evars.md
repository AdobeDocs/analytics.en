---
title: Merchandising eVars and Product Finding Methods
description: A deep dive into the concepts behind merchandising eVars and how they process and allocate data.
feature: Admin Tools
exl-id: 9e1a39aa-451f-49bb-8e39-797b6bbd5499
---
# Merchandising eVars and product finding methods

This very detailed document explains the concepts behind merchandising eVars, which process and allocate data differently than standard eVars. It also explains how merchandising eVars relate to product finding methods.

## Overview

Using merchandising eVars allows you to allocate any successful activity to the values captured by the eVars at a *per-product* level instead of a *per-visit/per-order* level.

While most retail websites have many ways to find products, Adobe considers the following to be the fundamental product finding methods that every retail client should track in Adobe Analytics:

* Internal Search Keywords
* Internal Campaign Tracking Codes
* Merchandising/Browse Categories
* Cross-selling Links

For the purposes of this document, let's map a few eVars to the solutions as follows:

* eVar2: Internal Search Keywords
* eVar3: Internal Campaign Tracking Codes
* eVar4: Merchandising/Browse Categories
* eVar5: Cross-Selling Links

We can use an additional eVar to measure the performance of all product finding methods in relation to each other. In addition to the finding methods described above, the eVar includes other finding methods in its comparison, such as links to product detail pages from external websites.

* eVar1: Product Finding Methods

Instead of configuring any of these variables to be standard eVars, configure them to be merchandising eVars.

To demonstrate how to set these variables, here is an example where a visitor decides to use the internal keyword search "sandals" to find a product on the site. On the keyword search results page, you must capture data in at least two eVars:

* `eVar2` is equal to the keyword that was used in the search ("sandals")
* `eVar1` is equal to the product finding method used ("internal keyword search").

When you set these two variables equal to these specific values, you know that the visitor is using the internal keyword search term of "sandals" to find a product. At the same time, you know that the visitor is not using the other product finding methods to find products (for example, the visitor is not browsing through product categories at the exact same time they are performing a keyword search). To ensure that proper per-product allocation takes place, these unused methods should not get credit for finding a product that was found via an internal keyword search. Hence, you must insert logic into the code (such as AppMeasurement, AEP Web SDK, and so on) that automatically sets the eVars associated with these other finding methods equal to a "non-finding method" value.

For example, when a user searches for products using the keyword "sandals", the Analytics code's logic should set the variables equal to the following on the internal keyword search results page:

* eVar2="sandals": the keyword "sandals" was used in the internal keyword search
* eVar1="internal keyword search": the "internal keyword search" finding method was used
* eVar3="non-internal campaign": an internal campaign was not used to access the search results page
* eVar4="non-browse": a browse category was not accessed on the search results page
* eVar5="non-cross-sell": a cross-sell link was not clicked on the Search results page

## Merchandising eVars settings

Here are the different settings that you can use with your merchandising eVars. The following screenshot comes from the Report Suite Manager. Access it by going to [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Conversion Variables] > [!UICONTROL Add new] > [!UICONTROL Enable Merchandising].

![Merch eVars](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/assets/merch-evars1.png)

Find more detail on these settings in the sections below the table.

| Setting  | Description  |
|--- | --- |
| Name | The Name, or the reporting dimension that the variable is meant to be associated with. If `eVar1` is meant to capture Product Finding Methods, then the Name field for `eVar1` should be set to "Product Finding Methods". |
| Merchandising | The type of syntax that will be used to capture the merchandising eVar values |
| Allocation | Helps determines the merchandising eVar value that should receive credit when a successful event takes place. |
| Expire After | Determines when existing product and merchandising eVar bindings should no longer be in effect. |
| Type | The type of data being collected in the merchandising eVar |
| Merchandising Binding Event | The event(s) that determine when a product should be bound to a merchandising eVar value |
| Reset | A trigger that will reset all back-end data for the eVar at that point |
| Enable Merchandising | A flag that needs to be set to "Enabled" to turn the eVar from a standard eVar to a Merchandising eVar |

### Enable Merchandising

When the "Enable Merchandising" setting is set to "Enabled", all the settings as described below appear in the Report Suite Manager. When the "Enable Merchandising" setting is set to "Disabled", only the standard eVar settings are available.

### Merchandising

This option is not available for standard eVars. The [!UICONTROL Merchandising] setting lets you to pick either [!UICONTROL Conversion Variable Syntax] or [!UICONTROL Product Syntax] as the method for capturing the merchandising eVar's value.  

**[!UICONTROL Conversion Variable Syntax]** means that you set the eVar value in its own variable. For example, with Conversion Variable Syntax, the `eVar1` value of "internal keyword search" is set as follows within the page code (or the AppMeasurement code, AEP Web SDK code, and so on):

`s.eVar1="internal keyword search";`

With **[!UICONTROL Product Syntax]**, however, the eVar is set within only the Adobe Analytics products variable. The Analytics products variable is divided up into six different portions per product:

`s.products="[category];[name];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Category] and [!UICONTROL Name] identify the given product.
* [!UICONTROL Quantity] and [!UICONTROL Revenue] are useful when a product purchase is being tracked.  
* [!UICONTROL Events] is useful for recording custom incremental or currency event values that are not meant to be counted as revenue (such as shipping, discounts, etc.)

Merchandising eVars that are configured to use Product Syntax are set within the final portion of the products variable. For example, suppose that a visitor used an internal keyword search to find product ID "12345". The Product syntax-based way for setting eVar1 in this example would look like this:

`s.products=";12345;;;;eVar1=internal keyword search";`

Notice that we still have semicolon-delimited placeholders for the quantity, revenue, and event portions of the products variable.  Without these placeholders, the `eVar1` setting of internal keyword search would be completely ignored.

### Allocation

The term "Allocation" for merchandising eVars is misleading, especially for merchandising eVars that use Conversion Variable Syntax. All standard eVars can have their own individual allocation setting. However, merchandising eVars with Conversion Variable Syntax use only the "Most Recent (Last)" allocation setting, regardless of what the allocation settings in the Report Suite Manager show.

Understanding what this setting does means understanding the difference between eVar allocation and merchandising eVar binding. For merchandising eVars, "Merchandising eVar Binding" is a more appropriate name for this "Allocation" setting.

#### Standard eVar allocation setting

Whenever any eVar with standard syntax is collected from an image request, the Adobe Analytics processing servers insert data into another database column, called a `post_evar` column. Since eVars are meant to be persistent - they expire at some point beyond the current hit in most cases - the servers then set this `post_evar` column on every subsequent image request. It is set equal to the last value passed into its corresponding eVar. For standard eVars, when a success event takes place, Adobe Analytics uses the `post_evar` column instead of the regular eVar column to determine the eVar value that should be given credit for the event.

For standard eVars, the Allocation setting determines whether the first or the last eVar value that was collected during a certain period will be inserted into the `post_evar` column. If the Allocation setting for a standard eVar is equal to "Original Value (First)", then the first eVar value collected from the visitor is inserted into the `post_evar` column for all subsequent image requests. This continues for all future requests sent from this visitor's browser until the eVar expires per its "Expire After" setting.

If a standard eVar's Allocation setting is equal to "Most Recent (Last)", then the most recent eVar value collected from the visitor is filled into the `post_evar` column for all subsequent image requests. "Most Recent (Last)" allocation implies that the `post_evar` value changes every time its corresponding eVar is set to a new value in any image request. "Original Value (First)" allocation implies that the `post_evar` column does not change across hits even though its corresponding eVar might be set to a different value in a future image request.

#### Merchandising eVar allocation (binding) setting

As mentioned before, all merchandising eVars with Conversion Variable Syntax have only "Most Recent (Last)" allocation. Thus, the Allocation setting for merchandising eVars does not determine what values are inserted into the post_evar column as a visitor continues to use the site. Rather, this setting determines which eVar value binds to a product and how such products allocate their success events back to the eVar values they are bound to.

The following happens when a merchandising eVar's Allocation (i.e. binding) setting is set equal to "Original Value (First): Any products that are set alongside the post_evar column and that have not been previously been bound to the post_evar column's corresponding "pre-processed" eVar will be bound to the value contained in the post_evar column.  This binding between eVar value and product never changes until the eVar expires per the "Expire After" setting in the Report Suite settings.

Any time an image request meets the criteria that would otherwise bind an already-bound product to the most recently set eVar value, the "Original Value (First)" setting forces the Adobe Analytics data collection servers to ignore any such further attempts to do so. The opposite happens with merchandising eVars with the Allocation (binding) setting equal to "Most Recent (Last)". Any time an image request meets the criteria that bind a product to a merchandising eVar, the product will bind (and rebind) itself to the most recent value passed into the eVar, or the value that's (always) contained in the `post_evar` column.

As mentioned previously, merchandising eVars allow you to allocate success events to eVar values at a per-product basis instead of at a per-visit/per-order basis. So, whenever a bound product has a success event (such as a cart add or purchase) associated with it, the success event gives its credit to both the product and the merchandising eVar values that the product is bound to at that time.

### Expire After

The expiration setting of a merchandising eVar lets you choose

* When both the product/eVar bindings should expire, and

* When the post_evar column should no longer be automatically filled in after an eVar has been passed into an image request.

Expiration for an eVar can take place when either a success event is recorded or a certain period of time passes. Adobe Analytics allows for only one Expiration setting at a time, per eVar.

For the Product Finding Method, the best practice for setting a merchandising eVar's expiration should be setting it equal to

* EITHER the amount of time that a product is held in a site's shopping cart before the site automatically removes it from the cart (e.g. 14 days, 30 days, etc.)
* OR when the purchase event takes place.

With either setting, any products that a visitor purchases have the order/unit/revenue credit allocated to the merchandising eVar values that the products were bound to at that time.

### Type

The eVar type setting determines what type of data is inserted into the eVar. In most cases, this value should be equal to "Text". Using "Counter" for a merchandising eVar is rare. However, "Counter" could be used to allocate success to Counter eVar values on a per-product basis.  Discussing solutions with a type of "Counter" is outside the scope of this document.

### Merchandising Binding Event

The Merchandising Binding Event setting lets you specify the conditions for a product to be bound to a merchandising eVar's value. These conditions are limited to the firing of specific success events or eVars only. Firing traffic variables (e.g. props) have no effect on merchandising bindings.

Note that the Merchandising Binding Event setting can bind a product to an eVar value through more than one event. Examples:

* Via a product view event
* Via a cart add event
* Via a purchase event

By default, the setting binds a product to a merchandising eVar value whenever any other event/eVar (merchandising or standard) is contained in the same image request as the product.

### Reset

The Reset setting lets you to immediately "expire" all eVar values for all visitors who currently have a `post_evar` value in the Adobe Analytics backend database. It also eliminates all current product/eVar bindings.

>[!IMPORTANT]
>Adobe does not recommend using the Reset setting unless you fully intend to have the eVar start over with a completely "clean slate" of data from the time that the reset takes place.

## Which settings should you use?

Among the many available setting combinations, you might wonder: Which settings are best practice?

If you want to bind "internal keyword search" to product ID 12345, the products variable would be set as follows:

`s.products=";12345;;;;eVar1=internal keyword search";`

Any success events (cart adds, purchases) that are captured at the same time as productID 12345 are credited to both product ID 12345 and the eVar1 value of "internal keyword search". The only way a different eVar1 value receives credit for the success events associated with product ID 12345 is if eVar1 were later set to a different value within the products variable (alongside product ID 12345).

For Example:

```js
s.products=";12345;;;;eVar1=internal campaign";
```

This variable setting changes the binding of product ID 12345 from the eVar1 value of "internal keyword search" to the eVar1 value of "internal campaign". Also, this rebinding change takes place when the eVar is configured to use Product Syntax and the Allocation (binding) setting of "Most Recent (Last)". If the Allocation (binding) setting were instead set to "Original Value (First)", setting eVar1 equal to "internal campaign" alongside product ID 12345 would not rebind product ID 12345 to the eVar1 value of "internal campaign". Instead, the binding would remain with the originally-bound value – "internal keyword search".

### Challenges of using Product Syntax

Without careful planning, several issues can arise from using Product Syntax. Let's take the case of using multiple eVars to track product finding methods on the website. Here, each individual product finding method eVar must be set at the same time in order to give a particular finding method eVar credit (and the other finding method eVars no credit). Product Syntax can be used in such scenarios but the resulting code to deploy is more complicated.  

If we use our original "sandals" example and adapt it to use Product Syntax (assuming the visitor found a product with the ID of "sandal123" using the keyword term of "sandals") the resulting products variable must be set as follows:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

While the syntax of the products variable is long in this example, it will bind each of the eVar values seen to the product ID of "sandal123". From then on, any success events (e.g. cart adds, purchases) that are captured at the same time as the "sandal123" product are credited to the eVar values that were last bound to the product.  This code sample shows if a purchase of 1 unit of the "sandal123" product (for $79.95) takes place after the eVars above were bound to the "sandal123" product:

```js
s.products=";sandal123;1;79.95";
s.events="purchase";
```

The following values would all have 1 order, 1 unit, and $79.95 of revenue attributed to them:

* eVar2 value of "sandals"
* eVar1 value of "internal keyword search"
* eVar3 value of "non-internal campaign"
* eVar4 value of "non-browse"
* eVar5 value of "non-cross-sell"

This is correct attribution, which is not an issue. Rather, the major dilemma with this approach is determining how and when to set the Product Finding Method eVars.

In most cases with Product Syntax, the Product Finding Method eVars would have to be set on a product detail page rather than on the page that the finding method was actually used (e.g. on the keyword search results page, the browse page, the internal campaign landing page, etc.). It is reasonable to assume that a product has not been truly "found" until a visitor interacts with a product to some degree. As such, these eVars (using Product Syntax) should not be set on the finding method page because multiple products are (usually) displayed on such pages. We want to bind the finding method value to only those products that the visitor has interacted with.

Moreover, while viewing a finding method page, visitors might have the ability to either click on a link that brings them to an individual product detail page or add an individual product to the cart directly from the finding method page. Using our "sandals" search keyword example, if a visitor adds the "sandal123" product to the cart directly from a keyword search results page, the code for capturing the cart add (via the Add-to-Cart button's onClick event, etc.) would have to be either generated dynamically at the time the cart add takes place or "hard-coded" directly via the page code or a tag management system.  Regardless, the code to fire in such cases would look something like this:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

This code properly binds the eVar values seen above to the "sandal123" product. However, in order to set these values appropriately when the click event takes place, the developer must:

* Add server-side logic to the search results page that determines the values that must be inserted into the product finding method eVars, and
* Assemble the entire products variable seen above with no syntax errors.

Also, if a visitor decides to "find" the product by clicking a link to its product detail page, the developer must:

* Pass the product finding method details (as seen above) from the finding method page over to the product detail page, and
* Recreate the same products variable value from the items that were just passed over from the previous page.

### Where Product Syntax is useful

Product Syntax is still useful when

* Multiple products with the same product IDs are interacted with at the same time, and
* The eVars to be bound to such products need to have different values per product ID.  

For example, many clothing products have "Child SKUs", which designate the size, color, style, and any other attributes. These attributes separate out a single child product from other products that belong to the same parent product. Let's say you decide to purchase a medium blue t-shirt plus a large red t-shirt. Assume that both shirts have the parent product ID of "tshirt123" and `eVar10` has been configured to capture child SKUs. The variables set on the purchase confirmation page would be set as follows:

```js
s.events="purchase";
s.products=";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

In this case, both `eVar10` (childSKU) values of "tshirt123-m-blue" and "tshirt123-l-red" get credit for the purchase of their respective instances of product ID "tshirt123".

### Challenges with "Most Recent" Allocation

You could face additional issues by using the Allocation (binding) setting of "Most Recent (Last)". In many web-browsing experiences, visitors "re-find" a product that they have already viewed and/or added to the cart. This usually happens via a subsequent visit or just before they decide to complete a purchase. Suppose that during a visit to the site, a visitor finds the "sandal123" product via the keyword search of "sandals". They immediately add it to the cart from the keyword search results page. The code that captures the cart add would be set as follows:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross";
```

As a result, each of the eVar values seen in this image request are bound to the "sandal123" product.

Now, imagine the visitor doesn't purchase the product during this visit, but comes back to the site three days later with the "sandals123" product still in the cart. The visitor wants to learn more about the product before making the purchase. But instead of using a keyword search to find the product, the visitor browses through the site. They end up in the "womens > shoes > sandals" merchandising browse section just before "re-finding" the product. When they end up "re-finding" the product detail page for the "sandal123" product, the variables would be set as follows (on page load):

```js
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

With an Allocation (binding) setting of "Most Recent (Last)", the "sandal123" product rebinds to completely different eVar values than what it was originally bound to. Moreover, if the visitor then completes the purchase of "sandal123", all purchase credit is given to these newly bound eVar values instead of the originally bound values!

The question here is: Which eVar values should get credit for the purchase"? Remember that the visitor initially found the "sandal123" product via an internal keyword search. They then  added it to the cart directly from the search results page. Therefore, the eVar1 value of "internal keyword search" (and the eVar2 value of "sandals") should get credit for the purchase. However, the Allocation (binding) settings were set to "Most Recent (Last)". Hence, the eVar1 value of "browse" (and the eVar4 value of "womens > shoes > sandals") gets the purchase credit instead. The reason is that they were the last values bound to "sandal123" before the visitor completed the purchase.

A solution to this problem is to change the Allocation (binding) setting of the merchandising eVar from "Most Recent (Last)" to "Original Value (First)". This way, the original eVar values bound to the "sandal123" product gets credit when the purchase takes place, regardless of how many times the visitor "re-finds" the product.

If the visitor adds a product to the cart but never purchases it, the eVar expiration allows a new finding method value to be bound to the product. The eVar expiration should equal the time that a website lets a product stay in the shopping cart before it is automatically removed.

### Using Conversion Variable Syntax

Let's return to the "Product Syntax" vs. "Conversion Variable Syntax" question. Adobe has discovered an easier method for both collecting the product finding method merchandising eVars and binding their values to products that visitors have found: Using Conversion Variable Syntax reduces the implementation work that the client's developers are responsible for. It still offers the same - or better - information than the Product Syntax method. Developers simply need to follow the deployment instructions that they were given, and the rest of the code can be placed into the Adobe AppMeasurement/AEP Web SDK file.

For example, let's look at the recommended solution for tracking internal keyword search performance. It says that on the keyword search results page, the code captures the keyword searched for via a prop (for example, prop4) and another prop (for example, prop5). These props track the number of results shown from the search. Whenever an Adobe Analytics image request is generated on the search results page, it used the data layer objects (or page code) deployed by the developers to fill in the above variables (the props).

Additional logic contained within the AppMeasurement/AEP Web SDK file can fill in the remainder of the variables (the merchandising eVars/dimensions) that need to be set at the same time.  
For instance, if a new visitor were to do a keyword search for "sandals", which returned 25 results on the search results page, the code to be fired (via the page code OR data layer capture) would look like this:

```js
s.prop4="sandals";
s.prop5="25";
```

Logic within the AppMeasurement/Analytics SDK file could then automatically transform this snippet of code into the following:

```js
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

There is no need to worry about passing data from page to page and trying to create a rather large, unwieldy string to be inserted into the products variable. Instead, developers can implement their portion of the tracking solutions – what's inserted into the props – and leave the rest of the implementation to the custom code provided by Adobe Consulting.

As explained earlier, all merchandising eVars that use Conversion Variable Syntax have the Allocation setting of "Most Recent (Last)". Once an eVar is set equal to any value, that value persists across all subsequent hits (via the post_evar column). It persists until it is set to a different value or until the eVar expires. Thus, any products anyone interacts with after the eVars are set, if they have not already been bound to those eVars, bind to the "Most Recent (Last)" values passed into the eVar.  

Using our above example, the `eVar2` value of "sandals" and the eVar1 value of "internal keyword search", etc. persist on all pages seen after the keyword search took place. They persist until the eVars are overwritten with other values. Let's say a visitor clicks on a link to the product detail page for the "sandal123" product ID from the keyword search results page.  Then the "sandal123" product ID (if it hasn't been bound yet) binds to the each of the values contained in the post_evar columns, or to the eVar values that were collected from the previous (search results) page.

There is one more thing to reconsider with Conversion Variable Syntax. It's that binding events must be set up to bind an eVar value to a product. Simply setting a merchandising eVar (in its own variable) alongside a product (in the products variable) in an Adobe Analytics image request does not necessarily bind the eVar value to the product.  Instead, the Merchandising Binding Event setting, which is set in the Report Suite Manager, determines the criteria that binds an eVar value to a product

Since we want to bind the Product Finding Method eVar values to products whenever a product interaction takes place – implying that a product has been "found" – it is safe to assume that the most common "product found" interactions that can take place are either a product view (when visitors go to a product detail page) or a cart add (when visitors add a product to the cart directly from a product finding method page).

Thus, we can choose these two events (prodView, scAdd) as the "fundamental" merchandising binding events.
Here is what happens when either of these binding events are contained within an image request. Any product IDs that are contained in the same request (within the products variable) and which have not been bound to a merchandising eVar will bind to the most recent values passed into the merchandising eVar (post_evar columns). Any attempt to rebind these products after this original binding takes place are ignored when the Allocation (binding) setting is set equal to "Original Value (First)".  

### Best Practice settings

Following are the best practice settings. They easily implement the product finding method with the best results. Adobe recommends that clients configure each of their product finding method merchandising eVars (in general) as follows:

* Merchandising Enabled: Enabled
* Merchandising [syntax]: Conversion Variable Syntax
* Allocation [binding]: Original Value (First)
* Expire After: The amount of time a product stays in a cart before it is automatically removed (e.g. 14 days, 30 days, etc.).  If no such time exists, then Expire After the "purchase" event
* Type: Text
* Merchandising Binding Events:  Product View, Cart Add, and Purchase

## What do Binding Events actually do?

When a binding event is contained in the same server call as the products variable, the Merchandising eVar (using Conversion Variable Syntax) values in their post column bind to the products variable. Based on the earlier example , assume that one server call contains the following Merchandising eVar values:

```js
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

As explained earlier, the above eVars persist beyond the current hit via their respective post_evar column. Hence, Adobe's servers transform the eVars above into the following:

```js
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

These post columns are stored in Adobe's database and persist beyond the current hit where they were initially set. This assumes that no expiration or variable resetting takes place.  Adobe's servers have these post_evar values "available" at the time that they process any future server calls that contain both the binding event and the products variable.

The binding that takes place is solely between these post_evar values and the contents of the products variable. The binding event does not necessarily "bind" to either the eVars or the products variable. It is the "catalyst" that tells the Adobe servers to bind the post_evar values to the products.

Assume that on a future hit, the following variables are set:

```js
s.products=";sandals123"
s.events="prodView";
```

In the post_evar columns, the Adobe processing servers see this hit as follows:

```js
s.products=";sandals123";
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Assume eVar1, eVar2, eVar3, eVar4, and eVar5 have been configured to use `prodView` as a binding event. If any one of these eVars is not configured to use prodView as a binding event, then binding between that (misconfigured) eVar and the products variable will not take place.

Binding produces some very interesting results, which can be seen in the post_products column's value. The binding transforms the above code and sets a few more post columns, as follows:

```js
post_events="prodView";
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

The value contained in the post_products column might be familiar to you. Scroll up in this document and compare this post_products value and the s.products value as shown under. Notice that the post_products column is set using Product Variable Syntax!

This means that Binding "copies" the Conversion Variable Syntax eVar values into the products variable via Product Syntax. This copying action takes place only when the products variable and a binding event (set via the eVar configuration) are contained in the same request. At that point, the value(s) contained in the post_eVar column(s) are bound to the product. This Binding is represented via Product Syntax as stored in the post_products column.

## Merchandising eVars, the Instances metric, and Attribution IQ

When a standard eVar is sent in an Analytics server call, the value in its post_evar column always gets an Instance attributed to it. Instances represent the number of times that an eVar has been set equal to a particular value in an image request.

For example, assume that `eVar10` is a standard eVar with [!UICONTROL Last Touch] attribution. If you set `s.eVar10="hello world"` on any page, the value of "hello world" is passed over to the post_evar10 column when Adobe processes the hit. The instances metric is equal to "1" for each individual `eVar10` setting of `hello world`. Keep in mind that an instance is not always recorded when the post_evar column has a value. Rather, the post_evar column determines which value gets the instance when an instance is recorded.

Instances for a merchandising eVar give attribution to the values the eVar collects. But this happens only when a product that was bound to the merchandising eVar value was "interacted" with at the same time.

For example, setting `s.eVar1="Internal Keyword Search"` by itself does not give any Instance metric credit to the eVar1 value of "Internal Keyword Search". An instance IS recorded at that point. However, unless a product is bound to that "Internal Keyword Search" value at the same time `eVar1` is set, the instance is attributed to the Unspecified bucket. In other words, the `eVar1` value of "Internal Keyword Search" can get an Instance. But this happens only when a product that is bound to the value of "Internal Keyword Search" appears in the products variable in the same image request.  

In summary, without additional configuration, the out-of-the-box Instances metric for a merchandising eVar is less than useful. Luckily, Adobe released [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html). It lets you apply multiple attribution models for any customized metric that Adobe Analytics collects. Metrics that apply these attribution models do not use the values contained in the post_evar columns or the values that are bound to any one particular product. Rather, these metrics use only the values that are passed over via the image requests themselves (or values that are captured via Adobe Analytics processing rules). You can use the features in Attribution IQ to get an accurately attributed instances metric for all merchandising eVars that use Conversion Variable Syntax.

![Attribution select](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/assets/attribution-select.png)

When adding an instance metric for a merchandising eVar to a report, the proper Attribution IQ model would be the "Last Touch" model. The Lookback Window setting for the model does not matter in this case. The reason is that a "forced" Last Touch attribution model always gives instance credit to each individual value that is passed in via a request. This is regardless of whether the eVar's actual attribution/binding settings are set equal to "Most Recent (Last)" to "Original Value (First)".
