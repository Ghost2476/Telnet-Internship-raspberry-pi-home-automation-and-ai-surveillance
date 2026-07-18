# Home Assistant Cloud / Nabu Casa Example

## Purpose

Home Assistant Cloud, provided by Nabu Casa, provides encrypted remote access to the Home Assistant dashboard and the Home Assistant Companion App.

## Why it was used

- Enables remote Home Assistant access without ordinary router port forwarding
- Provides a managed encrypted remote URL
- Supports access when the phone is outside the home Wi-Fi network
- Provides a simple remote-access method focused on Home Assistant

## Project use

Nabu Casa remote access was enabled/configured during the project.

At one stage, Home Assistant Cloud displayed the instance as offline. The exact cause was not confirmed remotely. This is recorded as an incident and limitation, not hidden as a failure.

Tailscale was documented as a separate private VPN route for authorised devices and as a resilience option.

## Security rules

- Do not publish the Nabu Casa remote URL.
- Do not publish cloud account email addresses.
- Do not publish account tokens, QR codes, or device-registration information.
- Use a strong Home Assistant account password.
- Enable multi-factor authentication where available.
- Do not use normal router port forwarding for Home Assistant.
- Do not treat Nabu Casa as direct remote access to Ghost, Docker, PostgreSQL, CompreFace, or Double Take.

## Relationship with Tailscale

- Nabu Casa provides managed encrypted remote access to Home Assistant.
- Tailscale provides a private VPN between authorised devices.
- The two services have different roles and may coexist.