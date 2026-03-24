# Background Sound Parts

Parts tagged with `bg_sound_part` play a looping background sound when the camera is inside them. The sound fades in smoothly when you enter the part's volume and fades out when you leave. This is useful for ambient areas like indoor reverb zones, outdoor wind areas, or specific rooms.

It's recommended to apply this tag to the same parts you use as reverb zones, so the ambient sound matches the reverb area.

## Setup

1. Create a `BasePart` that covers the area you want sound in (a large invisible block works well)
2. Add the `bg_sound_part` tag
3. Set the `sound_id` attribute (see below)

The part should be invisible and non-collidable — it's only used as a volume trigger.

## Attributes

-   `sound_id` (string, required) — The sound to play. You can use either a name from the list below, or a raw Roblox asset ID (like `rbxassetid://123456`)
-   `volume` (number, 1) — Target volume when the camera is inside the part. Defaults to 1

## Available Sounds

These are the built-in sound names you can use for `sound_id`:

### Map-specific ambience
-   `ambience_afghanistan`
-   `ambience_backrooms`
-   `ambience_crossroads_sniperscape`
-   `ambience_hong_kong`
-   `ambience_shipment`
-   `ambience_tel_aviv`

### General ambience
-   `buzzing` — Electrical buzzing, good for indoor industrial areas
-   `general_distant_firefight` — Distant gunfire ambience
-   `general_intense_firefight` — Closer, more intense gunfire
-   `general_leaf_rustling` — Foliage rustling
-   `general_wind` — General outdoor wind
-   `general_wind_low` — Softer wind
-   `old_gunshots` — Legacy distant gunshots
-   `old_shipment_wind` — Legacy shipment map wind
-   `old_wind` — Legacy wind
-   `pearl_of_the_orient_toolbox_wind` — Specific wind loop
