## Tailscale and Ghost

Ghost was joined to the private Tailscale network so it could communicate securely with the authorised project environment when local-network access was not sufficient.

Tailscale was used for administration and required service connectivity. CompreFace, PostgreSQL, and Docker management were not exposed to the public internet.

## Container network exposure

PostgreSQL is a database dependency for CompreFace and should be available only to the required Docker services. It must not be published publicly.

CompreFace and Double Take interfaces should be restricted to local Docker networking, the local LAN where necessary, or the private Tailscale network. Public port forwarding is not used.

## Docker and storage security

Docker volumes provide persistence for CompreFace and PostgreSQL. These volumes can contain sensitive application and biometric-related data, so they are not exported to Git or public storage.

Ghost storage must be monitored because the root filesystem became nearly full during the project. Docker images, container logs, database volumes, and media can consume substantial disk capacity.