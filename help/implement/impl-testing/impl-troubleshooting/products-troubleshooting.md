---
description: The s.products variable may be the most syntactically complex variable used by data collection.
keywords: Analytics Implementation
seo-description: The s.products variable may be the most syntactically complex variable used by data collection.
seo-title: Common mistakes in the Products variable
solution: Analytics
subtopic: Troubleshooting
title: Common mistakes in the Products variable
topic: Developer and implementation
uuid: fbfeb3e6-a482-4e1c-9aab-aad4b0fdc5b2
index: y
internal: n
snippet: y
---

# Common mistakes in the Products variable

The s.products variable may be the most syntactically complex variable used by data collection.

 Commas, semi-colons, pipes, and equals signs all play specific roles in the variable. It has no overall maximum length, but each individual product entry cannot be longer than 100 bytes (including multi-byte characters). Mistakes in implementation of this variable are understandable, but unfortunately for developers, [!UICONTROL s.products] is often a site's most important variable because it makes possible the tracking of revenue, units, product names, and so forth.

Here are a few extremely easy-to-make mistakes that can cause issues on any implementation.

Make sure that your [!UICONTROL category], [!UICONTROL product name], and [!UICONTROL revenue] totals are devoid of commas and semi-colons. The comma is used to separate entries in the [!UICONTROL s.products] string. This happens when you have two products in the same transaction, the semi-colon is used to delimit fields within an entry. If you use a comma or semi-colon in any other way, data collection assumes that you are separating product entries. Consider the following example:

```js
s.products="widgets;large widget, 40′x40′;1;19.99,wugs;tiny wug;2;1,999.98";
```

In this implementation, the developer probably intended for data collection to read this as shown below:

Category 1: widgets

Product 1: large widget, 40′x40′

Units 1: 1

Revenue 1: 19.99

Category 2: wugs

Product 2: tiny wug

Units 2: 2

Revenue 2: 1,999.98

Note the commas in the Product 1 and Revenue 2 entries. These indicate a new product entry. Data collection would interpret the above as:

Category 1: widgets

Product 1: large widget

Category 2: 40'x40'

Product 2: 1

Units 2: 19.99

Category 3: wugs

Product 3: tiny wug

Units 3: 2

Revenue 3: 1

Category 4: 999.98

A mistake like this often results in unexpected numerical values in the [!UICONTROL Products] report, because the units field is recorded as the product name. If you see invalid product names in your [!UICONTROL Products] report, review your [!UICONTROL s.products] variable implementation for misuse of reserved characters, like the comma.

Your product and category names should not contain unsupported characters. This can be especially difficult in the [!UICONTROL s.products] string, because product names are often likely to contain characters such as ™, ©, and ®. These characters need to be stripped out of the product and category values before they are placed into [!UICONTROL s.products]. You also need to ensure that currency symbols are not included in your revenue values. Supported characters are numbers 1-127 from the ASCII table.

If you are not passing a product category in the product string, make sure to include a semi-colon (;) where the product category is normally displayed, as shown below: 

```js
s.products=";product name"
```

In this case, the semi-colon represents a placeholder for the product category. If the semi-colon is left out of the product string, then "product name" would be counted as the category, the number of units to be counted as the product name, the revenue to be counted as the units, and so on. 
