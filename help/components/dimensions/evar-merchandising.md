---
title: eVar (Merchandising dimension)
description: Custom variables that tie to the products dimension.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: 'https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# eVar (Merchandising)

>[!BEGINSHADEBOX]

*This help page describes how merchandising eVars work as a [dimension](overview.md). For information on how to implement merchandising eVars, see [eVar (merchandising variable)](/help/implement/vars/page-vars/evar-merchandising.md) in the Implementation user guide.*

>[!ENDSHADEBOX]

A merchandising eVar works like a standard eVar, except that each product has its own copy of it. Persistence, allocation, and expiration all work the same way, but separately for each product. A standard eVar holds one persisted value per visitor that receives credit for every success event. A merchandising eVar holds one persisted value per product, and that value receives credit for that product's success events:

* Product A &rarr; `eVar1` = `value A`
* Product B &rarr; `eVar1` = `value B`

Each product's value can be set or changed only on hits that include that product. Once set, the value persists until it expires and receives credit only for that product's success events. Changing product A's value has no effect on product B.

Merchandising eVars work only with the [`products`](/help/implement/vars/page-vars/products.md) variable. A merchandising eVar value that is not bound to a product receives no credit. Success events on hits without products are attributed to `"None"` for every merchandising eVar.

>[!TIP]
>
>To bind persisted values to a dimension other than products, consider using [[!UICONTROL Binding dimensions]](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence#binding-dimension) in Customer Journey Analytics.

## Why use merchandising eVars

Keeping a separate value for each product matters when a single value shouldn't receive credit for everything a visitor buys. A standard eVar works well for external campaigns or external search terms, where one value should receive credit for any success events that occur. For example, if a customer clicks a link in an email campaign to visit your website, all purchases made as a result should be credited to that campaign.

Internal search and category browsing are different, because a visitor often uses them to find several products, each in a different way. For example, a customer searches your site for `"goggles"`, then adds a pair to their cart:

![Goggles example](assets/merch-example-goggles.png)

Before checkout, the customer searches for `"winter coat"`, then adds a down jacket to their cart:

![Coat example](assets/merch-example-coat.png)

When the visitor completes this purchase, the internal search term `"winter coat"` receives credit for the entire order, including the goggles, because it's the eVar's most recent value (the default allocation of [!UICONTROL Most Recent (Last)]). The search term `"goggles"` receives no credit, even though it led to part of the purchase:

| Internal Search Term | Revenue |
| --- | --- |
| winter coat | $157 |

## How merchandising eVars solve this problem

If merchandising is enabled for the eVar in the previous example, the search term `"goggles"` is bound to the snow goggles, and the search term `"winter coat"` is bound to the down jacket. Merchandising eVars allocate revenue at the product level, so each term receives credit for the amount of revenue for the product to which the term is bound:

| Internal Search Term | Revenue |
| --- | --- |
| winter coat | $119 |
| goggles | $38 |

## How binding and allocation work

Merchandising eVars rely on three concepts:

* **Binding**: An association between a product and an eVar value. Each product keeps its own binding for each merchandising eVar. Like a standard eVar value, a binding persists on later hits until it expires. For example, a value bound to a product on a product page still receives credit when that product is purchased on a later page, without setting the value again. How a value reaches the product depends on the eVar's syntax, described below.
* **Allocation**: The [!UICONTROL Allocation] setting determines what happens when a new value tries to bind to a product that is **already bound**. Allocation is evaluated separately for each product, so merchandising eVar values bound to different products never compete with each other.
  * **[!UICONTROL Original Value (First)]**: The existing binding is kept. The new value is ignored for that product until the binding expires.
  * **[!UICONTROL Most Recent (Last)]**: The product rebinds to the new value.
* **Expiration**: The [!UICONTROL Expire After] setting determines when bindings end. Each product's binding has its own expiration, counted from when that product was bound. For example, with a [!UICONTROL Week] expiration, if product A is bound on Monday and product B is bound on Wednesday, product A's binding expires the following Monday and product B's binding expires the following Wednesday. When a binding expires, the product no longer has a value for that eVar, the same way a standard eVar has no value after it expires. Success events for that product are attributed to `"None"` until the product is bound again.

Each merchandising eVar uses one of two syntaxes, set in the [!UICONTROL Merchandising] setting in [report suite settings](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md). The syntax determines how a value reaches a product:

* **[Product syntax](#product-syntax)**: The value is set directly on each product in the `products` variable, and binds to that product on that hit.
* **[Conversion variable syntax](#conversion-variable-syntax)**: The value is set in the eVar itself and persists like a standard eVar value. It binds to the products on the same or a later hit that contains a binding event.

Both syntaxes use the same binding, allocation, and expiration behavior described above. They differ in the following ways:

| | Product syntax | Conversion variable syntax |
| --- | --- | --- |
| Where the value is set | On each product, in the [`products`](/help/implement/vars/page-vars/products.md) variable | In the [`eVar`](/help/implement/vars/page-vars/evar-merchandising.md) itself, the same way as a standard eVar |
| When binding occurs | On any hit where the value is set on the product | On hits that contain both products and a configured binding event |
| Values per hit | Each product can have a different value | Every product in the binding hit receives the same value |
| Implementation effort | Higher | Lower |

## Product syntax

With product syntax, the eVar value is set on each product in the `products` variable. In the `products` string, the value after the last semicolon of a product is its merchandising eVar. See [Implement using product syntax](/help/implement/vars/page-vars/evar-merchandising.md#implement-using-product-syntax) for the full syntax.

The value binds directly to that product on that hit. Binding events are not used. Later hits that include the product, such as a cart add or purchase, do not need to repeat the value. Because each product carries its own value, product syntax is the only option when products in the **same hit** need **different** values.

+++Example: the same product receives two values

| Hit | `products` | `events` |
| --- | --- | --- |
| 1 | `;12345;;;;eVar1=internal keyword search` | |
| 2 | `;12345;;;;eVar1=internal campaign` | |
| 3 | `;12345;1;50` | `purchase` |

* **[!UICONTROL Original Value (First)]**: Hit 2 is ignored for product `12345`. The purchase is credited to `internal keyword search`.
* **[!UICONTROL Most Recent (Last)]**: Hit 2 rebinds product `12345`. The purchase is credited to `internal campaign`.

+++

+++Example: two products receive different values

| Hit | `products` | `events` |
| --- | --- | --- |
| 1 | `;productA;;;;eVar1=value A` | |
| 2 | `;productB;;;;eVar1=value B` | |
| 3 | `;productA;1;50,;productB;1;30` | `purchase` |

Each product keeps its own binding, so the allocation setting has no effect in this example. `value A` receives credit for product A's revenue, and `value B` receives credit for product B's revenue. Both values receive one order, because the order contains a product bound to each value.

+++

+++Example: products with the same ID and different values

A visitor buys a medium blue t-shirt and a large red t-shirt, both with the parent product ID `tshirt123`, and `eVar10` captures child SKUs:

```js
s.events = "purchase";
s.products = ";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

Each child SKU receives credit for its own instance of `tshirt123`.

+++

The tradeoff is that product syntax requires the complete value string on each product whenever binding should occur. For product finding methods, which typically use several eVars at once, the string looks like this:

```js
s.products = ";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

A finding method should receive credit only after the visitor interacts with a product, so this string is typically set on the product detail page or on a cart add, not on the search results page. To do so, developers must:

* Carry the finding method details from the finding method page to the product detail page, or have them available when a cart add fires from a results page.
* Assemble the full `products` string without syntax errors.

Conversion variable syntax avoids both requirements.

## Conversion variable syntax

With conversion variable syntax, the value is set in the eVar itself:

```js
s.eVar1 = "internal keyword search";
```

The eVar acts as a *staging area*. A value set in the eVar is held there until a binding event binds it to the products on a hit. Binding occurs in two stages:

1. **Staging**: When the eVar is set, its value persists on subsequent hits until it expires. This persisted value is the `post_evar` column in [data feeds](/help/export/analytics-data-feed/data-feed-overview.md). For merchandising eVars that use conversion variable syntax, the staged value **always reflects the most recent value sent**, regardless of the [!UICONTROL Allocation] setting. Each new value replaces the previously staged value.
1. **Binding**: When a hit contains both products and a configured [!UICONTROL Merchandising Binding Event], the staged value binds to every product on that hit. If a product is already bound, [!UICONTROL Allocation] determines whether the new value replaces the existing binding. Products that are already bound keep their value with [!UICONTROL Original Value (First)], or rebind with [!UICONTROL Most Recent (Last)].

If the eVar, the `products` variable, and a binding event are all set on the same hit, staging and binding happen simultaneously. The new value binds immediately to the products on that hit.

Setting the eVar alongside a product without a binding event does not bind the value to that product. A staged value receives no credit until it is bound to a product.

### What binding events do

A binding event is the trigger that tells Adobe to bind the staged value to the products on the hit.

* Binding events can be standard or custom success events, the tracking code ([!UICONTROL Campaign Event]), or eVars. Props have no effect on binding.
* You can configure multiple binding events, such as [!UICONTROL Product View Event], [!UICONTROL Cart Add Event], and [!UICONTROL Purchase Event]. If any of these events are on a hit with products, the staged value binds to every product on that hit.
* By default ([!UICONTROL All]), binding occurs whenever any other event or eVar is on the same hit as a product. [!UICONTROL All] is used if no binding event is explicitly selected. With [!UICONTROL All], setting the eVar on a hit that includes products always triggers binding on that hit. A value staged on an earlier hit binds on the next hit that includes products and any other event or eVar.

+++Example: binding with a binding event

Consider the following hits:

```js
// Hit 1
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";

// Hit 2
s.products = ";sandal123";
s.events = "prodView";
```

If `prodView` is a binding event for both eVars, hit 2 binds `internal keyword search` (`eVar1`) and `sandals` (`eVar2`) to `sandal123`. If an eVar does not list `prodView` as a binding event, no binding occurs for that eVar.

+++

+++Example: allocation is evaluated per product

| Hit | `eVar1` | `products` | `events` |
| --- | --- | --- | --- |
| 1 | `value A` | | |
| 2 | | `;productA,;productB` | Binding event |
| 3 | `value B` | | |
| 4 | | `;productA` | Binding event |
| 5 | | `;productA;1;50,;productB;1;30` | `purchase` |

After hit 3, the staged value (`post_evar1`) is `value B` with either allocation setting.

* **[!UICONTROL Original Value (First)]**: Hit 4 is ignored for product A, because product A is already bound. Both products stay bound to `value A`, which receives all purchase credit.
* **[!UICONTROL Most Recent (Last)]**: Hit 4 rebinds product A to `value B`. Product B is not in hit 4, so it stays bound to `value A`. Product A's purchase credit goes to `value B`, and product B's purchase credit goes to `value A`.

With only a single binding attempt, such as hits 1, 2, and 5 alone, both settings produce the same result. Allocation matters only when a product that is already bound receives another binding attempt.

+++

## Best practice: product finding methods

Most retail sites benefit from tracking the following product finding methods, each as a merchandising eVar:

* Internal search keywords (for example, `eVar2`)
* Internal campaign tracking codes (for example, `eVar3`)
* Merchandising or browse categories (for example, `eVar4`)
* Cross-sell links (for example, `eVar5`)
* An overall product finding method eVar that compares all methods, including methods such as external links to product pages (for example, `eVar1`)

When a visitor uses one method, set the other finding method eVars to a "non-" value. Otherwise, an unused method's earlier value could receive credit for a product found through another method. For example, on the results page for an internal search for "sandals":

```js
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";
s.eVar3 = "non-internal campaign";
s.eVar4 = "non-browse";
s.eVar5 = "non-cross-sell";
```

With conversion variable syntax, developers can set only simple values, such as a search term in a prop, and logic in your implementation can fill in the merchandising eVars. Nothing needs to be passed between pages or built into the `products` string. The `products` variable is still required on the hits where binding occurs.

Adobe recommends the following settings for product finding method eVars:

| Setting | Value |
| --- | --- |
| [!UICONTROL Allocation] | [!UICONTROL Original Value (First)] |
| [!UICONTROL Expire After] | How long products stay in the cart before automatic removal, such as 14 or 30 days using [!UICONTROL Custom]. If the cart has no limit, use [!UICONTROL Purchase]. |
| [!UICONTROL Type] | [!UICONTROL Text String] |
| [!UICONTROL Enable Merchandising] | [!UICONTROL Enabled] |
| [!UICONTROL Merchandising] | [!UICONTROL Conversion Variable Syntax] |
| [!UICONTROL Merchandising Binding Event] | [!UICONTROL Product View Event], [!UICONTROL Cart Add Event], and [!UICONTROL Purchase Event] |

See [Conversion variables](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) in the Admin guide for a description of each setting.

+++Why Original Value (First) instead of Most Recent (Last)

Visitors often re-find a product that they already viewed or added to the cart. For example:

1. A visitor searches for "sandals" and adds `sandal123` to the cart from the results page. The product binds to `internal keyword search`.
1. Three days later, the visitor browses to **Women > Shoes > Sandals** (`eVar1` = `browse`), views `sandal123` again, and then purchases it.

With [!UICONTROL Most Recent (Last)], the product view in step 2 rebinds `sandal123` to `browse`, which then receives the purchase credit. The method that originally found the product receives none.

With [!UICONTROL Original Value (First)], the binding attempt in step 2 is ignored, and `internal keyword search` keeps the credit.

If the visitor never purchases the product, expiration removes the binding, so the next finding method the visitor uses can bind to the product. This is why [!UICONTROL Expire After] should match how long a product stays in the cart.

+++

## Instances on merchandising eVars

The default [Instances](../metrics/instances.md) metric is not recommended for use on merchandising variables.

* For merchandising variables using product syntax, instances are not incremented at all.
* For merchandising variables using conversion variable syntax, instances are counted each time the eVar is set. However, the instance attributes to the dimension item `"None"` unless all of the following happen on the same hit:
  * The merchandising eVar is set with a value.
  * The `products` variable is defined with a value.
  * A binding event is set.

Since most use cases for conversion variable syntax require the eVar and products variable on different hits, the default Instances metric is not realistic to use.

To count instances for each value sent with conversion variable syntax, apply the **Last Touch** [attribution model](/help/analyze/analysis-workspace/attribution/overview.md) to the Instances metric. Attribution models use the values sent on each hit, not staged values or product bindings. The lookback window does not matter, because Last Touch credits each value on the hit where it was sent, regardless of the eVar's allocation setting.

![Attribution select](assets/attribution-select.png)
