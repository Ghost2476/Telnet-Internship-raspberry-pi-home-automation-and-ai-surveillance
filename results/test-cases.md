# Test Cases

> Replace every `<record>` entry with an observed result. Do not invent measurements.

| Test ID | Scenario | Expected result | Actual result | Evidence | Status |
|---|---|---|---|---|---|
| T01 | Home Assistant starts | Dashboard is available locally | `<record>` | Screenshot | Pass/Fail |
| T02 | SSH administration | Key-based SSH works on port 22222 | `<record>` | Sanitised terminal screenshot | Pass/Fail |
| T03 | Nabu Casa access | Home Assistant Cloud status is checked | `<record>` | Redacted status screenshot | Pass/Fail |
| T04 | Nabu Casa incident | Offline state, if observed, is documented honestly | `<record>` | Redacted screenshot/log | Pass/Fail |
| T05 | Tailscale connection | Approved devices show connected to tailnet | `<record>` | Redacted status screenshot | Pass/Fail |
| T06 | Remote HA through Tailscale | Authorised device opens Home Assistant outside local Wi-Fi | `<record>` | Redacted screenshot | Pass/Fail |
| T07 | Sensor update | Selected sensor entity updates correctly | `<record>` | Entity screenshot | Pass/Fail |
| T08 | Temperature automation | Smart bulb changes as configured | `<record>` | Trace/output screenshot | Pass/Fail |
| T09 | Frigate person event | Outside camera creates person event | `<record>` | Frigate event screenshot | Pass/Fail |
| T10 | Zone filtering | Relevant `place1` or `place2` event is processed | `<record>` | Zone/event screenshot | Pass/Fail |
| T11 | Known identity: Rayen | Accepted Rayen match triggers name alert | `<record>` | Double Take and phone screenshot | Pass/Fail |
| T12 | Known identity: Melek | Accepted Melek match triggers name alert | `<record>` | Double Take and phone screenshot | Pass/Fail |
| T13 | Unknown face | Unknown-person warning is sent | `<record>` | Phone screenshot | Pass/Fail |
| T14 | Glasses test | Incorrect 76.64% result is rejected at threshold 0.85 | `<record>` | Double Take screenshot | Pass/Fail |
| T15 | Notification navigation | Tapping alert opens Frigate media | `<record>` | Phone screenshot | Pass/Fail |
| T16 | Ghost Docker stack | Required containers are running | `<record>` | Sanitised Docker screenshot | Pass/Fail |
| T17 | Restart resilience | Required services reconnect after restart | `<record>` | Dashboard/log evidence | Pass/Fail |
| T18 | Ghost disk capacity | Storage is checked before continued Docker use | `<record>` | Sanitised disk output | Pass/Fail |

## Test evidence rules

- Do not publish real IP addresses, URLs, passwords, API keys, or device identifiers.
- Blur unconsenting faces, neighbours, number plates, addresses, and private home details.
- Use actual automation traces where possible.
- Record failed tests as failed; a failed test is useful evidence for troubleshooting.