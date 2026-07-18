## Secure service connectivity

Double Take connects to MQTT, Frigate and CompreFace using private configuration values. Its MQTT password, Frigate URL, CompreFace API key, local network addresses, and any Tailscale addresses are not published.

Tailscale permits authorised private access to the host and required services without making the Double Take interface or the CompreFace API public.