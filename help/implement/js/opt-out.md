---
title: Opt-out links
description: Learn how to create an implement opt-out links for visitors to your site.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
---
# Implement opt-out links

>[!IMPORTANT]
>
>Adobe recommends using the opt-in service, especially for organizations concerned with GDPR regulations. See [Opt-in service overview](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) in the Experience Cloud Identity Service user guide.

Some visitors to your website prefer not to have their browsing information included in your data set. Adobe offers the ability to provide visitors to your website a means to opt out of their information being collected. All implementation types are accommodated; your organization is responsible for your own privacy policy and for remaining in compliance with your signed terms.

When a visitor reaches an opt-out URL, they are prompted to install an opt-out cookie. If a user chooses not to be tracked and an opt-out cookie is set, your JavaScript file continues to send data to Adobe servers. However, that data is not processed or included in reports.

>[!TIP]
>
>Adobe also offers privacy settings on a per-report suite basis. See [Privacy Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md) in the Admin user guide.

## Opt-out URL

The opt-out page for your organization depends on the [`trackingServer`](../vars/config-vars/trackingserver.md) variable value in your implementation.

* In the Analytics extension:
  1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
  1. Click the desired tag property.
  1. Click the [!UICONTROL Extensions] tab, then click [!UICONTROL Configure] under Adobe Analytics.
  1. Click the [!UICONTROL General] accordion, and note the [!UICONTROL Tracking Server] value.

* In a JavaScript implementation:
  1. On your web server, open the AppMeasurement.js file used on your site in a code or text editor.
  1. Note the `trackingServer` variable value.

* Using the [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html):
  1. Navigate to your site using the Chrome browser.
  1. Open the Experience Cloud Debugger, then go to the [!UICONTROL Network tab].
  1. Note the [!UICONTROL Request URL - Hostname] value.

Once you have found your implementation's `trackingServer` domain, append the path `/optout.html` to the end. For example:

* Third-party cookies: `https://example.data.adobedc.net/optout.html`
* First-party cookies: `https://stats.example.com/optout.html`

## Opt-out query string parameters

There are settings that you can automatically load onto this page by using query strings.

### Locale

Automatically switch the language of the opt-out page by including the `locale` query string parameter. Assign this query string parameter one of the following values:

* en_US (English, default)
* bg_BG (Bulgarian)
* zh_CN (Simplified Chinese)
* zh_TW (Traditional Chinese)
* cs_CZ (Czech)
* da_NK (Danish)
* nl_NL (Dutch)
* et_EE (Estonian)
* fi_FI (Finnish)
* fr_FR (French)
* de_DE (German)
* el_GR (Greek)
* it_IT (Italian)
* jp_JP (Japanese)
* ko_KR (Korean)
* lv_LV (Latvian)
* lt_LT (Lithuanian)
* nb_NO (Norwegian)
* pl_PL (Polish)
* pt_BR (Portuguese)
* sk_SK (Slovak)
* es_ES (Spanish)

For example, `https://example.data.adobedc.net/optout.html?locale=ko_KR` loads the opt-out page in Korean.

>[!TIP]
>
>The `en_US` query string value is not required, as the page loads in English by default.

### Popup

Adds a 'Close Window' button to the page, allowing the potential to make the opt-out page a popup window. Use the `popup` query string parameter, and give it a value of `1`.

For example, `https://example.data.adobedc.net/optout.html?popup=1` loads the opt-out page with a 'Close Window' button.

>[!NOTE]
>
>Historically this query string parameter forced a popup window. However, most modern browsers give control around popups to the end user.

### Single click opt-out

Allows the user to immediately opt out of tracking. Add the two query string parameters `opt_out` and `confirm_change`, giving each a value of `1`.

For example, `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` immediately installs the opt-out cookie on the visitor's page.

### Single click opt-in

Allows the user to immediately opt back in to tracking by deleting the opt-out cookie. Add the two query string parameters `opt_in` and `confirm_change`, giving each a value of `1`.

For example, `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` immediately deletes the opt-out cookie for the visitor.
