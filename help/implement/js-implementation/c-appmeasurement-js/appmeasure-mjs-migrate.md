---
description: The following table contains a list of tasks you need to perform to migrate your implementation.
keywords: Analytics Implementation;appmeasurement;migrate;migrating;javascript
seo-description: The following table contains a list of tasks you need to perform to migrate your implementation.
seo-title: Migrating to AppMeasurement for JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrating to AppMeasurement for JavaScript
topic: Developer and implementation
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
---

# Migrating to AppMeasurement for JavaScript

The following table contains a list of tasks you need to perform to migrate your implementation.

>[!NOTE]
>
>We recommend migrating to the [Identity Service](/help/implement/js-implementation/c-unique-visitors/visid-service.md) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) Check plug-in compatibility

Where: s\_code.js

Some plug-ins are no longer supported. See [AppMeasurement Plug-in Support](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) .

![](assets/step2_icon.png) Download the new AppMeasurement

Where: Admin > Code Manager

The download zip contains a minified AppMeasurement.js file, and Javascript files for the Media and Integrate modules.

![](assets/step3_icon.png) Copy your s\_code.js customization to `AppMeasurement.js`.

Where: s\_code.js and AppMeasurement.js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (Optional) Update plug-ins

Where: AppMeasurement.js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md).

![](assets/step5_icon.png) (Optional) Update Media and Integrate modules

Where: AppMeasurement.js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Deploy new JavaScript

Where: Your website

The new JavaScript file can be deployed according to your standard process. Your existing page code is compatible with this version.
