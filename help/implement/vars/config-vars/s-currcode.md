---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---

# s.currencyCode

The  variable determines the conversion rate to be applied to revenue.

All monetary amounts are stored in a currency of your choice. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

|Max Size|Debugger Parameter|Reports Populated|Default Value|
|--- |--- |--- |--- |
|N/A|cc|Conversion > Purchases > Revenue All Conversion reports showing Revenue or monetary values|"USD"|

If your site allows visitors to purchase in multiple currencies, you should use the *`currencyCode`* variable to make sure revenue is stored in the appropriate currency. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. As soon as data collection receives the data, it uses the current conversion rate to convert the 40 Euros to its USD equivalent.

Populating the *`currencyCode`* variable on the HTML page instead of in the JavaScript file is recommend if you sell in multiple currencies. If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. You then convert all revenue before sending it into [!DNL Analytics].

Currency conversion applies to both revenue and any currency events. These are events that are used to sum values similar to revenue, such as tax and shipping. The revenue and currency events are specified in the products string. For more information on products, see [events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html).

## Syntax and Possible Values

```js
s.currencyCode="currency_code"
```

## Examples

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## Configuration Settings

Adobe [!DNL Customer Care] can change the default currency setting for your report suite. When you change the base currency for a report suite, the existing revenue in the system is not converted. All new revenue values will be converted accordingly.

## Pitfalls, Questions, and Tips

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly.
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* Currency events should not be used for non-currency purposes. If you need to count arbitrary or dynamic values that are not currency, use the [!UICONTROL numeric] event type.
* When the *`currencyCode`* variable is empty, no conversion is applied.

For more information, see [Currency Codes](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html).
