---
description: null
keywords: Analytics Implementation
seo-description: null
seo-title: Overview of merchandising variables
solution: Analytics
title: Overview of merchandising variables
topic: Developer and implementation
uuid: 3c01b52e-a7ff-40b2-832a-e2bd88f9aa90
index: y
internal: n
snippet: y
---

# Overview of merchandising variables

When measuring the success of external campaigns or external search terms, you typically want a single value to receive credit for any success events that occur. For example, if a customer clicks a link in an email campaign to visit your website, all purchases made as a result should be credited to that campaign.

But what about events that are driven by internal search or by category browsing when a customer is looking for multiple items? For example, a customer searches your site for "goggles" and then adds a pair to the cart: 

![](assets/merch-example-goggles.png)

Before checkout, the customer searches for "winter coat", and then adds a down jacket to the to the cart: 

![](assets/merch-example-coat.png)

When this purchase is completed, assuming the allocation wasn't changed from Most Recent, you'll have an internal search for "winter coat" credited with the purchase of a pair of goggles. Good for "winter coat", but bad for marketing decisions: 

|  Internal Search Term  | Revenue  |
|---|---|
|  winter coat  | $157  |

**How merchandising variables solve this problem**

Cross-category merchandising variables, or "merchandising evars", let you assign the current value of an eVar to a product at the time a success event takes place. This value remains tied to that product, even if one or more new values are later set for that particular eVar.

If merchandising is enabled for the eVar in the previous example, the search term "goggles" is tied to the Fernie Snow Goggles, and the search term "winter coat" is tied to the El Gordo Down Jacket. Merchandising variables allocate revenue at the product level, so each term receives credit for the amount of revenue for the product to which the term was associated: 

|  Internal Search Term  | Revenue  |
|---|---|
|  winter coat  | $119  |
|  goggles  | $38  |

