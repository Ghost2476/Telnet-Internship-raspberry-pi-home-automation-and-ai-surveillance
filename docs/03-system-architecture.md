```mermaid
    flowchart TB
    Admin[Personal PC] -->|Ethernet / local network| RPi[Raspberry Pi 4]
    Admin -->|SSH key authentication<br/>port 22222| RPi

    RPi --> HA[Home Assistant OS]
    HA --> Sensors[Sensors and smart devices]
    HA --> Rules[Automations]
    HA --> Broker[MQTT broker]
    HA --> Push[Mobile notifications]

    Camera[IP Camera] -->|RTSP stream| Frigate[Frigate]
    Frigate -->|Person events| Broker
    Frigate -->|Snapshots / recordings| Media[Home Assistant media]

    Ghost[Ghost Ubuntu PC] --> Docker[Docker / Docker Compose]
    Docker --> DT[Double Take]
    Docker --> CF[CompreFace]
    Docker --> PG[(PostgreSQL)]

    DT -->|Reads Frigate events| Broker
    DT -->|Face-comparison request| CF
    CF -->|Persistent service data| PG
    DT -->|Accepted match event| HA

    Nabu[Nabu Casa / Home Assistant Cloud]
    RemoteUser[Authorised phone or browser] -->|Encrypted remote connection| Nabu
    Nabu -->|Encrypted Home Assistant access| HA

    Tailscale[Tailscale private VPN]
    Tailscale --- RPi
    Tailscale --- Ghost
    Tailscale --- Admin
    Tailscale --- VPNPhones[Authorised phones]

    HA -->|Known or unknown notification| Push
    Push --> Pixel[Pixel 6]
    Push --> iPhone[iPhone]
    Push --> iPhone[iPhone]
```

## Architecture Explanation

    | Component            | Location                         | Role                                               | Why it is used                                    |
| -------------------- | -------------------------------- | -------------------------------------------------- | ------------------------------------------------- |
| Raspberry Pi 4, 2 GB | Local network                    | Runs Home Assistant OS                             | Low-power smart-home controller                   |
| Home Assistant       | Raspberry Pi                     | Integrations, entities, automations, notifications | Central decision and control layer                |
| Sensors/devices      | Local environment                | Provide input or physical output                   | Enable smart-home monitoring and automation       |
| MQTT broker          | Local/Home Assistant environment | Publish-subscribe message exchange                 | Decouples Frigate, Double Take and Home Assistant |
| IP camera            | Outside area                     | RTSP video source                                  | Provides video for monitoring                     |
| Frigate              | Deployed camera-AI service       | Person detection, events, snapshots                | Starts the AI workflow only when needed           |
| Ghost                | Ubuntu PC                        | Docker face-recognition host                       | More suitable than the Pi for AI containers       |
| Docker/Compose       | Ghost                            | Runs isolated services                             | Reproducible, manageable deployment               |
| CompreFace           | Docker on Ghost                  | Face-recognition API                               | Compares faces with enrolled subjects             |
| PostgreSQL           | Docker on Ghost                  | CompreFace persistent database                     | Keeps application/service data after restart      |
| Double Take          | Ghost/Docker service             | Connects Frigate, CompreFace and MQTT              | Manages recognition flow and match publishing     |
| Tailscale            | Pi, Ghost, authorised devices    | Private encrypted network                          | Secure remote access without port forwarding      |
| Pixel 6/iPhone       | Mobile devices                   | Receive notifications                              | User-facing alert output                          |

## Private remote-access plane
The Home Assistant Cloud remote-access connection was enabled during the project. At one stage, the instance appeared offline in Nabu Casa; the exact cause could not be confirmed remotely. This incident is documented in the project limitations and troubleshooting sections.


Tailscale creates a private encrypted network, called a tailnet, between authorised devices. In this project, the Raspberry Pi/Home Assistant host, Ghost processing host, personal administration device, and authorised phones are members of the same private network.

This allows remote administration and Home Assistant access without exposing local services directly to the public internet. The VPN is separate from the local Ethernet/LAN path and provides secure access when the user is away from the home network.