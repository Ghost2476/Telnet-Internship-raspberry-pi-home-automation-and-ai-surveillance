Functional

- Provide remote access to authorised devices through Tailscale VPN.
- Permit secure access to Home Assistant and approved project services over the tailnet.
- Keep camera processing and face-recognition services accessible only to intended local or VPN users.

Security/non-functional

- Do not use router port forwarding for Home Assistant, MQTT, Frigate, CompreFace, Double Take, or PostgreSQL.
- Do not expose the MQTT broker, CompreFace API, PostgreSQL database, or Docker management interface to the public internet.
- Enrol only authorised devices in the Tailscale tailnet.
- Protect the Tailscale account with multi-factor authentication where available.
- Revoke a lost, replaced, or untrusted device from the tailnet immediately.
- Do not store reusable Tailscale authentication keys in Git.