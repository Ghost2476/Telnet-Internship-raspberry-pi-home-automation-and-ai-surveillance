# Tailscale Private Remote-Access Flow

```mermaid
flowchart LR
    Admin[Authorised administration PC] --> TS[Tailscale encrypted private VPN]
    Phone[Authorised phone] --> TS
    Ghost[Ghost Ubuntu PC] --> TS
    HA[Home Assistant / Raspberry Pi] --> TS

    TS -->|Private access| HA
    TS -->|Private administration access| Ghost

    HA --> Frigate[Frigate media and events]
    Ghost --> DT[Double Take]
    Ghost --> CF[CompreFace]
```

## Security rule

Tailscale is used only for authorised private access. Tailscale Funnel or other public publishing mechanisms are not part of the project design.