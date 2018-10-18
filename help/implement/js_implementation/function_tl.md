---
description: File downloads and exit links can be automatically tracked based on parameters set in the AppMeasurement for JavaScript file.
keywords: Analytics Implementation
seo-description: File downloads and exit links can be automatically tracked based on parameters set in the AppMeasurement for JavaScript file.
seo-title: The s.tl() Function - Link Tracking
solution: Analytics
subtopic: Link tracking
title: The s.tl() Function - Link Tracking
topic: Developer and implementation
uuid: 8b8aea17-00e7-42a8-bef8-ef8b1393cf60
index: y
internal: n
snippet: y
---

# The s.tl() Function - Link Tracking

File downloads and exit links can be automatically tracked based on parameters set in the AppMeasurement for JavaScript file.

## The s.tl() Function - Link Tracking {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the AppMeasurement for JavaScript file. 

If needed, these types of links can be manually tracked using custom link code as explained below. In addition, custom link code can be used to track generic custom links that can be used for a variety of tracking and reporting needs.

## s.tl() Parameter Reference {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<table id="table_B93B42A7A9454A18B15108B179DA11F3"> 
 <thead> 
  <tr> 
   <th class="entry"> Variable </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> this </td> 
   <td> <p>The first argument should always be set either to this (default) or true. The argument refers to the object being clicked; when set to "this," it refers to the HREF property of the link. </p> <p>If you are implementing link tracking on an object that has no HREF property, you should always set this argument to "true." </p> <p>Because clicking a link often takes a visitor off the current page, a 500ms delay is used to ensure that an image request is sent to Adobe before the user leaves the page. This delay is only necessary when leaving the page, but is typically present when the <span class="wintitle"> s.tl() </span> function is called. If you want to disable the delay, pass the keyword 'true' as the first parameter when calling the <span class="wintitle"> s.tl() </span> function. </p> </td> 
  </tr> 
  <tr> 
   <td> linkType </td> 
   <td> <p> 
     <codeblock class="syntax javascript">
       s.tl(this,linkType,linkName,&amp;nbsp;variableOverrides,&amp;nbsp;doneAction) 
     </codeblock> </p> <p>linkType has three possible values, depending on the type of link that you want to capture. If the link is not a download or an exit link, you should choose the Custom links option.  </p>
    <table id="table_63B2354DD29A4F2CB3660C5BBAB969D2">  
    </table> </td> 
  </tr> 
  <tr> 
   <td> linkName </td> 
   <td> This can be any custom value, up to 100 characters. This determines how the link is displayed in the appropriate report. </td> 
  </tr> 
  <tr> 
   <td> variableOverrides </td> 
   <td> (Optional, pass null if not using) This lets you change variable values for this single call, It is similar to other <span class="keyword"> AppMeasurement </span> libraries. </td> 
  </tr> 
  <tr> 
   <td> useForcedLinkTracking </td> 
   <td> <p>This flag is used to disable forced link tracking for some browsers. Forced link tracking is enabled by default for FireFox 20+ and WebKit browsers. </p> <p> <b> Default Value</b> </p> <p>true </p> <p> <b> Example</b> </p> <p> 
     <codeblock class="syntax javascript">
       s.useForcedLinkTracking&amp;nbsp;=&amp;nbsp;false 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td> forcedLinkTrackingTimeout </td> 
   <td> <p>The maximum number of milliseconds to wait for tracking to finish before performing the <span class="wintitle"> doneAction </span> that was passed into <span class="filepath"> s.tl </span>. This value specifies the maximum wait time. If the track link call completes before this timeout, the <span class="wintitle"> doneAction </span> is executed immediately. If you notice that track link calls are not completing, you might need to increase this timeout. </p> <p> <b> Default Value</b> </p> <p>250 </p> <p> <b> Example</b> </p> <p> 
     <codeblock class="syntax javascript">
       s.forcedLinkTrackingTimeout&amp;nbsp;=&amp;nbsp;500 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td> doneAction </td> 
   <td> <p>An optional parameter to specify a navigation action to execute after the track link call completes when <span class="codeph"> useForcedLinkTracking </span> is enabled. </p> <p> <b> Syntax</b> </p> <p> 
     <codeblock class="syntax javascript">
       s.tl(linkObject,linkType,linkName,variableOverrides,doneAction) 
     </codeblock> </p> <p> <b> <span class="wintitle"> doneAction </span> </b> : (optional) Specifies the action to take after the link track call is sent or has timed out, based on the value specified by: 
     <codeblock class="syntax javascript">
       s.forcedLinkTrackingTimeout 
     </codeblock> The <span class="wintitle"> doneAction </span> variable can be the string navigate, which causes the method to set <span class="filepath"> document.location </span> to the href attribute of <span class="wintitle"> linkObject </span>. The <span class="wintitle"> doneAction </span> variable can also be a function allowing for advanced customization. </p> <p>If providing a value for <span class="wintitle"> doneAction </span> in an anchor <span class="wintitle"> onClick </span> event, you must return false after the <span class="filepath"> s.tl </span> call to prevent the default browser navigation. </p> <p>To mirror the default behavior and follow the URL specified by the href attribute, provide a string of navigate as the <span class="wintitle"> doneAction </span> . </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <span class="wintitle"> doneAction </span>. </p> <p> <b> Examples</b> </p> 
    <codeblock class="syntax javascript">
      &lt;a&amp;nbsp;href="..."&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,'navigate');return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt;&amp;nbsp;&lt;a&amp;nbsp;href="#"&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt;&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

**Example**

The following example of an [!UICONTROL s.tl()] function call uses the default 500 ms delay to ensure data is collected before leaving the page.

```js
s.tl(this,'o','link name');
```

The following example disables the 500 ms delay, if the user is not going to leave the page, or whenever the object being clicked has no HREF.

```js
s.tl(true,'o','link name');
```

The 500ms delay is a maximum delay. If the image requested returns in less than 500 ms, the delay stops immediately. This allows the visitor to move onto the next page or next action within the page.

The following examples are for handling custom links on WebKit browsers:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>Uses of custom link code are often very specific to your Web site and reporting needs. You can contact your Adobe Consultant or Customer Care before implementing custom link code to understand the possibilities available to you and how best to leverage this feature based on your business needs.

The basic code to track a link using custom link code is shown in the following example:

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>The [!UICONTROL s_gi] function must contain your report suite ID as a function parameter. Be sure to swap out [!DNL rsid] for your unique report suite ID.

>[!NOTE]
>
>If the link name parameter is not defined, the URL of the link (determined from the "this" object) is used as the link name.

[!DNL Analytics] variables can be defined as part of custom link code. 

## Automatic Tracking of Exit Links and File Downloads {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

The JavaScript file can be configured to automatically track file downloads and exit links based on parameters that define file download file types and exit links.

<!-- 

link_automatic.xml

 -->

The parameters that control automatic tracking are as follows:

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 

```

The parameters *`trackDownloadLinks`* and *`trackExternalLinks`* determine if automatic file download and exit link tracking are enabled. When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Example 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. When *`linkLeaveQueryString`*=false, exit links are determined using only the domain, path, and file portion of the link URL. When *`linkLeaveQueryString`*=true, the query string portion of the link URL is also used to determine an exit link.

## Example 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

With the following settings, the example below will be counted as an exit link:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='http://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 

```

## Example 3 {#section_2A78D05162D640169844A7D1E9799BAA}

With the following settings, the link below is not counted as an exit link:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='http://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 

```

>[!NOTE]
>
>A single link can be tracked only as a file download or exit link, with file download taking priority. If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. The following table summarizes the automatic tracking of file downloads and exit links.

## Manual Link Tracking Using Custom Link Code {#concept_7113B5D037BE4622B6934554C6D18F96}

Custom link code lets file downloads, exit links, and custom links be tracked in situations where automatic tracking is not sufficient or applicable.

<!-- 

link_manual.xml

 -->

Custom link code is typically implemented by adding an [!UICONTROL onClick] event handler to a link or by adding code to an existing routine. It can be implemented from essentially any JavaScript event handler or function.

Link Tracking consists of calling the AppMeasurement for JavaScript function whenever the user performs actions that generate data you want to capture. This function, [!UICONTROL s.tl()], is either called directly in an event handler, such as [!UICONTROL onClick] or [!UICONTROL onChange], or from within a separate function. This [!UICONTROL s.tl()] function has five arguments. The first three are required:

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## Custom Link Tracking on FireFox and WebKit Browsers {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

JavaScript H.25 includes an update to ensure that link tracking completes successfully on WebKit browsers (Safari and Chrome). JavaScript H.26 includes an update to ensure that link tracking completes successfully on FireFox 20+.

After this update, download and exit links that are automatically tracked (determined by [!DNL s.trackDownloadLinks]and [!DNL s.trackExternalLinks]) are tracked successfully. If you are tracking custom links using manual JavaScript calls, you need to modify how these calls are made. For example, exit and download links are often tracked using code similar to the following: 

```js
<a href="http://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

Internet Explorer executes the track link call and open the new page. Other browsers might cancel execution of the track link call when the new page opens. This often prevents track link calls from completing.

To work around this behavior, H.25 (released July 2012) includes an overloaded track link method ( [!DNL s.tl]) that forces browsers with this behavior to wait for the track link call to complete. This new method executes the track link call and handles the navigation event, instead of using the default browser action. This overloaded method requires an additional parameter, called [!UICONTROL doneAction], to specify the action to take when the link tracking call completes.

To use this new method, update calls to [!DNL s.tl] with an additional [!UICONTROL doneAction] parameter, similar to the following:

```js
<a href="http://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

Passing navigate as the [!UICONTROL doneAction] mirrors the default browser behavior and opens the URL specified by the href attribute when the tracking call completes.

In JavaScript H.25.4 (released February 2013), the following scope limitations were added to links tracked when `useForcedLinkTracking` is enabled. The automatic forced link tracking applies only to:

* `<A>` and `<AREA>` tags. 

* The tag must have an `HREF` attribute. 
* The `HREF` can't start with `#`, `about:`, or `javascript:`. 

* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

## Link Tracking Using an Image Request {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

Links can be tracked without calling the s.tl() function by constructing an image request.

<!-- 

link_img.xml

 -->

Image requests are hard coded by adding the "pe" parameter to your image request src parameter as follows:

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_d = download 
* lnk_e = exit 
* lnk_o = custom

Additionally, a link URL can be specified by passing the URL in the pev1 parameter:

```
pev1=mylink.com
```

A link name can be specified by passing the name in the pev2 parameter:

```
pev2=My%20Link
```

For example:

```
<img src="http://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## Setting Additional Variables for File Downloads, Exit Links, and Custom Links {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

They are, by default, set within the JS file as follows:

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

The *`linkTrackVars`* parameter should include each variable that you want to track with every file download, exit link, and custom link. The *`linkTrackEvents`* parameter should include each event you want to track with every file download, exit link, and custom link. When one of these link types occur, the current value of each variable identified is tracked.

For example to track prop1, eVar1, and event1 with every file download, exit link, and custom link, use the following settings within the global JS file:

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>If *`linkTrackVars`* (or *`linkTrackEvents`*) is null (or an empty string), all [!DNL Analytics] variables (or events) that are defined for the current page are tracked. This most likely inflates instances of each variable inadvertently and should be avoided.

## Best Practices {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. Instances of each variable and event can be inflated in situations where the variable (or event) applies to the current page, but not the specific file download, exit link, or custom link.

To ensure that the proper variables are set with custom link code, Adobe recommends setting *`linkTrackVars`* and *`linkTrackEvents`* within the custom link code, as follows:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 

```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>In the above example, the value for prop1 is set within the custom link code itself. The value of prop2 comes from the current value of the variable as set on the page.

## Using Function Calls with Custom Link Code {#concept_DB662C93B3ED415DB72C80270502BE5D}

Due to the complex nature of custom link code, you can consolidate the code into a self-contained JavaScript function (defined on the page or in a linked JavaScript file) and make calls to the function within the [!UICONTROL onClick] handler.

<!-- 

link_functions.xml

 -->

For example, you could insert the following two functions in your `AppMeasurement.js` file, just below the `s_doPlugins()` function, and then use them throughout your site:

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>If needed, you can pass the link type and link name as additional parameters for the JavaScript function.

You can use code similar to the following to call these functions:

```
<a href=”http://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## Avoiding Duplicate Link Counts {#section_9C3F73DE758F4727943439DED110543C}

It is possible for the link to be double-counted in situations where the link is normally captured by automatic file download or exit link tracking.

For example, if you are tracking PDF downloads automatically, the following code results in a duplicate download count:

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

To ensure link double counting does not occur, use the following modified JavaScript function:

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

The last two lines of the code above modify the behavior of custom link code so only the automatic tracking behavior occurs, eliminating any possible double counting. 

## Popup Windows with useForcedLinkTracking {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, AppMeasurement overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. AppMeasurement executes the track link call and handles the navigation event manually, instead of using the default browser action.

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent AppMeasurement from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

This allows the link to be tracked and the popup to load as expected. 

## Links from URL Shorteners {#concept_CD792362A8E04448B452BE9A18772024}

Links from URL shortener services (such as bit.ly) are typically not tracked as page views or as referrers. These services return 301/302 redirects with the full URL to the web browser, which then sends a new, separate request to the full URL. The original referrer is preserved since the shortener is no longer in the loop, and there isn't an indication on the request that a redirect service was used to get the URL.

<!-- 

link_shortener.xml

 -->

Due to the variety of services available, we recommending testing the specific scenarios in use on your site to determine the redirect mechanism used by the service. 

## Link Tracking Variables in doPlugins {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

To help manage link tracking, these following variables are populated before the `doPlugins` function runs.

<!-- 

util_linkhandler.xml

 -->

Inside of `doPlugins`, you can use the following values to modify link tracking behavior. For example, you can abort tracking, or add additional variables to tracking requests. 

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Impact </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>Contains the automatically determined link type, if any. Can be set to one of the following: </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d (download) </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e (exit) </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o (custom/other) </li> 
    </ul> <p>This is the <span class="codeph"> pe </span> parameter in the image request. </p> </td> 
   <td colname="col3"> <p>If set with <span class="codeph"> linkURL </span> or <span class="codeph"> linkName </span>, a server call is sent as a download, custom, or exit link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>The name that will appear in the custom, download or exit link report. Truncated at 100 characters. Can be set to any string. </p> <p>This is the <span class="codeph"> pev2 </span> parameter in the image request. </p> </td> 
   <td colname="col3"> <p> If set with <span class="codeph"> linkType </span> , an image request will be sent as a download, custom or exit link </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>The URL of the link, which acts as the name if a linkName does not exist. Can be set to any URL string. </p> <p>This is the <span class="codeph"> pev1 </span> parameter in the image request. </p> </td> 
   <td colname="col3"> <p>If set with <span class="codeph"> linkType </span>,&nbsp;an image request will be sent as a download, custom or exit link </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkObject </td> 
   <td colname="col2"> <p>The clicked object for reference. This is read-only. </p> </td> 
   <td colname="col3"> <p>No direct impact on measurement. </p> </td> 
  </tr> 
 </tbody> 
</table>

** Example**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## Validating File Downloads, Exit Links, and Custom Links {#concept_0B43AD582D3E470899FCCB58E44D3D49}

To fully validate download, exit, and custom links, Adobe recommends using a packet analyzer to examine the links in real-time.

<!-- 

downloads_validate.xml

 -->

File downloads, exit links, and custom links are not page views, so the [!UICONTROL DigitalPulse Debugger] tool cannot be used to verify parameters and variable settings. You must use a [Packet Analyzer](../impl_testing/packet_monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) to view track link data. 
