---
description: The getTimeParting plug-in populates custom variables with hour of day, day of week, and weekend and weekday values into custom variables. Analysis Workspace offers out-of-the-box Time Parting dimensions. The plug-in should be used if time parting dimensions are needed in other Analytics solutions, outside of Analysis Workspace.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
---

# getTimeParting

The getTimeParting plug-in populates custom variables with hour of day, day of week, and weekend and weekday values into custom variables. [!UICONTROL Analysis Workspace] offers out-of-the-box Time Parting dimensions. The plug-in should be used if time parting dimensions are needed in other Analytics solutions, outside of [!UICONTROL Analysis Workspace].

This plug-in captures the date and time information available in the user's web browser. It obtains the hour of the day and the day of the week from this information. It then converts this data to the time zone of your choosing. It also accounts for Daylight Savings Time.

> [!NOTE] The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**Config Section**

Place the following code in the area of the [!DNL s_code.js] file labeled [!UICONTROL CONFIG SECTION], and make the necessary updates as described below.

`s._tpDST` - an array of DST values. The array is structured in the following format: `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6',
2020:'4/5,10/4',
2021:'4/4,10/3'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3',
2020:'3/8,11/1',
2021:'3/14,11/7'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27',
2020:'3/29,10/25',
2021:'3/28,10/31'}
```

Note for Northern Hemisphere clients: in the array DST values are DST start, DST end.

Note for Southern Hemisphere clients: in the array DST values are DST end, DST start.

**Parameters**

```js
var tp = s.getTimeParting(h,z);
```

* h = (required) Hemisphere - Specify what hemisphere you are converting the time to. This is a value of 'n' or 's'. This is used to determine how to use the DST array passed. If 'n' is passed the plugin uses the dates when DST is on. If 's' is passed the plugin uses the dates when DST is off.
* z = (optional) Time Zone - If you would like the data to be based upon a specific time period, then that will need to be specified as the hours different from GMT here. Note this should be the GMT during non DST. If no value is specified, it defaults to GMT (i.e. '-5' for US Eastern Time)

**Returns**

Returns a concatenated value of time at minute level and day of week, for example:

```
8:03 AM|Monday
```

You can then use [Classifications](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) to group visits into time periods. For example, you could set up a rule in Classification Rule Builder to bucket visits between 9:00 AM and 9:59 AM to "9:00 AM - 10:00 AM". As an alternative to classifications, you could provide additional client-side logic to bucket visits in JavaScript.

**Example Call**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**PLUGINS SECTION**

Add the following code to the [!UICONTROL PLUGINS SECTION] in the [!DNL s_code.js] file.

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**Notes**

* Always test plug-in installations to ensure that data collection is as expected before deploying to production.
* Configuration variables must be set for plugin to work correctly.

