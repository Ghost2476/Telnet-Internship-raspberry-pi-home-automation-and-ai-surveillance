# Complete System Architecture

```mermaid
flowchart TB
    Admin[Personal PC] -->|Ethernet / local network| RPi[Raspberry Pi 4]
    Admin -->|SSH key authentication<br/>Port 22222| RPi

    RPi --> HA[Home Assistant OS]
    HA --> Sensors[Sensors and smart devices]
    HA --> Automations[Automation engine]
    HA --> MQTT[MQTT broker]
    HA --> Push[Mobile notifications]

    Camera[IP Camera] -->|RTSP stream| Frigate[Frigate]
    Frigate -->|Person events| MQTT
    Frigate -->|Snapshots / recordings| Media[Home Assistant media]

    Ghost[Ghost Ubuntu PC] --> Docker[Docker and Docker Compose]
    Docker --> DT[Double Take]
    Docker --> CF[CompreFace]
    Docker --> PG[(PostgreSQL)]

    DT -->|Reads Frigate events| MQTT
    DT -->|Face comparison request| CF
    CF -->|Persistent service data| PG
    DT -->|Accepted known match| HA

    RemoteUser[Authorised remote user] --> Nabu[Nabu Casa / Home Assistant Cloud]
    Nabu -->|Encrypted access to Home Assistant| HA

    Tailscale[Tailscale private VPN]
    Tailscale --- RPi
    Tailscale --- Ghost
    Tailscale --- Admin
    Tailscale --- MobileVPN[Authorised mobile devices]

    HA -->|Known or unknown notification| Push
    Push --> Pixel[Pixel 6]
    Push --> iPhone[iPhone]
```

## Design summary

The Raspberry Pi runs Home Assistant and coordinates automations. Ghost runs the Docker-based face-recognition services. Frigate produces person events, Double Take coordinates recognition through CompreFace, and Home Assistant sends the final notification.

Nabu Casa provides managed remote access to Home Assistant. Tailscale provides a separate private VPN network for authorised project devices.