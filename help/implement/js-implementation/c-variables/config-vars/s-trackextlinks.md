---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.trackExternalLinks

If  is 'true,'  and  are used to determine whether any link clicked is an exit link.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | True  |

The *`trackExternalLinks`* variable should only be set to 'false' if there are no exit links on your site, or if you don't care to track the number of clicks on those exit links. An exit link is any link that takes a visitor off of your site. If *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. The data that is sent with an exit link includes the link URL, link name, and visitor click map data for that link. If *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

## Syntax and Possible Values

The *`trackExternalLinks`* variable is expected to be either 'true' or 'false.'

```
js
s.trackExternalLinks=true|false

```

## Examples

```
js
s.trackExternalLinks=true 

```

```
js
s.trackExternalLinks=false

```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map. 
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).
