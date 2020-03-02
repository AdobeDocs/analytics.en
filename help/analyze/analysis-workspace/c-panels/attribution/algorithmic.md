---
description: null
title: Algorithmic Attribution
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
---

# Algorithmic Attribution

![Algorithmic](assets/algorithmic.png)

The Algorithmic [attribution model](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html#attribution-models) in Analysis Workspace differs from other models within Attribution IQ in that it uses statistical techniques to allocate credit across the dimension values in your report or Freeform Table. Like all other attribution models in Analysis Workspace, it can be used on any dimension or metric and supports unlimited segmentation and breakdowns and distributes 100% of conversions to the dimension(s) in the table (also known as “fractional” attribution).

The algorithm used for attribution is based on the Harsanyi Dividend from cooperative game theory. The Harsanyi dividend is a generalization of the Shapley value solution (named after Lloyd Shapley, a Nobel Laureate economist) to distributing credit among players in a game with unequal contributions to the outcome.

At a high level, the attribution calculation of the conversion credit for each touchpoint considers each of the marketing touchpoints within a lookback window as a coalition of players to which a surplus must be equitably distributed. Each coalition’s surplus distribution is determined according to the surplus that was previously created by each subcoalition (or previously participating dimension values) recursively. For more details, please see John Harsanyi’s and Lloyd Shapley’s original papers:

* Shapley, Lloyd S. "A value for n-person games." Contributions to the Theory of Games 2.28 (1953): 307-317.

* Harsanyi, John C. "A simplified bargaining model for the n-person cooperative game." International Economic Review 4.2 (1963): 194-220.

*Note: The outcome of Algorithmic attribution only differs from other models when multiple touchpoints exist within the given lookback window. For example, with only a single touchpoint, 100% of credit will be allotted to that value regardless of the attribution model selected.*