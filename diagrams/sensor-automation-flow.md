# Sensor Automation Flow

```mermaid
flowchart TD
    Sensor[Sensor or smart-device entity] --> State[Home Assistant state update]
    State --> Trigger[Automation trigger]
    Trigger --> Check{Threshold or condition met?}
    Check -- No --> Wait[No action]
    Check -- Yes --> Action[Control smart output]
    Action --> Bulb[Smart bulb changes colour or state]
    Bulb --> Evidence[Automation trace and test record]
```

## Example

A temperature entity updates in Home Assistant. When the value reaches the configured threshold, an automation turns the selected smart bulb red as a visible warning.