---
description: Plug-in support has changed in the new version of JavaScript AppMeasurement.
keywords: Analytics Implementation;appmeasurement;javascript;plugin;plug-in
seo-description: Plug-in support has changed in the new version of JavaScript AppMeasurement.
seo-title: AppMeasurement plug-in support
solution: Analytics
subtopic: JavaScript AppMeasurement
title: AppMeasurement plug-in support
topic: Developer and implementation
uuid: e048e16b-994a-4079-bde4-3faa3df8c96d
index: y
internal: n
snippet: y
---

# AppMeasurement plug-in support

Plug-in support has changed in the new version of JavaScript AppMeasurement.

## Tested Plug-ins {#section_48415FB895E6455FAC34B0B96DE6EBE7}

The following plug-ins were tested and verified as compatible:

* [appendList](../../../implement/js-implementation/c-mplementation-plug-ins/appendlist.md#concept_C4588F8E123E4DB99C8ADCD5A524D693) 
* crossVisitParticipation 
* userAgentManager 
* [getTimeParting](../../../implement/js-implementation/c-mplementation-plug-ins/gettimeparting.md#concept_3746EA1D1EF746049AE84105B911F44A) 
* join 
* split 
* [getDaysSinceLastVisit](../../../implement/js-implementation/c-mplementation-plug-ins/getdayssincelastvisit.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) 
* [getNewRepeat](../../../implement/js-implementation/c-mplementation-plug-ins/getnewrepeat.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) 
* getTimeToComplete 
* manageVars (requires `s.pt` plugin utility) 
* channelManager 
* Cookie Combining Utility 
* getPageName

## Untested Plug-ins {#section_32BA7CAB37554A278170A728F1D65CE9}

The following plug-ins should continue to work since the underlying functionality is still supported, but they have not been tested and verified as compatible. You should test these plug-ins in your development environment before migration.

* getActionDepth 
* [getAndPersistValue](../../../implement/js-implementation/c-mplementation-plug-ins/getandpersistvalue.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) 
* getCookiesAccepted 
* [getValOnce](../../../implement/js-implementation/c-mplementation-plug-ins/getvalonce.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)

## Unsupported Plug-ins {#section_73AF0EE257A44DCE9232F85A95AB8884}

These plug-ins are not supported and no longer function due to their use of functionality that no longer exists in the new AppMeasurement for JavaScript library.

* callBack 
* channelExtract 
* detectRIA 
* deviceOrientationChanges 
* DynamicObjectIDs 
* Form Analysis 
* manageQueryParam 
* HTML5Storage

