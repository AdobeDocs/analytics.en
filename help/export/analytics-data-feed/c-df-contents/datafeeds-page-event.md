---
description: Lookup table to determine the type of a hit based on the page_event value.
keywords: Data Feed;page;event;page_event;post_page_event
title: Page Event Lookup
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
---
# Page Event Lookup

Lookup table to determine the type of a hit based on the page_event value.

| Hit type | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Page views | 0: All page view calls and `trackState` calls from mobile SDK's | Same value as `page_event` |
| Link tracking | 10: Custom links and `trackAction` calls in mobile SDK's<br>11: Download links<br>12: Exit links | 100: Custom links and `trackAction` calls in mobile SDK's<br>101: Download links<br>102: Exit links |
| Milestone video | 31: Media start<br>32: Media updates (no other variable processing)<br>33: Media updates (with other variables) | 76: Media start<br>77: Media updates (no other variable processing)<br>78: Media updates (with other variables) |
| Heartbeat video | 50: Media stream start (non-Primetime)<br>51: Media stream close (non-Primetime)<br>52: Media stream scrubbing (non-Primetime)<br>53: Media stream keep alive (non-Primetime)<br>54: Media stream ad start (non-Primetime)<br>55: Media stream ad close (non-Primetime)<br>56: Media stream ad scrubbing (non-Primetime)<br>60: Primetime media stream start<br>61: Primetime media stream close<br>62: Primetime media stream scrubbing<br>63: Primetime media stream keep alive<br>64: Primetime media stream ad start<br>65: Primetime media stream ad close<br>66: Primetime media stream ad scrubbing | Same value as `page_event` |
| Survey | 40: Any call generated from Survey | 80: Any call generated from Survey |
| Analytics for Target | 70: Hit includes Target activity data | Same value as `page_event` |
