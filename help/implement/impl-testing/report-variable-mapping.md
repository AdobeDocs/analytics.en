---
description: The tables below display the report to variable mapping, or the reports and the variables that are used in them.
keywords: Analytics Implementation
seo-description: The tables below display the report to variable mapping, or the reports and the variables that are used in them.
seo-title: Report to variable mapping
solution: Analytics
title: Report to variable mapping
topic: Developer and implementation
uuid: 219a1716-1161-4229-a231-353bb7d8effe
index: y
internal: n
snippet: y
---

# Report to variable mapping

The tables below display the report to variable mapping, or the reports and the variables that are used in them.

<a id="section_3DEC97FB4CCE43A09094C177D7BD0D87"></a>

**Conversion Reports** The following table lists the conversion variables that are used to populate each report: 

|  Purchases  |
|---|
|  Conversions and Averages  | s.events, s.products, s.purchaseID  | Set s.events to purchase, product detail, order number  |
|  Revenue  | s.events, s.products, s.purchaseID  | Set s.events to purchase, product detail, order number  |
|  Orders  | s.events, s.products, s.purchaseID  | Set s.events to purchase, product detail, order number  |
|  Units  | s.events, s.products, s.purchaseID  | Set s.events to purchase, product detail, order number  |

|  Shopping Cart  |
|---|
|  Conversions and Averages  | s.events, s.products, s.purchaseID  |  |
|  Cart  | s.events  | Set s.events to scOpen  |
|  Cart Views  | s.events  | Set s.events to scView  |
|  Cart Additions  | s.events  | Set s.events to scAdd  |
|  Cart Removals  | s.events  | Set s.events to scRemove  |
|  Checkouts  | s.events  | Set s.events to scCheckout  |

|  Custom Events  |
|---|
|  Custom Event 1  | s.events  | Populate with event1 - event100  |
|  …  | …  | Populate with event1 - event100  |
|  Custom Event 100  | s.events  | Populate with event1 - event100  |

|  Products  |
|---|
|  Conversions and Averages  | s.events, s.products, s.purchaseID  |  |
|  Products  | s.products, s.events  | May vary depending on right column metrics  |
|  Cross Sell  | s.products, s.events, s.purchaseID  | May vary depending on right column metrics  |
|  Categories  | s.products  | May vary depending on right column metrics  |

|  Campaigns  |
|---|
|  Conversions and Averages  | s.products, s.events, s.campaign  |  |
|  Tracking Code  | s.campaign  |  |
|  Creative Elements  | N/A  | Defined in [!DNL Analytics]  |
|  Campaigns  | N/A  | Defined in [!DNL Analytics]  |

|  Customer Loyalty  |
|---|
|  Customer Loyalty  | s.products, s.events, s.purchaseID  | Variables set on the Order Confirmation (Thank You!) page  |

|  Sales Cycle  |
|---|
|  Days Before First Purchase  | s.products, s.events, s.purchaseID  | Variables set on the Order Confirmation (Thank You!) page  |
|  Days Since Last Purchase  | s.products, s.events, s.purchaseID  | Variables set on the Order Confirmation (Thank You!) page  |
|  Visit Number  | s.products, s.events, s.purchaseID  | Variables set on the Order Confirmation (Thank You!) page  |
|  Daily Unique Customers  | s.products, s.events, s.purchaseID  | Variables set on the Order Confirmation (Thank You!) page  |
|  Monthly Unique Customers  | s.products, s.events, s.purchaseID  | Variables set on the Order Confirmation (Thank You!) page  |
|  Yearly Unique Customers  | s.products, s.events, s.purchaseID  | Variables set on the Order Confirmation (Thank You!) page  |

|  Finding Methods  |
|---|
|  Referring Domains  | N/A  | Automatically set by the .JS file  |
|  Original Referring Domains  | N/A  | Automatically set by the .JS file  |
|  Search Engines  | N/A  | Automatically set by the .JS file  |
|  Search Keywords  | N/A  | Automatically set by the .JS file  |

|  Visitor Profile  |
|---|
|  Top Level Domains  | N/A  | Automatically set by the .JS file  |
|  Languages  | N/A  | Automatically set by the .JS file  |
|  Time Zones  | N/A  | Automatically set by the .JS file  |
|  States  | s.state  | Variable set on the Order Confirmation (Thank You!) page  |
|  Zip/Postal Codes  | s.zip  | Variable set on the Order Confirmation (Thank You!) page  |
|  Domains  | N/A  | Automatically set by the .JS file  |

|  Technology  |
|---|
|  Browsers  | N/A  | Automatically set by the .JS file  |
|  Operating Systems  | N/A  | Automatically set by the .JS file  |
|  Monitor Resolutions  | N/A  | Automatically set by the .JS file  |

|  Site Path  |
|---|
|  Page Value  | s.pageName, s.products, s.events, s.purchaseID  |  |
|  Entry Pages  | s.pageName  |  |
|  Original Entry Pages  | s.pageName  |  |
|  Pages Per Visit  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Time Spent on Site  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Site Sections  | [!UICONTROL s.channel]  | Same as [!UICONTROL Channel] report in [!UICONTROL Traffic] reports section  |

|  Customer Variables  |
|---|
|  Custom eVar 1  | [!UICONTROL s.eVar] 1  |  |
|  Custom eVar 2  | [!UICONTROL s.eVar] 2  |  |
|  Custom eVar 3  | [!UICONTROL s.eVar] 3  |  |
|  …  |  |  |
|  Custom eVar 75  | [!UICONTROL s.eVar] 75  |  |

## Traffic Reports {#section_76A74C3D7B60461D9ADE0E5E183DD777}

The following table lists the [!UICONTROL traffic] variables that are used to populate each report: 

|  Calculated Metrics  |
|---|
|  N/A  | N/A  | N/A  |

|  Site Traffic  |
|---|
|  Page Views  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Hourly Unique Visitors  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Daily Unique Visitors  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Monthly Unique Visitors  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Yearly Unique Visitors  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Visits  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  File Downloads  | N/A  | Automatically tracked by .JS file (depends on .JS variable settings)  |

|  Finding Methods  |
|---|
|  Referring Domains  | N/A  | Automatically set by the .JS file  |
|  Referrers  | N/A  | Automatically set by the .JS file  |
|  Search Engines  | N/A  | Automatically set by the .JS file  |
|  Search Keywords  | N/A  | Automatically set by the .JS file  |
|  Return Frequency  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Daily Return Visits  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Return Visits  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  Visit Numbers  | N/A  | Calculated by business rules in [!DNL Analytics]  |

|  Visitor Profile  |
|---|
|  Domains  | N/A  | Automatically set by the .JS file  |
|  Top Level Domains  | N/A  | Automatically set by the .JS file  |
|  Languages  | N/A  | Automatically set by the .JS file  |
|  Time Zones  | N/A  | Automatically set by the .JS file  |
|  Visitor Details  | N/A  | Automatically set by the .JS file  |
|  Last 100 Visitors  | N/A  | Calculated by business rules in [!DNL Analytics]  |
|  User Home Page  | N/A  | Automatically set by the .JS file  |
|  Key Visitors  | N/A  | Based on visitor's IP address  |
|  Pages Viewed by Key Visitors  | N/A  | Based on visitor's IP address  |

|  Geo Segmentation  |
|---|
|  Countries  | N/A  | Based on visitor's IP address  |
|  U.S. States  | N/A  | Based on visitor's IP address  |
|  DMA  | N/A  | Based on visitor's IP address  |
|  International Cities  | N/A  | Based on visitor's IP address  |
|  U.S. Cities  | N/A  | Based on visitor's IP address  |

|  Technology  |
|---|
|  Browser Types  | N/A  | Automatically set by the .JS file  |
|  Browsers  | N/A  | Automatically set by the .JS file  |
|  Mobile Devices  | N/A  | Automatically set by the .JS file  |
|  Browser Width  | N/A  | Automatically set by the .JS file  |
|  Browser Height  | N/A  | Automatically set by the .JS file  |
|  Operating Systems  | N/A  | Automatically set by the .JS file  |
|  Monitor Color Depth  | N/A  | Automatically set by the .JS file  |
|  Monitor Resolutions  | N/A  | Automatically set by the .JS file  |
|  Netscape Plug-ins  | N/A  | Automatically set by the .JS file  |
|  Java  | N/A  | Automatically set by the .JS file  |
|  JavaScript  | N/A  | Automatically set by the .JS file  |
|  JavaScript Version  | N/A  | Automatically set by the .JS file  |
|  Cookies  | N/A  | Automatically set by the .JS file  |
|  Connection Types  | N/A  | Automatically set by the .JS file  |
|  Segmentation  |

|  Segmentation  |
|---|
|  Most Popular Pages  | s.pageName  |  |
|  Most Popular Site Sections  | s.channel  |  |
|  Most Popular Servers  | s.server  |  |

|  Custom Insight  |
|---|
|  Custom Links  | s.linkName  | Requires custom implementation  |
|  Custom Insight 1  | s.prop1  |  |
|  …  | …  |  |
|  Custom Insight 75  | s.prop75  |  |

|  Hierarchies  |
|---|
|  Hierarchy 1  | s.hier1  |  |
|  …  | …  |  |
|  Hierarchy 5  | s.hier5  |  |

## Pathing Reports {#section_85E0A2396B894659A6BE572819263E95}

The following table lists the pathing variables that are used to populate each report within [!DNL Analytics]: 

|  Pages  |
|---|
|  Page Summary  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Page Value  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Most Popular Pages  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Reloads  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Clicks to Page  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Time Spent on Page  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Pages Not Found  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |

|  Entries and Exits  |
|---|
|  Entry Pages  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Exit Pages  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Exit Links  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |

|  Complete Paths  |
|---|
|  Full Paths  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Longest Paths  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Path Length  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Time Spent per Visit  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Single-page Visits  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |

|  Advanced Analysis  |
|---|
|  Previous Page  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Next Page  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Previous Page Flow  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Next Page Flow  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  PathFinder  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |
|  Fall-out  | s.pageName (or other pathed variable)  | Also depends on internal business rules  |

