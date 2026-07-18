# Face Recognition Decision Flow

```mermaid
flowchart TD
    Start[Frigate detects a person outside] --> Event[Frigate MQTT event]
    Event --> DT[Double Take processes event image]
    DT --> Face{Usable face detected?}
    Face -- No --> Unknown[Unknown-person warning]
    Face -- Yes --> CF[CompreFace compares enrolled subjects]
    CF --> Score{Accepted score at or above 0.85?}
    Score -- Yes --> Known[Known-person notification]
    Score -- No --> Unknown
    Known --> Media[Tap alert opens Frigate media]
    Unknown --> Media
```

## Interpretation

An unknown outcome is the safe fallback. It can mean that the person is not enrolled, that the face was unclear, or that the confidence score was below the accepted threshold.