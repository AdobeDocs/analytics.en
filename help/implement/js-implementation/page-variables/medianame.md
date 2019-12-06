---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
subtopic: Variables
title: Page variables
topic:
uuid:
---

# mediaName

This variable specifies the name of the video or media item.


<!-- 

mediaName.xml

 -->

It is only available via the [!UICONTROL Data Insertion API] and [!UICONTROL Full Processing Data Source].

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  64 KB  | pev3  | Videos; Next Video Flow; Previous Video Flow; Video Segments Viewed; Time Spent on Video  | None  |

**Syntax and Possible Values** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**autoTrack Method:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* variable does not need to be implemented explicitly. It is determined automatically by the AppMeasurement for JavaScript code.

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

```js
s.Media.close(mediaName)
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

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Examples** {#section_4B9584265B1A47289818141B2A88021D}

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
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Pitfalls, Questions, and Tips** {#section_941A445BB52E4063B0F6920E61BB90DE}

* You must call the media tracking methods only if player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.
* This variable is stored as a mySQL TEXT variable as opposed to VARCHAR(100).
