---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# mediaSession

This variable specifies the segments of a video or media asset consumed.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Max Size </th> 
   <th class="entry"> Debugger Parameter </th> 
   <th class="entry"> Reports Populated </th> 
   <th class="entry"> Default Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 Bytes </td> 
   <td> pev3 </td> 
   <td> Time Spent on Video <p>Video Segments Viewed </p> </td> 
   <td> None </td> 
  </tr> 
 </tbody> 
</table>

**Syntax and Possible Values** {#section_9A63266633C4427CB4A6549E4D887B85}

**autoTrack Method:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* does not need to be implemented explicitly. It will be determined automatically by the AppMeasurement for JavaScript code.

**Manual Tracking Method:**

Syntax:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 

```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Possible Values:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 

```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Examples** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 

```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Pitfalls, Questions, and Tips** {#section_1BCEB037AB724B6EBE87420BD3604B88}

You must call the media tracking methods only if player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.
