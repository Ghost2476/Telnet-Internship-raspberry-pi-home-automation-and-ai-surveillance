| Test ID | Scenario                     | Expected result                                     | Actual result        | Evidence                    | Status    |
| ------- | ---------------------------- | --------------------------------------------------- | -------------------- | --------------------------- | --------- |
| T01     | Home Assistant starts        | Dashboard loads locally                             | Record actual result | Screenshot                  | Pass/Fail |
| T02     | SSH local administration     | Key-based SSH works on port 22222                   | Record actual result | Terminal screenshot         | Pass/Fail |
| T03     | Tailscale connection         | Pi, Ghost and authorised device show connected      | Record actual result | Sanitised status screenshot | Pass/Fail |
| T04     | Remote Home Assistant access | HA opens on authorised device outside home Wi-Fi    | Record actual result | Sanitised screenshot        | Pass/Fail |
| T05     | Sensor state update          | Entity updates correctly                            | Record actual result | Screenshot                  | Pass/Fail |
| T06     | Temperature automation       | Light performs expected action                      | Record actual result | Trace/output                | Pass/Fail |
| T07     | Frigate person event         | Person event is created                             | Record actual result | Frigate event               | Pass/Fail |
| T08     | Zone relevance               | Relevant zone event is processed                    | Record actual result | Frigate evidence            | Pass/Fail |
| T09     | Known identity Rayen         | Name notification arrives                           | Record actual result | Match + phone               | Pass/Fail |
| T10     | Known identity Melek         | Name notification arrives                           | Record actual result | Match + phone               | Pass/Fail |
| T11     | Unknown person               | Unknown warning arrives                             | Record actual result | Phone alert                 | Pass/Fail |
| T12     | Glasses false-positive case  | No accepted incorrect match at 0.85                 | Record actual result | Double Take evidence        | Pass/Fail |
| T13     | Notification navigation      | Frigate media opens after tap                       | Record actual result | Phone screenshot            | Pass/Fail |
| T14     | Remote media review          | Frigate media opens through Tailscale away from LAN | Record actual result | Phone screenshot            | Pass/Fail |
| T15     | Restart test                 | Services reconnect after restart                    | Record actual result | Dashboard/logs              | Pass/Fail |