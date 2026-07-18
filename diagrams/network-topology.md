# Network Topology

```mermaid
flowchart LR
    Camera[IP camera] -->|RTSP on local network| Frigate[Frigate]
    Frigate -->|MQTT person events| Broker[MQTT broker]
    Broker --> HA[Home Assistant on Raspberry Pi]
    Broker --> DT[Double Take on Ghost]

    DT -->|Private service request| CF[CompreFace on Ghost]
    CF --> PG[(PostgreSQL on Ghost)]

    PC[Administration PC] -->|Ethernet / LAN| HA
    PC -->|SSH key, port 22222| HA

    Phone1[Pixel 6] -->|Companion App notifications| HA
    Phone2[iPhone] -->|Companion App notifications| HA

    Remote[Authorised remote user] -->|Encrypted managed path| Nabu[Nabu Casa]
    Nabu --> HA

    TS[Tailscale private VPN]
    TS --- HA
    TS --- PC
    TS --- Ghost[Ghost Ubuntu PC]
    TS --- Phone1
    TS --- Phone2
```

## Security boundary

Camera, MQTT, Frigate, Double Take, CompreFace, PostgreSQL, Docker, and SSH remain private services. Router port forwarding and public Funnel exposure are not used in the documented design.