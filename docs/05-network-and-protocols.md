# Network and Protocols

## Ethernet

Ethernet connected the PC and Raspberry Pi during setup. It provided a stable local connection when a monitor was unavailable and enabled access to the Home Assistant web interface and SSH administration.

## HTTP / HTTPS

Home Assistant exposes a web interface on port 8123. HTTP is used on the local network. HTTPS is used for secure remote access through Home Assistant Cloud when the Cloud tunnel is connected.

## SSH

Secure Shell (SSH) was used for command-line administration of the Home Assistant host. Key-based authentication was used instead of a password. The private key is not stored in this repository.

## MQTT

MQTT is a lightweight publish/subscribe messaging protocol. The MQTT broker receives messages from publishers and delivers them to subscribers. Frigate publishes detection events; Home Assistant subscribes to those events and runs automations.

## RTSP

Real-Time Streaming Protocol (RTSP) provides the IP camera video stream to Frigate. Frigate analyses the stream locally for motion and objects such as persons.