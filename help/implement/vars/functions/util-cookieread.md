---
title: Util.cookieRead
description: Gets the value for a cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
---
# Util.cookieRead

Cookies can store and retrieve information across pages on the same domain. Use the `Util.cookieRead()` method to retrieve a value from a cookie.

## Read cookies using the Adobe Analytics extension and the Web SDK extension

You can read cookies by setting values in data elements.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Data Elements] tab, then click the desired data element (or create a data element).
4. Set the [!UICONTROL Extension] drop-down list to **[!UICONTROL Core]**, and the [!UICONTROL Data Element Type] to **[!UICONTROL Cookie]**.
5. Enter the cookie name in the text field.

The cookie value is stored in the data element. You can then reference the data element in rules to assign the desired variables.

## s.Util.cookieRead() in AppMeasurement and the Analytics extension custom code editor

Call the `s.Util.cookieRead()` method to read a desired cookie value. Its only argument is a string, which is required. This method returns a string containing the cookie value. If the cookies does not exist, an empty string is returned.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
