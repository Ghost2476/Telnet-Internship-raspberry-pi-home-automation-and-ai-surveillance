# Network and Protocols

## Ethernet

Ethernet was used during the headless Raspberry Pi setup. It provided a stable direct local connection while no monitor was available and allowed access to Home Assistant and SSH administration.

## HTTP and HTTPS

Home Assistant is accessed through a browser. Local access uses the Home Assistant web interface, normally on port 8123. Remote access through the private Tailscale network is encrypted by the VPN tunnel; any public exposure is avoided.

## SSH

SSH provides command-line administration of the Raspberry Pi/Home Assistant host. Key-based authentication was configured instead of password authentication. SSH access uses port 22222. The private key is never committed to the repository.
# Nabu Casa / Home Assistant Cloud Example

Home Assistant Cloud, provided by Nabu Casa, was used to provide encrypted remote access to the Home Assistant dashboard and Home Assistant Companion App.
Simple encrypted remote Home Assistant access without port forwarding

## Tailscale VPN

Tailscale creates a private mesh VPN between authorised devices. It uses WireGuard-based encrypted connections and allows the project services to be reached remotely without router port forwarding.

Tailscale was installed/configured on the required project devices, including the Home Assistant/Raspberry Pi environment, Ghost Ubuntu PC, and authorised user devices. Only devices signed into the project tailnet can access Tailscale addresses and services.

## MQTT

MQTT is a lightweight publish/subscribe protocol. Frigate publishes person-detection events, Double Take uses relevant event information for face processing, and Home Assistant uses event and match information in automations.

## RTSP

RTSP transports the IP camera video stream to Frigate.

## Docker networking

Docker on Ghost creates an internal network for the containerised services. CompreFace and PostgreSQL communicate within Docker, while Double Take communicates with the required local or Tailscale-reachable services. Only required interfaces are exposed.

## Face-recognition communication

Double Take receives Frigate-related information, sends face images to CompreFace, and receives a candidate identity with a confidence score. Accepted matches are made available to Home Assistant for known-person notifications.