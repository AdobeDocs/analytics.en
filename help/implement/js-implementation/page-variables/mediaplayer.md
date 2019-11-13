---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# mediaPlayer

This variable specifies the player used to consume a video or media item.

<!-- 

mediaPlayer.xml

 -->

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 Bytes  | pev3  | Video Players  | None  |

**Syntax and Possible Values** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack Method:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Manual Tracking Method:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Possible Values:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Examples** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pitfalls, Questions, and Tips** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

You must call the media tracking methods only if player cannot be tracked using s.Media.autoTrack = true.

