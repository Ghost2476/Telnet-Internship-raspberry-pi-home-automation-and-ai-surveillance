## MQTT security

The MQTT broker is treated as an internal service. It is not exposed to the public internet and is accessed only by authorised local services or, where required, authorised devices over the private Tailscale network.

MQTT usernames and passwords are stored privately and are excluded from version control. Raw MQTT payloads may contain camera names, event identifiers, or recognition data, so they are not published without sanitisation.