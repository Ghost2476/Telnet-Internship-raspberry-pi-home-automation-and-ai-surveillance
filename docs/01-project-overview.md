| Phase                  | Work completed                                                                | Evidence                          |
| ---------------------- | ----------------------------------------------------------------------------- | --------------------------------- |
| Hardware preparation   | Raspberry Pi 4, microSD, Ethernet, camera, sensors and output device prepared | Sanitised hardware image          |
| Headless setup         | Pi configured without a monitor through Ethernet                              | Terminal screenshot               |
| Home Assistant         | HAOS installed and accessed locally                                           | Dashboard screenshot              |
| SSH                    | Key-based access configured on port 22222                                     | Sanitised SSH screenshot          |
| Tailscale VPN          | Private remote network configured for authorised devices                      | Tailnet device screenshot         |
| Sensors                | Sensor/device entities integrated                                             | Entity screenshot                 |
| Temperature automation | Sensor value changes a light state/colour                                     | Trace and output screenshot       |
| MQTT                   | Broker communication configured                                               | MQTT integration screenshot       |
| Frigate                | RTSP camera connected and person detection enabled                            | Frigate screenshot                |
| Zones                  | place1 and place2 focus monitoring                                            | Zone screenshot                   |
| Notifications          | Pixel 6 and iPhone receive alerts                                             | Sanitised notification screenshot |
| Docker services        | CompreFace, PostgreSQL and Double Take deployed on Ghost                      | Docker screenshot                 |
| Face recognition       | Known/unknown identity decision flow tested                                   | Double Take result screenshot     |
| Threshold tuning       | 0.85 selected following false-positive test                                   | Before/after screenshot           |
| Documentation          | Sanitised repository and report created                                       | Repository screenshot             |

The Raspberry Pi was accessed through direct Ethernet and SSH because the setup was headless; Home Assistant OS administration used the ha command-line interface rather than standard sudo workflows.