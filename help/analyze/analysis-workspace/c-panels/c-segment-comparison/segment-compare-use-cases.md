---
title: Segment Comparison Use Cases
description: Learn real-world use cases on how the segment comparison panel can be used to gain insight into marketing strategy.
keywords: Segment IQ
feature: Segmentation
role: User, Admin
exl-id: d7c02e5c-5313-4e12-86cb-d483644ccbc7
TQID: https://experienceleague.adobe.com/RSrhYA6EYk3UhFqMQ1FJVHzqA7RFIqdvSyvatTF0goE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Segment comparison use cases

The segment comparison panel is a widely used feature in Analysis Workspace. Customers frequently discover new ways to drive insights with when using the panel. Find below some typical use cases

## Use case 1: compare mobile versus desktop implementations

> *"You compared hits from one site to another site and quickly found a number of tagging inconsistencies. This way, you avoided data problems before product release."*

You are in charge of a mobile website and a desktop website, and tasked to make sure that tags are consistent across mobile and desktop. To make sure you do not miss anything important, you use the segment comparison panel to compare hits coming from their mobile site to hits coming from their desktop site. You notice that there are no checkout events on the mobile website and get the correct tags in place before the mobile site is released. As a result,  you prevent a data disaster due to the mobile site not recording any conversions.

| Segment 1 | Segment 2 |
|--- |--- |
| Hit container where Mobile Device Type equals Mobile Phone or Tablet | Everyone else |

{style="table-layout:fixed"}


## Use case 2: compare customers who use a certain feature to customers who don't

> *"You found customers who used your product comparison feature were 10% more likely to convert. You moved the product comparison to the top of the page, and grew orders by 4%!"*

A retail site optimization team wants to understand better the users who are interacting with a product comparison feature they recently released. They use the segment comparison panel to compare users who use the product comparison feature to everyone else on the site. They quickly identify several important differences, including the fact that these users are 10% more likely to purchase a product. The site optimization team decides to test the product comparison feature more prominently at the top of the page.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where custom event (price comparison tool) exists | Everyone else |

{style="table-layout:fixed"}


## Use case 3: compare news site visitors to other site section visitors

> *"You discovered that visitors to your news section were twice as likely to watch video ads, so you added more video options to that section. You experienced a 7% increase in video ads viewed!"*

A major media publishing company looks at ways to improve the content engagement for audiences in their news section. They create a segment of visitors who visit the News site section to understand the news audience better. They immediately find that these users are twice as likely to watch video ads than visitors to any other site section. The video team put together a recommended video section on their news side rail and achieves a 7% increase in video ads viewed.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where Site Section equals 'News' | Everyone Else |

{style="table-layout:fixed"}


## Use case 4: compare visitors from paid search to everyone else

> *"Visitors coming to your site from search engines were 3 times more likely to up-sell than everyone else. You upped your spend on specific keywords as a result and achieved a 56% increase in up-sells."*

A major B2B services company wants to understand the type of traffic that paid search keywords are bringing to their site. Paid search has not resulted in numerous conversions directly, and the marketing executive considers decreasing the budget for it. The marketing team creates a segment of visitors who come to the site via paid search and compare that segment to all other visitors using the segment comparison panel. They discover that although these visitors are not as likely to convert directly, they are 3 times more likely to up-sell on a previously purchased service. The marketing team focuses their budget on just the up-sell related keywords and sees a 56% increase in service up-sells.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where Referrer Type equals Paid Search | Everyone Else |

{style="table-layout:fixed"}


## Use case 5: compare Fitbit purchasers to everyone else

> *"You found that people buying Fitbits were 6 times more likely to get an 'out of stock' message than everyone else. So, you quickly ordered more Fitbits and avoided running out of stock!"*

**Scenario:** A major online retailer is interested in how one of the hottest holiday products - Fitbit - is selling and what makes Fitbit purchasers unique among other customers. The marketing team is able to select the Fitbit line item in their products report and quickly run a segment comparison analysis from the context menu. What they discover is that users purchasing Fitbits are 6 times more likely to get an "out of stock" message than any other customer. After further analysis, the marketing team is able to direct these visitors to their brick and mortar stores while they wait on their purchasing department to order more Fitbits to ship. As a result, the retailer avoids more "out of stock" messages, and is able to satisfy more of the holiday demand.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where Orders exist and custom dimension Brand equals FitBit | Everyone else |

{style="table-layout:fixed"}
