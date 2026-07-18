# Tailscale Configuration Example

## Purpose

Tailscale provides private remote access between authorised project devices.

## Devices

- Raspberry Pi / Home Assistant environment
- Ghost Ubuntu PC
- Personal administration PC
- Authorised Pixel 6
- Authorised iPhone

## Security rules

- Do not use router port forwarding.
- Do not enable public Funnel exposure for Home Assistant, camera, Frigate, Double Take, CompreFace, MQTT, PostgreSQL, or SSH.
- Keep all Tailscale authentication keys private.
- Use multi-factor authentication for the Tailscale account.
- Remove old or untrusted devices from the tailnet.
- Use restrictive ACLs if multiple users or device groups are added.

## Omitted private values

- Tailnet name
- Tailscale IP addresses
- MagicDNS names
- Device IDs
- Authentication keys
- API tokens
- Access-control policies that reveal personal device names