---
description: Captures the language setting in the visitor's browser, letting you see the revenue and unique visitors related to the language setting. When you know the effect that preferred languages have on your site's success metrics, you can decide how to present your site in other languages. For example, if you notice that a large number of German-speaking customers generate shopping cart activity on your site, you can translate your site into that language and implement a marketing campaign to drive traffic to your German site.
seo-description: Captures the language setting in the visitor's browser, letting you see the revenue and unique visitors related to the language setting. When you know the effect that preferred languages have on your site's success metrics, you can decide how to present your site in other languages. For example, if you notice that a large number of German-speaking customers generate shopping cart activity on your site, you can translate your site into that language and implement a marketing campaign to drive traffic to your German site.
seo-title: Language
solution: Analytics
title: Language
topic: Reports
uuid: 04f1fc86-2738-4063-8091-772ddc59f9cf
---

# Language

Captures the language setting in the visitor's browser, letting you see the revenue and unique visitors related to the language setting. When you know the effect that preferred languages have on your site's success metrics, you can decide how to present your site in other languages. For example, if you notice that a large number of German-speaking customers generate shopping cart activity on your site, you can translate your site into that language and implement a marketing campaign to drive traffic to your German site.

 **[!UICONTROL Visitor Profile]** > **[!UICONTROL Languages]**

We populate this report based on the accept-language portion of the http header request. The language-accept HTTP header is configured as part of each browser’s language preference settings:

[https://www.w3.org/International/questions/qa-lang-priorities.en.php](https://www.w3.org/International/questions/qa-lang-priorities.en.php)

If a browser does not have a language specified, or if the browser returns a language ID=0, the report will show "Unspecified" in the graph. Browser support for this setting can affect the number of "Unspecified" returns.

Some line items in this report include regions. These are region subtags.

>[!NOTE]
>
>The Hourly time granularity is not supported.

