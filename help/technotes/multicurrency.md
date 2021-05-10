---
description: Describes how to define target currency codes for multi-currency support to work.
title: Multi-currency support
uuid:
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
---
# Multi-currency support

This document describes how to define target currency codes for multi-currency support.

Target currency codes are defined at three levels:

## Page level

You can set a JavaScript variable for the target currency at the page level. The site owner sets this variable with the appropriate three-letter ISO 4217 currency code (as listed at below in this document). If the [currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) variable is not set at this level, the default currency will be the same as the one specified in the report suite. If the variable at the page level conflicts with the variable specified in the report suite, the variable in the report suite will take precedence.


## Report suite level

 The **base currency** is specified when [creating report suites](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html). This is the default setting for currency and takes precedence over currency codes set at the page level. Thus, if a report suite has orders that accept U.S. Dollars, Euro, and British Pounds and the report suite has a default currency code set to "US Dollars", then the reporting back-end database translates all transactions to US Dollars.

 Marketing reports use the exchange rate at the time the image request occurs to translate page-level currency values to the default report-suite currency values. Reports suites use "US Dollars" as the default currency.


## Report level
 
Users can set the default reported currency for user-login session. This can be accessed through the **Display Options**  link in any Conversion Report. Marketing reports use the exchange rate at the time the report is run to translate report-suite currency values into report-specified currency values.

## Supported currency codes (ISO 4217)

Analytics currently supports the following currency formats for conversion transactions:


'AFA' Afghanistan Afghanis (AFA)

'AFN' Afghanistan Afghanis (AFN)

'ALL' Albania Leke (ALL)

'DZD' Algeria Dinars (DZD)

'AOA' Angola Kwanza (AOA)

'ARS' Argentina Pesos (ARS)

'AMD' Armenia Drams (AMD)

'AWG' Aruba Guilders (AWG)

'AUD' Australia Dollars (AUD)

'AZM' Azerbaijan Manats (AZM)

'AZN' Azerbaijan New Manats (AZN)

'BSD' Bahamas Dollars (BSD)

'BHD' Bahrain Dinars (BHD)

'BDT' Bangladesh Taka (BDT)

'BBD' Barbados Dollars (BBD)

'BYR' Belarus Rubles (BYR)

'BZD' Belize Dollars (BZD)

'BMD' Bermuda Dollars (BMD) 

'BTN' Bhutan Ngultrum (BTN)

'BOB' Bolivia Bolivianos (BOB)

'BAM' Bosnia and Herzegovina Convertible Marka (BAM)

'BWP' Botswana Pulas (BWP)

'BRL' Brazil Reais (BRL)

'BND' Brunei Dollars (BND)

'BGN' Bulgaria Leva (BGN)

'BIF' Burundi Francs (BIF)

'KHR' Cambodia Riels (KHR)

'CAD' Canada Dollars (CAD)

'CVE' Cape Verde Escudos (CVE)

'KYD' Cayman Islands Dollars (KYD)

'CLP' Chile Pesos (CLP)

'CNY' China Yuan Renminbi (CNY)

'COP' Colombia Pesos (COP)

'XOF' Communauté Financière Africaine Francs BCEAO (XOF)

'XAF' Communauté Financière Africaine Francs BEAC (XAF)

'KMF' Comoros Francs (KMF)

'XPF' Comptoirs Français du Pacifique Francs (XPF)

'CDF' Congo/Kinshasa Francs (CDF)

'CRC' Costa Rica Colones (CRC)

'HRK' Croatia Kuna (HRK)

'CUC' Cuba Convertible Pesos (CUC)

'CUP' Cuba Pesos (CUP)

'CYP' Cyprus Pounds (CYP)

'CZK' Czech Republic Koruny (CZK)

'DKK' Denmark Kroner (DKK)

'DJF' Djibouti Francs (DJF)

'DOP' Dominican Republic Pesos (DOP)

'XCD' East Caribbean Dollars (XCD)

'EGP' Egypt Pounds (EGP)

'SVC' El Salvador Colones (SVC)

'ERN' Eritrea Nakfa (ERN)

'XBT' ERR (XBT)

'EEK' Estonia Krooni (EEK)

'ETB' Ethiopia Birr (ETB)

'EUR' Euro (EUR)

'FKP' Falkland Islands Pounds (FKP)

'FJD' Fiji Dollars (FJD)

'GMD' Gambia Dalasi (GMD)

'GEL' Georgia Lari (GEL)

'GHC' Ghana Cedis (GHC)

'GHS' Ghana Cedis (GHS)

'GIP' Gibraltar Pounds (GIP)

'XAU' Gold Ounces (XAU)

'GTQ' Guatemala Quetzales (GTQ)

'GGP' Guernsey Pounds (GGP)

'GNF' Guinea Francs (GNF)

'GYD' Guyana Dollars (GYD)

'HTG' Haiti Gourdes (HTG)

'HNL' Honduras Lempiras (HNL)

'HKD' Hong Kong Dollars (HKD)

'HUF' Hungary Forint (HUF)

'ISK' Iceland Kronur (ISK)

'INR' India Rupees (INR)

'IDR' Indonesia Rupiahs (IDR)

'XDR' International Monetary Fund Special Drawing Rights (XDR)

'IRR' Iran Rials (IRR)

'IQD' Iraq Dinars (IQD)

'IMP' Isle of Man Pounds (IMP)

'ILS' Israel New Shekels (ILS)

'JMD' Jamaica Dollars (JMD)

'JPY' Japan Yen (JPY)

'JEP' Jersey Pounds (JEP)

'JOD' Jordan Dinars (JOD)

'KZT' Kazakhstan Tenge (KZT)

'KES' Kenya Shillings (KES)

'KWD' Kuwait Dinars (KWD)

'KGS' Kyrgyzstan Soms (KGS)

'LAK' Laos Kips (LAK)

'LVL' Latvia Lati (LVL)

'LBP' Lebanon Pounds (LBP)

'LSL' Lesotho Maloti (LSL)

'LRD' Liberia Dollars (LRD)

'LYD' Libya Dinars (LYD)

'LTL' Lithuania Litai (LTL)

'MOP' Macau Patacas (MOP)

'MKD' Macedonia Denars (MKD)

'MGA' Madagascar Ariary (MGA)

'MWK' Malawi Kwachas (MWK)

'MYR' Malaysia Ringgits (MYR)

'MVR' Maldives Rufiyaa (MVR)

'MTL' Malta Liri (MTL)

'MRO' Mauritania Ouguiyas (MRO)

'MUR' Mauritius Rupees (MUR)

'MXN' Mexico Pesos (MXN)

'MDL' Moldova Lei (MDL)

'MNT' Mongolia Tugriks (MNT)

'MAD' Morocco Dirhams (MAD)

'MZN' Mozambique Meticais (MZN)

'MZM' Mozambique Meticais (MZM)

'MMK' Myanmar Kyats (MMK)

'NAD' Namibia Dollars (NAD)

'NPR' Nepal Rupees (NPR)

'ANG' Netherlands Antilles Guilders (ANG)

'NZD' New Zealand Dollars (NZD)

'NIO' Nicaragua Cordobas (NIO)

'NGN' Nigeria Nairas (NGN)

'KPW' North Korea Won (KPW)

'NOK' Norway Kroner (NOK)

'OMR' Oman Rials (OMR)

'PKR' Pakistan Rupees (PKR)

'XPD' Palladium Ounces (XPD)

'PAB' Panama Balboas (PAB)

'PGK' Papua New Guinea Kina (PGK)

'PYG' Paraguay Guarani (PYG)

'PEN' Peru Nuevos Soles (PEN)

'PHP' Philippines Pesos (PHP)

'XPT' Platinum Ounces (XPT)

'PLN' Poland Zlotych (PLN)

'QAR' Qatar Riyals (QAR)

'ROL' Romania Lei (ROL)

'RON' Romania New Lei (RON)

'RUB' Russia Rubles (RUB)

'RUR' Russia Rubles (RUR)

'RWF' Rwanda Francs (RWF)

'SHP' Saint Helena Pounds (SHP)

'WST' Samoa Tala (WST)

'STD' São Tome and Principe Dobras (STD)

'SAR' Saudi Arabia Riyals (SAR)

'SPL' Seborga Luigini (SPL)

'RSD' Serbia Dinars (RSD)

'CSD' Serbia Dinars (CSD)

'SCR' Seychelles Rupees (SCR)

'SLL' Sierra Leone Leones (SLL)

'XAG' Silver Ounces (XAG)

'SGD' Singapore Dollars (SGD)

'SKK' Slovakia Koruny (SKK)

'SIT' Slovenia Tolars (SIT)

'SBD' Solomon Islands Dollars (SBD)

'SOS' Somalia Shillings (SOS)

'ZAR' South Africa Rand (ZAR)

'KRW' South Korea Won (KRW)

'LKR' Sri Lanka Rupees (LKR)

'SDD' Sudan Dinars (SDD)

'SDG' Sudan Pounds (SDG)

'SRD' Suriname Dollars (SRD)

'SRG' Suriname Guilders (SRG)

'SZL' Swaziland Emalangeni (SZL)

'SEK' Sweden Kronor (SEK)

'CHF' Switzerland Francs (CHF)

'SYP' Syria Pounds (SYP)

'TWD' Taiwan New Dollars (TWD)

'TJS' Tajikistan Somoni (TJS)

'TZS' Tanzania Shillings (TZS)

'THB' Thailand Baht (THB)

'TOP' Tonga Pa'anga (TOP)

'TTD' Trinidad and Tobago Dollars (TTD)

'TND' Tunisia Dinars (TND)

'TRY' Turkey Lira (TRY)

'TRL' Turkey Liras (TRL)

'TMM' Turkmenistan Manats (TMM)

'TMT' Turkmenistan New Manats (TMT)

'TVD' Tuvalu Dollars (TVD)

'UGX' Uganda Shillings (UGX)

'UAH' Ukraine Hryvnia (UAH)

'AED' United Arab Emirates Dirhams (AED)

'GBP' United Kingdom Pounds (GBP)

'USD' selected United States Dollars (USD)

'UYU' Uruguay Pesos (UYU)

'UZS' Uzbekistan Sums (UZS)

'VUV' Vanuatu Vatu (VUV)

'VEB' Venezuela Bolivares (VEB)

'VEF' Venezuela Bolivares Fuertes (VEF)

'VND' Vietnam Dong (VND)

'YER' Yemen Rials (YER)

'ZMK' Zambia Kwacha (ZMK)

'ZMW' Zambia Kwacha (ZMW)

'ZWD' Zimbabwe Dollars (ZWD) 


## AppMeasurement.js Example

The `currencyCode` variable can be defined globally in the AppMeasurement.js file. Defining the currencyCode variable in this file ensures that all currency transactions use a uniform currency code. The example below specifies Euros as the `currencyCode` variable in the `CONFIG SECTION` of the AppMeasurement.js file. All purchase events will be interpreted by reporting as "Euro" transactions.

```

/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

## Additional Implementation Notes

* Keep in mind that while currency codes can change between pages, all conversion line items defined on a given page request must use the same currency (for example, you can't have Euro, British Pounds, and US Dollars defined on the same page view). If you do not want to do any currency conversion, you should leave the currencyCode value blank. This causes the values sent to be passed directly through to reports with no conversion.

* Setting an invalid currencyCode (any value not on the Supported currency codes list) causes the entire hit to be excluded and data to not be collected for that transaction. Before setting `currencyCode` in production, use a test report suite to verify that data is collected and the currency conversion is correct.

* Currencies that do not use a period (.) as the separator must be modified to use the period instead of the typical separator. For example, Swedish Krona, which uses a comma (,), must be modified to use a period instead of the comma. Analytics uses the comma to separate values, and the data will not be passed in correctly. The period will correctly pass the value to reports.
