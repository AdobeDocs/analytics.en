---
title: Algorithmic attribution
description: Details on the algorithmic attribution model.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
---
# Algorithmic attribution

The Algorithmic [attribution model](models.md) in Analysis Workspace differs from other models in that it uses statistical techniques to allocate credit across the dimension items in your report or freeform table. Like all other attribution models in Analysis Workspace, it can be used on any dimension or metric and supports unlimited segmentation and breakdowns and distributes 100% of conversions to the dimension(s) in the table (also known as "fractional" attribution).

The algorithm used for attribution is based on the Harsanyi Dividend from cooperative game theory. The Harsanyi dividend is a generalization of the Shapley value solution (named after Lloyd Shapley, a Nobel Laureate economist) to distributing credit among players in a game with unequal contributions to the outcome.

At a high level, the attribution calculation of the conversion credit for each touchpoint considers each of the marketing touchpoints within a lookback window as a coalition of players to which a surplus must be equitably distributed. Each coalition’s surplus distribution is determined according to the surplus that was previously created by each subcoalition (or previously participating dimension items) recursively. For more details, see John Harsanyi’s and Lloyd Shapley’s original papers:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>The outcome of Algorithmic attribution only differs from other models when multiple touchpoints exist within the given lookback window. Conversions with a single touchpoint receive 100% credit regardless of attribution model.
