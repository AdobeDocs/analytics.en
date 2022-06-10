---
title: What is the currencyCode variable, and how do I use it?
description: For eCommerce sites, sets the currency the page deals in.
feature: Variables
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
---
# currencyCode

For sites using commerce, revenue and currency is an important part of Analytics. Many sites, especially those that span multiple countries, use different currencies. Use the `currencyCode` variable to make sure revenue attributes to the correct currency.

If `currencyCode` is not defined, monetary values defined the [`products`](../page-vars/products.md) variable and currency events are treated as if they are the same as the report suite's currency. See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide to see the report suite's currency.

If `currencyCode` is defined and matches the report suite's currency, no currency conversion is applied.

If `currencyCode` is defined and is different than the report suite's currency, Adobe applies a currency conversion based on the current day's exchange rate. Adobe partners with [XE](https://xe.com) to convert currency each day. All values stored in data collection servers are ultimately stored in the report suite's currency.

>[!WARNING]
>
>If `currencyCode` contains an invalid value, the entire hit is discarded causing data loss. Make sure that this variable is correctly defined if you use it in your implementation.

This variable does not persist between hits. Make sure that this variable is defined on every page that involves revenue or currency events.

## Currency code using the Web SDK

Currency code is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM field `commerce.order.currencyCode`.

## Currency Code using the Adobe Analytics extension

Currency Code is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
1. Expand the [!UICONTROL General] accordion, which reveals the [!UICONTROL Currency Code] field.

You can use either a preset currency code or a custom currency code. If using a custom currency code, make sure that the code is valid.

## Currency Code in Adobe Experience Platform Mobile SDK

Currency Code is passed to the Adobe Experience Platform Mobile SDKs through context data variables in the Adobe Analytics extension.

1. Set the currency code in a context data variable during either `trackState` or `trackAction`.
1. Create a processing rule in the Adobe Analytics admin console for the report suite. Set the rule to overwrite the Currency Code variable.
1. Pass the currency code to the `products` variable in your call to `trackState` or `trackAction`.

You can use either a preset currency code or a custom currency code. If using a custom currency code, make sure that the code is valid.

## s.currencyCode in AppMeasurement and the Analytics extension custom code editor

The `s.currencyCode` variable is a string, containing a 3-letter uppercase code representing the currency on the page.

```js
s.currencyCode = "USD";
```

The following currency codes are valid:

| Currency Code | Currency Description|
| --- | --- |
| `AED` | United Arab Emirates Dirhams |
| `AFA` | Afghanistan Afghanis |
| `ALL` | Albania Leke |
| `AMD` | Armenia Drams |
| `ANG` | Netherlands Atilles Guilders |
| `AOA` | Angola Kwanza |
| `ARS` | Argentina Pesos |
| `AUD` | Australia Dollars |
| `AWG` | Aruba Guilders |
| `AZM` | Azerbaijan Manats |
| `BAM` | Bosnia and Herzegovina Convertible Marka |
| `BBD` | Barbados Dollars |
| `BDT` | Bangladesh Taka |
| `BGN` | Bulgaria Leva |
| `BHD` | Bahrain Dinars |
| `BIF` | Burundi Francs |
| `BMD` | Bermuda Dollars |
| `BND` | Brunei Dollars |
| `BOB` | Bolivia Bolivianos |
| `BRL` | Brazil Reais |
| `BSD` | Bahamas Dollars |
| `BTN` | Bhutan Ngultrum |
| `BWP` | Botswana Pulas |
| `BYR` | Belarus Rubles |
| `BZD` | Belize Dollars |
| `CAD` | Canada Dollars |
| `CDF` | Congo/Kinshasa Francs |
| `CHF` | Switzerland Francs |
| `CLP` | Chile Pesos |
| `CNY` | China Yuan Renminbi |
| `COP` | Colombia Pesos |
| `CRC` | Costa Rica Colones |
| `CSD` | Serbia Dinars |
| `CUP` | Cuba Pesos |
| `CVE` | Cape Verde Escudos |
| `CYP` | Cyprus Pounds |
| `CZK` | Czech Republic Koruny |
| `DJF` | Djibouti Francs |
| `DKK` | Denmark Kroner |
| `DOP` | Dominican Republic Pesos |
| `DZD` | Algeria Dinars |
| `EEK` | Estonia Krooni |
| `EGP` | Egypt Pounds |
| `ERN` | Eritrea Nakfa |
| `ETB` | Ethiopia Birr |
| `EUR` | Euro |
| `FJD` | Fiji Dollars |
| `FKP` | Falkland Islands Pounds |
| `GBP` | United Kingdom Pounds |
| `GEL` | Georgia Lari |
| `GGP` | Guernsey Pounds |
| `GHC` | Ghana Cedis |
| `GIP` | Gibraltar Pounds |
| `GMD` | Gambia Dalasi |
| `GNF` | Guinea Francs |
| `GTQ` | Guatemala Quetzales |
| `GYD` | Guyana Dollars |
| `HKD` | Hong Kong Dollars |
| `HNL` | Honduras Lempiras |
| `HRK` | Croatia Kuna |
| `HTG` | Haiti Gourdes |
| `HUF` | Hungary Forint |
| `IDR` | Indonesia Rupiahs |
| `ILS` | Israel New Shekels |
| `IMP` | Isle of Man Pounds |
| `INR` | India Rupees |
| `IQD` | Iraq Dinars |
| `IRR` | Iran Rials |
| `ISK` | Iceland Kronur |
| `JEP` | Jersey Pounds |
| `JMD` | Jamaica Dollars |
| `JOD` | Jordan Dinars |
| `JPY` | Japan Yen |
| `KES` | Kenya Shillings |
| `KGS` | Kyrgyzstan Soms |
| `KHR` | Cambodia Riels |
| `KMF` | Comoros Francs |
| `KPW` | North Korea Won |
| `KRW` | South Korea Won |
| `KWD` | Kuwait Dinars |
| `KYD` | Cayman Islands Dollars |
| `KZT` | Kazakhstan Tenge |
| `LAK` | Laos Kips |
| `LBP` | Lebanon Pounds |
| `LKR` | Sri Lanka Rupees |
| `LRD` | Liberia Dollars |
| `LSL` | Lesotho Maloti |
| `LTL` | Lithuania Litai |
| `LVL` | Latvia Lati |
| `LYD` | Libya Dinars |
| `MAD` | Morocco Dirhams |
| `MDL` | Moldova Lei |
| `MGA` | Madagascar Ariary |
| `MKD` | Macedonia Denars |
| `MMK` | Myanmar Kyats |
| `MNT` | Mongolia Tugriks |
| `MOP` | Macau Patacas |
| `MRO` | Mauritania Ouguiyas |
| `MTL` | Malta Liri |
| `MUR` | Mauritius Rupees |
| `MVR` | Maldives Rufiyaa |
| `MWK` | Malawi Kwachas |
| `MXN` | Mexico Pesos |
| `MYR` | Malaysia Ringgits |
| `MZM` | Mozambique Meticais |
| `NAD` | Namibia Dollars |
| `NGN` | Nigeria Nairas |
| `NIO` | Nicaragua Gold Cordobas |
| `NOK` | Norway Kroner |
| `NPR` | Nepal Rupees |
| `NZD` | New Zealand Dollars |
| `OMR` | Oman Rials |
| `PAB` | Panama Balboas |
| `PEN` | Peru Nuevos Soles |
| `PGK` | Papua New Guinea Kina |
| `PHP` | Philippines Pesos |
| `PKR` | Pakistan Rupees |
| `PLN` | Poland Zlotych |
| `PYG` | Paraguay Guarani |
| `QAR` | Qatar Riyals |
| `ROL` | Romania Lei |
| `RUR` | Russia Rubles |
| `RWF` | Rwanda Francs |
| `SAR` | Saudi Arabia Riyals |
| `SBD` | Solomon Islands Dollars |
| `SCR` | Seychelles Rupees |
| `SDD` | Sudan Dinars |
| `SEK` | Sweden Kronor |
| `SGD` | Singapore Dollars |
| `SHP` | Saint Helena Pounds |
| `SIT` | Slovenia Tolars |
| `SKK` | Slovakia Koruny |
| `SLL` | Sierra Leone Leones |
| `SOS` | Somalia Shillings |
| `SPL` | Seborga Luigini |
| `SRD` | Suriname Dollars |
| `SRG` | Suriname Guilders |
| `STD` | Sao Tome and Principe Dobras |
| `SVC` | El Salvador Colones |
| `SYP` | Syria Pounds |
| `SZL` | Swaziland Emalangeni |
| `THB` | Thailand Baht |
| `TJS` | Tajikistan Somoni |
| `TMM` | Turkmenistan Manats |
| `TND` | Tunisia Dinars |
| `TOP` | Tonga Pa'anga |
| `TRL` | Turkey Liras |
| `TTD` | Trinidad and Tobago Dollars |
| `TVD` | Tuvalu Dollars |
| `TWD` | Taiwan New Dollars |
| `TZS` | Tanzania Shillings |
| `UAH` | Ukraine Hryvnia |
| `UGX` | Uganda Shillings |
| `USD` | United States Dollar |
| `UYU` | Uruguay Pesos |
| `UZS` | Uzbekistan Sums |
| `VEB` | Venezuela Bolivares |
| `VND` | Vietnam Dong |
| `VUV` | Vanuatu Vatu |
| `WST` | Samoa Tala |
| `XAF` | Communauté Financière Africaine Francs B |
| `XAG` | Silver Ounces |
| `XAU` | Gold Ounces |
| `XCD` | East Caribbean Dollars |
| `XDR` | International Monetary Fund Special Draw |
| `XOF` | Communauté Financière Africaine Francs B |
| `XPD` | Palladium Ounces |
| `XPF` | Comptoirs Français du Pacifique Francs |
| `XPT` | Platinum Ounces |
| `YER` | Yemen Rials |
| `ZAR` | South Africa Rand |
| `ZMK` | Zambia Kwacha |
| `ZWD` | Zimbabwe Dollar |
