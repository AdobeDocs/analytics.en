---
title: Custom events
description: The number of hits where a custom event exists.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
---
# Custom events

*This help page describes how custom events work as a metric. For information on how custom events work as an implementation variable, see [Events overview](/help/implement/vars/page-vars/events/events-overview.md) in the Implement user guide.*

Custom event metrics show the number of hits where a given custom event was set in an image request. These metrics are vital to many implementations, as they provide insight to events specific to each organization.

## How this metric is calculated

Custom events are calculated differently depending on their type. You can check an event's type under [Success events](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) in Report suite settings.

* **Counter events**: The default event setting. Most events are counter events. Counts the number of hits where the matching custom event `event1` - `event1000` exists in the [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
* **Numeric events**: Sums the numeric value assigned to the event in the `events` variable.
* **Currency events**: Applies currency conversion against that day's exchange rate, then sums the numeric value assigned to each hit in the `events` variable.

The number of available events depends on your organization's Analytics contract. Most organizations on non-legacy contracts have 1000 custom events available. Contact your organization's account manager if you are not sure how many custom events are available to you.

Adobe strongly recommends that you record how you use each event in your organization's [solution design document](/help/implement/prepare/solution-design.md).
