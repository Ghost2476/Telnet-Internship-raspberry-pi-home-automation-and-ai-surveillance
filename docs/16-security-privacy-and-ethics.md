# Security, Privacy, and Ethics

## Security design

The project uses layered security:

1. Local network segmentation and Ethernet-based initial access.
2. SSH key-based administration on port 22222.
3. Private MQTT credentials for application messaging.
4. Docker service separation on Ghost.
5. Private PostgreSQL persistence for CompreFace.
6. Tailscale VPN for encrypted remote access between authorised devices.
7. No public router port forwarding for Home Assistant, MQTT, Frigate, Double Take, CompreFace, PostgreSQL, or SSH.
8. No Tailscale Funnel/public proxy exposure for camera or biometric services.

## Why Tailscale was used

Tailscale was selected because it creates a private encrypted mesh network between authorised devices. It provides remote access without exposing internal services directly to the public internet.

The VPN enables the administrator and authorised phones to reach Home Assistant and relevant internal services while away from home Wi-Fi. It is safer than opening router ports because access is restricted to authenticated devices in the private tailnet.

## Tailscale security controls

- Only authorised devices are enrolled.
- The Tailscale account should use a strong unique password and multi-factor authentication.
- Device access is reviewed regularly.
- Lost, replaced or untrusted devices are removed immediately.
- Reusable authentication keys are not stored in Git.
- Tailnet names, device names, Tailscale IP addresses, MagicDNS names, access-control policies and administration URLs are not published.
- Public Funnel exposure is disabled/not used.
- Tailscale is not a replacement for strong passwords, updated software or secure Home Assistant configuration.

## Credential protection

The repository excludes RTSP URLs, camera credentials, MQTT passwords, PostgreSQL credentials, Docker environment files, CompreFace API keys, Double Take configuration secrets, Home Assistant tokens, SSH private keys, Tailscale auth keys, real IP addresses, and cloud URLs.

## Biometric and camera data

Face-reference images, face-recognition results, snapshots, recordings and identity names are sensitive personal data. Raw data is not uploaded to the public repository.

## Consent and fairness

Known individuals whose faces are enrolled should be informed and should consent to the use of their reference images. Recognition results are probabilistic and must not be used as the sole basis for security, disciplinary, or legal decisions.

## Meaning of unknown

An unknown result means that the system did not return an accepted known match. It may represent an unrecognised visitor, an enrolled person under poor lighting, an obscured face, glasses, poor camera angle, motion blur, or a detector error. It does not prove malicious intent.

## Data retention

Snapshots, recordings, face-reference images, Docker volumes and database backups must be protected and retained only for as long as necessary. Future work should automate retention and deletion.