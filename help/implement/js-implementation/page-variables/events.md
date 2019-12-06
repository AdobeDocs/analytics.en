---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---


# Events

The  variable is used to record common shopping cart success events as well as custom success events.


<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
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
   <td> No Limit </td> 
   <td> events </td> 
   <td> <p>Shopping Cart Events </p> <p>Custom Events </p> </td> 
   <td> N/A </td> 
  </tr> 
 </tbody> 
</table>

An [!UICONTROL event] should be considered a milestone within a site. Success events are most commonly populated on the final confirmation page of a process, such as a registration process or newsletter sign-up. Custom events are defined by populating the events variable with the literal values defined in the Possible Values section below.

By default, success events are configured as *counter* events. Counter events count the number of times a success event is set (x+1). Events can also be configured as *numeric* events. Numeric events allow you to specify the number to increment (as might be necessary when counting dynamic or arbitrary values, such as the number of results returned by an internal search).

A final event type, *currency*, allows you to define the amount to be added (similar to numeric events), but displays as currency in reports, and is subject to currency conversions based on the s. *`currencyCode`* value and the default currency setting for your report suite. For additional information on using numeric and currency events, see [Products](/help/implement/js-implementation/page-variables/page-variables.md).

**Configuring the Variable**

The `s.events` variable is enabled by default for all implementations. The seven pre-configured conversion events are automatically enabled for all new report suites. New custom events (event1- [event100 or event1000](/help/implement/js-implementation/page-variables/page-variables.md)) can be enabled by any admin-level user using the Admin Console.

**Possible Values**

The following is a list of possible values for the events variable: 

|  Event  | Description  | Reports Populated  |
|---|---|---|
|  prodView  | Product Views  | Products  |
|  scOpen  | Open / Initialize a new shopping cart  | Carts  |
|  scAdd  | Add item(s) to the shopping cart  | Cart Additions  |
|  scRemove  | Remove item(s) from the shopping cart  | Cart Removals  |
|  scView  | View shopping cart  | Cart Views  |
|  scCheckout  | Beginning of the checkout process  | Checkouts  |
|  purchase  | Completion of a purchase (order)  | Orders  |
|  event1 - event1000 (event100 for point product)  | Custom events  | Custom Events  |

**Syntax and Examples** 

Counter events are set by placing the desired events in the `s.events` variable, in a comma-separated list (if multiple events are to be passed).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

If on H23 code or higher, counter events can have integers greater than one assigned to them.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

Implementing counter events with assigned integer values treat the event as if it fired multiple times within the image request. Counter events do not allow decimals- it is recommended to use numeric events instead if this functionality is required.
Numeric and currency events must be included in the [!UICONTROL s.events] variable, though they typically receive their numerical value (e.g., 24.99) in the [!UICONTROL s.products] variable. This allows you to tie specific numeric and currency values to individual product entries.

**Event Serialization** 

By default, an event is counted every time the event is set on your site.

See [Event Serialization](/help/implement/js-implementation/event-serialization.md) for more information.

**Syntax**

```js
s.events="event1:3167fhjkah"
```

**Examples**

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
