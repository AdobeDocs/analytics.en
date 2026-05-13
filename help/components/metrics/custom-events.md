---
title: Custom events
description: The number of hits where a custom event exists.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
TQID: https://experienceleague.adobe.com/1D8ONiUuG3T6DqM7HygbBbf0Y4ja5ej1Hfy8-hKo0yg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Custom events

*This help page describes how custom events work as a metric. For information on how custom events work as an implementation variable, see [Events overview](/help/implement/vars/page-vars/events/events-overview.md) in the Implement user guide.*

Custom event [metrics](overview.md) show the number of hits where a given custom event was set in an image request. These metrics are vital to many implementations, as they provide insight to events specific to each organization.

## How this metric is calculated

Custom events are calculated differently depending on their type. You can check an event's type under [Success events](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) in Report suite settings.

* **Counter events**: The default event setting. Most events are counter events. Counts the number of hits where the matching custom event `event1` - `event1000` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
* **Numeric events**: Sums the numeric value assigned to the event in the `events` variable.
* **Currency events**: Applies currency conversion against that day's exchange rate, then sums the numeric value assigned to each hit in the `events` variable.

The number of available events depends on your organization's Analytics contract. Most organizations on non-legacy contracts have 1000 custom events available. Contact your Adobe Account Team if you are not sure how many custom events are available to you.

Adobe strongly recommends that you record how you use each event in your organization's [solution design document](/help/implement/prepare/solution-design.md).
