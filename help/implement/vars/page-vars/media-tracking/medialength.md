---
title: mediaLength
description: The length of the media tracked.
---

# mediaLength

The  variable specifies the total length of the media being played.


<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
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
   <td> No max size for entire pev3 request - size is limited to the browser's URL length limit. </td> 
   <td> pev3 </td> 
   <td> Time Spent on Video; <p>Video Segments Viewed </p> </td> 
   <td> None </td> 
  </tr> 
 </tbody> 
</table>

**Syntax and Possible Values** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**autoTrack Method:**

If using [!UICONTROL s.Media.autoTrack], the [!UICONTROL mediaLength] variable does not need to be implemented explicitly. It is determined automatically by the AppMeasurement for JavaScript code.

**Manual Tracking Method:**

Syntax: 

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Possible Values: 

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Examples** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pitfalls, Questions, and Tips** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* You must call the media tracking methods only if the player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.
* If not tracking using [!UICONTROL autoTrack], be sure to set the length in seconds.

