---
description: The following table shows the difference between correct and incorrect code mistakes.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Common syntax mistakes
topic: Developer and implementation
uuid: 9845dcb9-9f10-4f65-a43d-2af41edaa122
---

# Common syntax mistakes

The following table shows the difference between correct and incorrect code mistakes.

|  Incorrect  | Correct  |
|---|---|
|  prop1  | s.prop1 (uses "s.")  |
|  s.evar1  | s.eVar1 (uses correct capitalization)  |
|  s.pagetype='errorpage';  | s.pageType='errorPage'; (uses correct capitalization)  |
|  s.tl(this,o,pageA)  | s.tl(this,'o','pageA'); (correct usage of single quotes)  |
|  s.events='event1'; s.events='event2';  | s.events='event1,event2'; (correct format)  |
|  s.pageName="John" (smart quotes on)  | s.pageName="John" (smart quotes off)  |
|  s.products="shoes,UX4879,1,19.99"  | s.products="shoes;UX4879;1;19.99" (uses semicolons, not commas)  |
|  s.products=";MacBook Air;1;$1999.99"  | s.products=";MacBook Air;1;1999.99" (does not use dollar signs)  |
|  s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183"  | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95" (round or truncate long prices)  |
|  var s_account="rsid1, rsid2"  | var s_account="rsid1,rsid2" (no space between report suite IDs when doing multi-suite tagging)  |
|  s.events="event1, event2"  | s.events="event1,event2" (no space between event IDs when doing multi-event tagging)  |
|  s.products="product name"  | s.products=";product name" (semicolon used when no product category is listed)  |

## Additional Notes {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

Keep the closing HTML comment at the very end of the Adobe code (even if you are using the NOSCRIPT part of the script).
