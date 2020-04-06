---
description: Shows metrics based on whether the device has JavaScript enabled, disabled, or whether it is counted as "unidentified".
title: JavaScript Support
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
---

# JavaScript Support

Shows metrics based on whether the device has JavaScript enabled, disabled, or whether it is counted as "unidentified".

>[!NOTE] In early November 2016, we plan to remove the restriction where JavaScript is always listed as *`disabled / unidentified`* for Mobile devices.

The JavaScript report correspond to the column javascript in the raw data.

javascript is a visit-level field, so it persists the value from the first hit in the visit. The column javascript is based on the first value present in the j_jscript column (like a visit_referrer will only persist the first referrer of the visit).

j_jscript is populated from the parameter j from the Adobe Analytics image request.

Here is an example:

|  Hit  | j_jscript  | javascript  |
|---|---|---|
|  1  |  | 0  |
|  2  | 1.6  | 0  |
|  3  | 1.6  | 0  |

As a result, it does not matter if you had a javascript version specified at some point in the visit - it will always be displayed as not Javascript because the first hit did not contain any value for j_jscript.
