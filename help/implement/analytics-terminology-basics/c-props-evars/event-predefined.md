---
description: List of predefined events.
keywords: Analytics Implementation;event
seo-description: List of predefined events.
seo-title: What is a predefined event?
solution: Analytics
title: What is a predefined event?
topic: Developer and implementation
uuid: 4d0799ba-0f97-42c3-a620-36c03f9995da
index: y
internal: n
snippet: y
---

# What is a predefined event?

List of predefined events.

|  prodView  | Success event occurs any time a visitor views a product.  |
|---|---|
|  scView  | Success event occurs any time a shopping cart is viewed.  |
|  scOpen  | Success event occurs any time a visitor opens a shopping cart for the first time.  |
|  scAdd  | Success event occurs any time a product is added to a shopping cart.  |
|  scRemove  | Success event occurs any time an item is taken out of a shopping cart.  |
|  scCheckout  | Success event occurs on the first page of a checkout.  |
|  purchase  | Success event occurs on the final page of a checkout (includes Revenue, Orders, and Units).  |

When one of the predefined events above occurs, an instance of the event is incremented. You can view the metrics related to the event in several different reports. See below for an example of the code used to configure predefined events.

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* In the first example above, *`scAdd`* is the value of the event. Any time an item is added to the shopping cart, the event is incremented. 
* In the second example, two values are captured at the same time. When multiple success events occur on the same page, each event is incremented.

