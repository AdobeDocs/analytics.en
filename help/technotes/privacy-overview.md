---
description: Overview of what data Adobe Analytics collects and other privacy considerations.
keywords: privacy
title: Privacy overview
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
---
# Privacy overview

Adobe recommends that you provide your website visitors with easy-to-find and easy-to-understand information regarding the ability to opt out of having their browsing information collected by Adobe products or services.

Visitors can learn more about how Adobe generally uses information it collects in the [Adobe Privacy Center](https://www.adobe.com/privacy.html). It is up to your organization to disclose how you use Adobe's products and services because your organization exclusively controls how to implement Adobe's services. You are responsible for the creation of your own privacy policy, for complying with your privacy policy, for complying with your service agreement with Adobe, and for complying with all applicable laws.

## Data Collection Breakdown {#section_F59D958D7AE44747846993E643CD4BF2}

Adobe Analytics collects the following data: 

|  Type of Data  | Does Adobe Analytics collect this data?  |
|---|---|
|  URLs of Web Pages within Customer Site  | Yes  |
|  Name of Web Page  | Yes  |
|  Time spent on Page  | Yes  |
|  Time of Day  | Yes  |
|  URLs of Web Pages on Unaffiliated Sites  | **No** |
|  Cookie IDs (randomly generated)  | Yes  |
|  URL of page that user was on before visiting customer page  | Yes  |
|  Search query when consumer clicks on link to customer page  | Yes  |
|  Browser Type  | Yes  |
|  Device Type  | Yes  |
|  Operating System  | Yes  |
|  ISP/Connection Speed  | Yes  |
|  Display Settings (such as screen size and resolution)  | Yes  |
|  IP Address (used to approximate location)  | Yes&#42;  |
|  Information consumers provide in forms on customer site  | Yes  |
|  Information consumers provide in forms on social sites  | **No** |
|  Whether consumer clicked on ad  | Yes  |
|  Whether consumer clicked on link, image or text on site  | Yes  |
|  Whether consumer downloaded a file, image, etc.  | Yes  |
|  Items consumer purchased  | Yes  |
|  Items left in shopping cart  | Yes  |
|  Social Network Information (including photos, user ID, age, gender, location)  | **No** |
|  Personal Information that user provides outside of our services  | Yes  |
|  Ad campaign success rates  | Yes  |
|  Product info, such as colors, prices, styles, photos  | Yes  |

&#42;Unless the Adobe customer chooses to remove the IP.

## Other Privacy Considerations {#section_60AF6AD6FBD046EEAF9F083A9726EF8A}

| Region/Country | Consideration|
|--- |--- |
| Global | Adobe strongly suggests customers refrain from passing personally identifiable information (PII) to Adobe, especially in situations where the PII is not necessary for Analytics.|
| Global | Users need to be provided with notice and choice when profiling. This is required by law in Canada, Australia, the European Union (opt-in for some countries) and many countries in Latin America and Asia-Pacific.|
| Global | If using first-party cookies, Analytics opt-out is unique to a customer; you cannot rely on an opt-out on Adobe.com.|
| Global | First-party analytics are not within scope of the Self-Regulatory Program for Online Behavioral Advertising ("AdChoices").|
| Global | Cross-device data should not be merged unless tied to an identifier provided by the customer (such as hashed user name).|
| Global | There are likely restrictions placed upon the customer from combining ad impression information to PII.|
| Europe | Most countries in the European Union do not consider analytics cookies strictly necessary.|
| Europe | Adobe has enabled the setting IP-Obfuscation: Enabled - IP Removed (x.x.x.x) by default for all customers with a report suite set in EMEA. With this setting, the IP address will be completely replaced with the value (x.x.x.x) after geolookup and is no longer available as a data point. This basic replacement method cannot be reverse-engineered back to a unique, specific IP Address. Neither the customer nor Adobe can access the IP address; it is irreversibly anonymized. For more information about other IP obfuscation settings, see [General Account Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) in the Admin user guide.|
| Global | A customer can set the cookie lifetime variable in the JavaScript measurement code to a value of „none," „session" or another specified value measured in seconds.|
| Europe | Replace the last octet of IP addresses with 0	Removing the last octet is done before any processing is done on the hit, including before IP filtering/exclusion, before checking bot rules, before Geosegmentation lookups, etc. As such, the last octet is replaced with a 0, and IP exclusion rules should be updated to match IP addresses with a zero on the end. Matching * should match 0. For example, the IP address 11.22.33.44 gets changed to 11.22.33.0. Geosegmentation data will not be quite as exact as when the whole IP address is used. Specifically, city accuracy is going to be more affected than country or region accuracy. Both Bot rules and VISTA rules are affected because the entire IP address is unavailable to them. In addition, any processing rules that are IP based, including marketing channel rules and report suite processing rules, are affected by this setting.
Note: This setting is enabled by default for any new report suites created in the London Data Center after January 2019, but only if the settings for those report suites are copied from a template listed in the Admin Console. Report suites whose settings are duplicated from other report suites will inherit all settings from the selected report suite.|
| Germany | If you do not already have a Data Processing Agreement for Adobe Analytics in place with Adobe, you should contact your Adobe Account Manager or Customer Success Manager, who will work with the Adobe Legal Department to get the DPA in place.|

## EMEA Data Center Location {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

The following EMEA data center currently hosts Adobe Analytics data: 

|Adobe Name|Address|Facility Type (Operator)|Solution Components Supported|Certifications|
|--- |--- |--- |--- |--- |
|LON5|3 Centro  Boundary Way  Hemel Hempstead HP2 7SU  UK|Colocation Facility  (Gyron)|Multichannel Analytics,  Digital Analytics|SSAE 16|
