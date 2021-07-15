---
title: Merchandising eVars and Product Finding Methods
description: A deep dive into the concepts behind merchandising eVars and how they process and allocate data.
---
# Merchandising eVars and Product Finding Methods

This document explains the concepts behind merchandising eVars, which process and allocate data differently than standard eVars. It also explains how merchandising eVars relate to Product Finding Methods.

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

We can use an additional eVar to measure the performance of all product finding methods in relation to each other. In addition to the finding methods described above, the eVar will include other finding methods, such as links to product detail pages from external websites, in its comparison.

* eVar1: Product Finding Methods

You should not configure any of these variables to be standard eVars, but rather should configure them to be merchandising eVars.  Using merchandising eVars allows you to allocate any successful activity to the values captured by the eVars at a *per-product* level instead of a *per-visit/per-order* level. I will clarify the difference between per-product and per-order allocation throughout the remainder of this document.

To demonstrate how these variables are to be set, I will start off with an example in which a visitor decides that she will use the internal keyword search "sandals" to find a product on the site.  On the keyword search results page, you need to capture data in at least two eVars: 

* `eVar2` will be equal to the keyword that was used in the search ("sandals") 
* `eVar1` will be equal to the product finding method used ("internal keyword search"). 

When you set these two variables equal to these specific values, you know that the visitor is using the internal keyword search term of "sandals" to find a product. 
At the same time, you know that the visitor is not using the other product finding methods to find products (e.g. the visitor is not browsing through product categories at the exact same time he/she is performing a keyword search). To ensure that proper per-product allocation takes place, these unused methods should not credit for finding a product that was found via an internal keyword search.  Hence, you need to insert logic into the code (e.g. AppMeasurement, AEP Web SDK, etc.) that will automatically set the eVars associated with these other finding methods equal to a "non-finding method" value.

For example, when a user searches for products using the keyword "sandals", the Analytics code’s logic should set the variables equal to the following on the internal keyword search results page:

* eVar2="sandals": the keyword "sandals" was used in the internal keyword search
* eVar1="internal keyword search": the "internal keyword search" finding method was used
* eVar3="non-internal campaign": an internal campaign was not used to access the search results page
* eVar4="non-browse": a browse category was not accessed on the search results page
* eVar5="non-cross-sell": a cross-sell link was not clicked on the search results page

