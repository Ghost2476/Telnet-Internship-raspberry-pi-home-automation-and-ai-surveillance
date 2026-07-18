## Zones

The `place1` and `place2` zones define the relevant monitored areas. Zones reduce irrelevant detections and focus the project on the intended entrance or surveillance areas.

## Snapshots

Frigate saves event snapshots in the Home Assistant media area. The project uses the Frigate media location as the destination opened by notification taps.

## Privacy

Raw snapshots and recordings are not committed to Git. Screenshot evidence is cropped, blurred, or replaced by folder-structure views.
## Access control

Snapshots and recordings can reveal sensitive household information. They remain in private storage and are reviewed only through authorised Home Assistant access. Tailscale provides private remote transport when review occurs outside the home network.