# --------------------------------------------------------SENSORS------------------------------


## Automation: Temperature warning light

### Goal
Warn occupants when the measured temperature reaches the selected limit.

### Trigger
The temperature sensor state changes.

### Condition
Temperature is above the chosen threshold.

### Action
Set the smart bulb colour to red.

### Why
A colour-based alert is visible without opening the Home Assistant dashboard.

### Test
Change or simulate the sensor value above and below the threshold.

### Result
Record: passed / failed, date, and screenshot or automation trace.

### Limitations
The exact behaviour depends on sensor update frequency and bulb availability.






# --------------------------------------------------------FRIGATE + Camera ------------------------------


## Automation: Person detected in monitored zone

### Trigger
Frigate publishes a new person-detection event through MQTT.

### Conditions
- Object label is `person`
- Camera is the configured outside camera
- The person is in `place1` or `place2`

### Action
Home Assistant sends a push notification to both registered phones.

### Why
Zones avoid alerts for irrelevant movement outside the monitored entrance areas.

### Planned extension
Use face-recognition output to produce a known-person notification or an unknown/unrecognised-person alert.