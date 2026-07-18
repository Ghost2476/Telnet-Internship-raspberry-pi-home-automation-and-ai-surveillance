# Remote Access: SSH, Nabu Casa, and Tailscale

## Purpose

The project required secure access to Home Assistant and supporting services while a monitor was not permanently connected to the Raspberry Pi and while the administrator was away from the local network.

## Local headless access

The Raspberry Pi was initially accessed through Ethernet because no monitor was available. The administration computer reached Home Assistant locally and used SSH for command-line administration.

## SSH administration

SSH key-based authentication was configured for administration on port 22222.

The private SSH key remains only on the authorised administration device and is excluded from version control. Home Assistant OS uses the `ha` command-line interface for applicable host administration tasks instead of a conventional `sudo` workflow.

## Home Assistant Cloud / Nabu Casa

Home Assistant Cloud, provided by Nabu Casa, was used to provide encrypted remote access to the Home Assistant dashboard and Companion App.

This method does not require normal router port forwarding. It is designed for remote access to Home Assistant itself, not as a general private network for every project service.

## Nabu Casa incident

During the project, Home Assistant Cloud later displayed the Home Assistant instance as offline. The exact reason could not be confirmed remotely at that time.

This issue is documented as a project incident and limitation. It demonstrates why a secondary private remote-access method was valuable.

## Tailscale VPN

Tailscale was used as a private VPN between authorised devices. It provided encrypted remote connectivity to the Home Assistant environment and Ghost where configured.

Tailscale was not used to publicly publish services. Tailscale Funnel was not enabled for this project.

## Why both methods were used

Nabu Casa offered a simple managed remote path for Home Assistant and Companion App use.

Tailscale offered a private device-to-device path for authorised systems, including the Ghost face-recognition host. It also provided resilience if Home Assistant Cloud access was unavailable.

## Security controls

- No router port forwarding was used for Home Assistant, SSH, MQTT, Frigate, Double Take, CompreFace, PostgreSQL, or Docker.
- SSH uses key-based authentication.
- Only approved devices are enrolled in Tailscale.
- Tailscale authentication keys and API tokens are private.
- The Nabu Casa remote URL and cloud credentials are private.
- Multi-factor authentication should be enabled for Home Assistant and Tailscale accounts.
- Lost, replaced, or untrusted VPN devices must be removed immediately.
- Tailscale Funnel/public exposure was not used.