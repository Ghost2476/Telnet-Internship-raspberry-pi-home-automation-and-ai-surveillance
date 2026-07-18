# Nabu Casa and Tailscale Remote Access

```mermaid
flowchart LR
    LocalUser[User on home Wi-Fi] --> LAN[Local network]
    LAN --> HA[Home Assistant]

    RemoteUser[Authorised remote user] --> NC[Nabu Casa / Home Assistant Cloud]
    NC -->|Encrypted managed access| HA

    PC[Authorised PC] --> TS[Tailscale private VPN]
    Phone[Authorised phone] --> TS
    Ghost[Ghost Ubuntu PC] --> TS
    TS -->|Encrypted private access| HA

    HA --> Media[Frigate media]
    Ghost --> AI[Double Take and CompreFace]
```

## Difference

Nabu Casa provides managed encrypted remote access to Home Assistant. Tailscale provides a private VPN between approved devices and can also provide private access to Ghost.