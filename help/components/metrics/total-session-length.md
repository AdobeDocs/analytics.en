---
title: Total session length
description: The length of the previous mobile session in seconds.
---

# Total session length

The 'Total session length' metric, also known as 'Previous session length', is a metric exclusive to report suites that use the mobile SDK. It shows the amount of time the visitor spent during their last session of the mobile app.

## How this metric is calculated

The mobile SDK records the amount of time spent in an app for a given session. Time only increases when the app is active; it does not increase when the app is in the background.

When a session concludes, the amount of time spent is stored on the device. When the mobile app is next opened, it sends its previous session length to Adobe data collection servers.

For example, a visitor installs an example app, launches it, uses it for two minutes, then closes the app. The next day, the visitor launches the app again. Total session length for the second session is `120 seconds`.
