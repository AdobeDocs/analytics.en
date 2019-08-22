---
description: Shows the Lyris plug-in code to use with Adobe Analytics.
seo-description: Shows the Lyris plug-in code to use with Adobe Analytics.
seo-title: Query String Param Plug-In Code
solution: Analytics
title: Query String Param Plug-In Code
uuid: 4543dcfd-ff53-49d5-a413-723848470053
index: y
internal: n
snippet: y
---

# Query String Param Plug-In Code{#query-string-param-plug-in-code}

Shows the Lyris plug-in code to use with Adobe Analytics.

>[!NOTE]
>
>Please make sure that you reserved the necessary eVars in the Admin Tool of Adobe Analytics before you work with the code below. Once you know which eVars you have reserved, replace eVarN with the relevant eVar. E.g. eVar10.

```
/* 
  * Plugin: getQueryParam 2.3 
  */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/*in the s_doPlugins function - Replace N with actual eVar number*/ 
s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Message ID in eVarN variable s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Recepient ID in eVarN variable 

```

