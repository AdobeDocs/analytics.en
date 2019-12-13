---
title: Internal Traffic
description: The Internal Traffic plugin dynamically identifies visitors originating from an internal network.
---

# Internal Traffic

The Internal Traffic plugin dynamically identifies visitors originating from an internal network.

Identifying internal and external traffic promotes greater accuracy in all types of reporting, by providing a mechanism that filters and segments data being collected. Implemented correctly, it would also eliminate the need for a VISTA rule or Processing Rule that are typical approaches to identifying such traffic.

## How does the Internal Traffic plugin work?

The plugin attempts to load a file that would only be available within your internal network/intranet, i.e. a 1x1 transparent pixel. If it is loaded successfully, traffic for that visitor would be identified as internal. Anything else would be external traffic.

## Considerations

* The only downside to this approach is that a 404 error is displayed in the browser console for external visitors on the first page of their visit. This will not impact the user experience.
* We strongly suggest that you obtain approval from your Network or InfoSec team before trying to load a pixel hosted internally.
* Although the plugin will not move traffic to another report suite or exclude it from reporting (as might be done with a VISTA rule), custom logic can be included with its implementation, so that this functionality could take place client side.

## Implementation

1. Add your Intranet Pixel: You can add any type of file on your intranet that the plugin would attempt to access. A 1x1 transparent pixel is recommended. It should be placed in a location on your Intranet that is widely accessible from within your internal network(s).
1. Configure an eVar: An eVar will need to be added within your destination report suite. It should have an expiration of "Visit" and allocation of "Original Value (First)".
1. Define the internal URL: Within the AppMeasurement configuration variables and before doPlugins is instantiated, define the internal URL variable (s.intURL) for the pixel or other file can be used for the traffic check. For example: `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to "internal" or "external".
1. Add the Plugin Source Code: Include the plugin code below the doPlugins section of your AppMeasurement file.

## Plugin source code

Add this code below the doPlugins section of your AppMeasurement library.

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## Other Notes

* Always test plug-in installations to ensure that data collection happens as expected before deploying them in a production environment.
* Your implementation might be using a different object name than the default Adobe Analytics "s" object. If so, please update the object name accordingly.
* If you employ a Tag Management System, please follow its steps to update doPlugins and the other custom plugins.
