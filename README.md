# Raspberry Pi Home Automation and AI Surveillance

> Internship project documenting the design, implementation, testing, and evaluation of a Raspberry Pi based smart-home and AI camera system.

## Project status

**Status:** In development

The system currently supports Home Assistant based automation, MQTT communication, Frigate person detection, monitored zones, saved snapshots, and phone notifications. Known-versus-unknown face recognition is planned and will be tested later.

## Objectives

The project aims to build a local smart-home prototype that:

- Uses a Raspberry Pi as the central host
- Runs Home Assistant for device integration and automation
- Connects sensors and smart-home devices
- Uses MQTT for lightweight device and event communication
- Sends notifications to connected mobile phones
- Connects an IP camera to Frigate through RTSP
- Detects people in defined monitored zones: `place1` and `place2`
- Saves relevant snapshots
- Extends the system with known / unknown-or-unrecognised person notifications



## Current features

- Raspberry Pi based Home Assistant installation
- Local network and SSH administration
- Sensor integration and automation development
- MQTT message broker configuration
- Home Assistant mobile notification testing
- IP camera RTSP stream connected to Frigate
- Person detection and snapshot storage
- Zone-based monitoring using `place1` and `place2`
- Notifications sent to multiple phones
- Planned face-recognition classification for known and unknown/unrecognised people

## Technology stack

| Component | Role |
|---|---|
| Raspberry Pi 4 | Local host for the smart-home system |
| Home Assistant OS | Central home-automation platform |
| MQTT | Publish/subscribe communication between components |
| Frigate | Local NVR and AI-based person detection |
| RTSP | IP camera video-stream protocol |
| SSH | Secure command-line administration |
| Home Assistant Companion App | Mobile push notifications |

## Documentation

- [Project overview](docs/01-project-overview.md)
- [System architecture](docs/03-system-architecture.md)
- [Network and protocols](docs/05-network-and-protocols.md)
- [Home Assistant installation](docs/06-raspberry-pi-and-home-assistant-installation.md)
- [Sensors and integrations](docs/08-sensors-and-integrations.md)
- [Automations and notifications](docs/09-automations-and-notifications.md)
- [MQTT communication](docs/10-mqtt-communication.md)
- [Frigate camera AI](docs/11-frigate-camera-ai.md)
- [Face-recognition plan and results](docs/13-face-recognition-plan-and-results.md)
- [Testing and measurements](docs/14-testing-and-measurements.md)
- [Problems, solutions, and limitations](docs/15-problems-solutions-and-limitations.md)

## Privacy and security

This repository contains **sanitised examples only**.

It does not contain:

- Camera usernames, passwords, or RTSP URLs
- MQTT passwords
- SSH private keys
- Home Assistant Cloud URLs or access tokens
- Real local IP addresses
- Family snapshots, recordings, or face-recognition training images
- Home Assistant databases or `.storage` files

## Repository structure

```text
.
├── config-examples/   # Sanitised configuration examples
├── diagrams/          # Mermaid architecture and workflow diagrams
├── docs/              # Technical documentation
├── images/            # Sanitised screenshots and diagrams only
├── results/           # Test tables and measured results
└── reports/           # Final internship report
```

## Limitations

- An unknown or unrecognised result does not prove that a person is an intruder.
- Face recognition depends on camera angle, light, face visibility, and image quality.
- The Raspberry Pi has limited processing resources, so AI features must be tested carefully.
- Remote access depends on network connectivity and the configured remote-access service.

