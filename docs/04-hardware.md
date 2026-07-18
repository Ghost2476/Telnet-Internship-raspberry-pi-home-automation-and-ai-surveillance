Hardware table
| Item | Purpose |
|---|---|
| Raspberry Pi 4, 2 GB RAM | Home Assistant host |
| microSD card | Home Assistant OS storage |
| Ethernet cable | Headless local setup and stable network access |
| IP camera | RTSP video stream for Frigate |
| Sensors | Environmental/device input for Home Assistant |
| Smart bulb or controlled light | Visual output of automation |
| Ghost Ubuntu PC | Docker host for CompreFace and Double Take |
| Pixel 6 | Notification recipient |
| iPhone | Notification recipient |
Software table
| Software | Purpose |
|---|---|
| Home Assistant OS | Smart-home central platform |
| Mosquitto / configured MQTT broker | MQTT message broker |
| Frigate | RTSP camera processing and person detection |
| Docker and Docker Compose | Container deployment on Ghost |
| CompreFace | Face-recognition service |
| PostgreSQL | CompreFace database service |
| Double Take | Frigate-to-recognition workflow and match publishing |
| Home Assistant Companion App | Mobile notifications |
| SSH | Headless administration |
| Tailscale |Secure private remote access        |
| WireGuard protocol | Encrypts point-to-point VPN traffic |