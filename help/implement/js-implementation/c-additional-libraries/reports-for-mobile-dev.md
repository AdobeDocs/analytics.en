---
description: Because mobile devices are tracked via a beacon, just like other visitors, most reports are available and correct.
keywords: Analytics Implementation;reports;mobile protocols;search engines;search keywords;referring domains;referrers;geosegmentation;domains;connection type;time zone;cookies;java;javascript;monitor colors;monitor resolution;browser width;height;netscape plug-in
solution: Analytics
title: Reports for devices using mobile protocols
topic: Developer and implementation
uuid: 4aab125d-c131-4402-9bc8-1c7fd1bb2bee
---

# Reports for devices using mobile protocols

Because mobile devices are tracked via a beacon, just like other visitors, most reports are available and correct.

 [!DNL VISTA] can be used to alter data collected from both Mobile and standard methods. All [!UICONTROL Custom] [!UICONTROL Insight] ( [!UICONTROL prop] and [!UICONTROL eVar]), [!UICONTROL Event], [!UICONTROL Site Traffic], and [!UICONTROL Pathing] reports are supported.

## Search Engines, Search Keywords, Referring Domains, and Referrers {#section_184D2EF9D906443FBDED04A09CDC50E9}

These reports only have data if the referrer is populated in the image request sent from the mobile page. The referrer is populated via the "r" query string parameter, as outlined in the Implementing without JavaScript white paper. You must also manually pass the referrer information into the image request.

The 'r' query string parameter must include the protocol of the referrer. If the protocol is left off, the referrer report is not populated. For example, use `r=https://msn.com` not `r=msn.com`.

## Geosegmentation and Domains {#section_2B4E9443AAFE4ECA961F9E993592E628}

Geosegmentation reports are based on the IP address of the device sending the request. Because mobile devices rely on a gateway to request images from Adobe servers, the gateway's IP address is used to determine the geo-location of the user. Because gateways and their IP addresses are registered for large networks, the associated geo-location is often less accurate.

Domains are also based on the IP address of the gateway, which means the domains report often contains the name of the carrier who owns the gateway. Due to Mobile Virtual Network Operators (MVNOs), this may not be accurate.

## Connection Types {#section_0E7FA18178B848AEBB839B1694B4D691}

Adobe maintains a known range of IP addresses that belong to mobile carriers. When a hit is received from an IP range that belongs to a known mobile carrier, the hit appears as "Mobile Carrier" on the Connection Type Report. Otherwise, mobile traffic is listed under "Lan/Wifi".

## Time Zones, Cookies, Java, JavaScript, Monitor Colors and Resolutions, Browser Width and Height, and Netscape Plug-ins {#section_158C848273AE4691B4413767E849E846}

These reports are all collected by using JavaScript to detect specific settings of the browser. Because JavaScript is not used to create the image beacon on mobile devices, data collected from mobile users is not included in these reports.
