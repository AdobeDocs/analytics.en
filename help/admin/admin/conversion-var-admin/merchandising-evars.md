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

