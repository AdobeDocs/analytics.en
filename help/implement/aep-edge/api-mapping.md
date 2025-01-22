# Sending data to Adobe Analytics


## Standard dimensions

Use either the `interact` or `collect` endpoint

Can either send them directly in the `xdm` object to automatically map them, or send them anywhere in the payload, and use datastream mapping to map them to the correct XDM field.

## Standard metrics

## Streaming media dimensions

If you use the Media Edge API, you can use these endpoints to populate the following dimensions in Adobe Analytics.

| Dimension | Endpoint | Payload path | Additional details |
| --- | --- | --- | --- |
| Ad | | | |
| Ad length (variable) | | | |
| Ad loads | | | |
| Ad name (variable) | | | |
| Ad player name | | | |
| Ad pod | | | |
| Ad in pod position | | | |
| Advertiser | | | |
| Album | | | |
| Artist | | | |
| Average bitrate | | | |
| Author | | | |
| Bitrate changes | | | |
| Buffer events | | | |
| Campaign ID | | | |
| Chapter | | | |
| Content | `sessionStart` | `xdm.mediaCollection.sessionDetails.name` | |
| Content channel | `sessionStart`| `xdm.mediaCollection.sessionDetails.channel` | |
| Content length (variable) | `sessionStart` | `xdm.mediaCollection.sessionDetails.length` | |
| Content name (variable) | `sessionStart` | `xdm.mediaCollection.sessionDetails.friendlyName` | |
| Content player name | `sessionStart` | `xdm.mediaCollection.sessionDetails.playerName` | |
| Content segment | | | |
| Content type | `sessionStart` | `xdm.mediaCollection.sessionDetails.contentType` | |
| Day part | | | |
| Dropped frames | | | |
| Episode | | | |
| Errors | | | |
| External Error IDs | | | |
| Genre | | | |
| Label | | | |
| Media feed type | | | |
| Media path | | | |
| MVPD | | | |
| Network | | | |
| Player SDK error IDs | | | |
| Publisher | | | |
| Season | | | |
| Show | | | |
| Show type | | | |
| Station | | | |
| Stream type | | | |
| Total buffer duration | | | |
| Time to start | | | |

## Streaming media metrics

| Metric | Endpoint | Payload path | Additional details |
| --- | --- | --- | --- |
| Average minute audience | | | |
| Content completes | | | |
| Pause impacted streams | | | |
| Pause events | | | |
| Total pause duration | | | |
| Content starts | | | |
| 10% progress marker | | | |
| 25% progress marker | | | |
| 50% progress marker | | | |
| 75% progress marker | | | |
| 95% progress marker | | | |
| Content resumes | | | |
| Content segment views | | | |
| Media starts | | | |
| Content time spent | | | |
| Unique time played | | | |
| Ad completes | | | |
| Ad starts | | | |
| Ad time spent | | | |
| Media time spent | | | |
| Chapter completes | | | |
| Chapter starts | | | |
| Chapter time spent | | | |
| Streams impacted by closed captioning | | | |
| Closed captioning counts | | | |
| Closed captioning total duration | | | |
| Streams impacted by full screen | | | |
| Full screen counts | | | |
| Full screen total duration | | | |
| Streams impacted by in focus | | | |
| In focus counts | | | |
| In focus total duration | | | |
| Streams impacted by mute | | | |
| Mute counts | | | |
| Mute total duration | | | |
| Streams impacted by picture in picture | | | |
| Picture in picture counts | | | |
| Picture in picture total duration | | | |
| Average bitrate | | | |
| Bitrate change impacted streams | | | |
| Bitrate changes | | | |
| Buffer impacted streams | | | |
| Buffer events | | | |
| Total buffer duration | | | |
| Drops before start | | | |
| Dropped frames | | | |
| Dropped frame impacted streams | | | |
| Error impacted streams | | | |
| Error events | | | |
| Time to start | | | |
| Authorized | | | |
