---
title: Segment comparison use cases
description: Learn real-world use cases on how the segment comparison panel can be used to gain insight into marketing strategy.
keywords: Segment IQ
feature: Panels
role: User, Admin
exl-id: d7c02e5c-5313-4e12-86cb-d483644ccbc7
---
# Segment IQ use cases

The segment comparison panel is a widely-used feature in Analysis Workspace. Customers frequently discover new ways to drive insights with it. The following are several successful use cases.

## Use case 1: compare mobile vs. desktop implementations

> *"We compared hits from one site to another site and quickly found a number of tagging inconsistencies. This way, we avoided data problems before product release."*

A product manager in charge of a mobile website and a desktop website was tasked with making sure tags were consistent across mobile and desktop. To make sure he hadn't missed anything important, he used the segment comparison panel to compare hits coming from their mobile site to hits coming from their desktop site. He noticed that there were no checkout events on the mobile website and got the correct tags in place before the mobile site was released. As a result, the product manager avoided a data disaster due to the mobile site not having recorded any conversions.

| Segment 1 | Segment 2 |
|--- |--- |
| Hit container where Mobile Device Type equals Mobile Phone or Tablet | Everyone else |

## Use case 2: compare customers who use a certain feature to those who don't

> *"We found customers who used our product comparison feature were 10% more likely to convert. We moved it to the top of the page, and grew orders by 4%!"*

A retail site optimization team wanted to better understand the users who were interacting with a product comparison feature they had recently released. They used the segment comparison panel to compare users who used the product comparison feature to everyone else on the site. They quickly identified several important differences, including the fact that these users were 10% more likely to purchase a product. The site optimization team decided to test the product comparison feature more prominently at the top of the page.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where custom event (price comparison tool) exists | Everyone else |

## Use case 3: compare news site visitors to other site section visitors

> *"We discovered that visitors to our news section were twice as likely to watch video ads, so we added more video options to that section. We experienced a 7% increase in video ads viewed!"*

A major media publishing company looked at ways to improve the content engagement for audiences in their news section. They created a segment of visitors who had visited the News site section to better understand the news audience. They immediately found that these users were twice as likely to watch video ads than visitors to any other site section. The video team put together a recommended video section on their news side rail and achieved a 7% increase in video ads viewed.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where Site Section equals 'News' | Everyone Else |

## Use case 4: compare visitors from paid search to everyone else

> *"Visitors coming to our site from search engines were 3 times more likely to up-sell than everyone else. We upped our spend on specific keywords as a result and achieved a 56% increase in up-sells."*

A major B2B services company wanted to understand the type of traffic that paid search keywords were bringing to their site. Paid search had not resulted in a lot of conversions directly, and the marketing executive considered decreasing budget for it. The marketing team created a segment of visitors who came to the site via paid search and compared them to all other visitors using the segment comparison panel. They discovered that although these visitors were not as likely to convert directly, they were 3 times more likely to up-sell on a previously purchased service. The marketing team focused their budget on just the up-sell related keywords and saw a 56% increase in service up-sells.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where Referrer Type equals Paid Search | Everyone Else |

## Use case 5: compare Fitbit purchasers to everyone else

> *"We found that people buying Fitbits were 6 times more likely to get an 'out of stock' message than everyone else, so we quickly ordered more Fitbits and avoided running out of stock!"*

**Scenario:** A major online retailer was interested in how one of the hottest holiday products - Fitbit - was selling and what made Fitbit purchasers unique among other customers. The marketing team was able to simply right click on the “Fitbit” line item in their products report and quickly run a Segment IQ analysis. What they found was that users purchasing Fitbits were 6 times more likely to get an “out of stock” message than any other customer. After further analysis, the marketing team was able to direct these visitors to their brick and mortar stores while they waited on their purchasing department to order more Fitbits to ship. As a result, the retailer avoided more "out of stock" messages, and was able to satisfy more of the holiday demand.

| Segment 1 | Segment 2 |
|--- |--- |
| Visitor container where Orders exist and custom dimension Brand equals FitBit | Everyone else |
