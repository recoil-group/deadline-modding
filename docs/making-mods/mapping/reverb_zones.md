# Reverb Zones

Reverb zones are invisible parts placed in `Workspace.ignore.reverb` that control how sounds (especially gunshots) echo. When the camera enters a reverb zone, the game applies a reverb preset and optionally muffles outdoor background sounds.

## Setup

1. Create a `BasePart` in `Workspace.ignore.reverb`
2. Name it using the format: `{priority} {gunshot_layer} {reverb_preset}`

### Naming format

The part name has 3 space-separated parts:

1. **Priority** (number) — When the camera is inside multiple overlapping zones, the highest priority wins. Range 0–10
2. **Gunshot layer** — Which gunshot tail/echo samples to use (see below)
3. **Reverb preset** — Which Roblox reverb preset to apply (see below)

### Examples

-   `5 indoor_small indoor_small` — Priority 5, uses `indoor_small` gunshot layer and reverb preset, muffles outdoor sounds (name contains "indoor")
-   `3 field default` — Priority 3, uses `field` gunshot layer and `default` reverb, no muffling
-   `7 indoor_large indoor_large` — Priority 7, large indoor gunshot layer and reverb, muffles outdoor sounds

## Reverb Presets (Roblox ReverbSoundEffect)

The preset name in the part name must match a child of `SoundService.presets`. These control the Roblox ReverbSoundEffect applied to sound groups (DecayTime, Density, Diffusion, DryLevel, WetLevel):

-   `default` — Standard outdoor reverb, minimal echo
-   `indoor_small` — Small enclosed room, tight reverb
-   `indoor_large` — Large indoor space (warehouse, hangar), longer echo
-   `afghan_bg` — Afghanistan map outdoor ambience reverb
-   `shipment_bg` — Shipment map reverb

## Gunshot Layer Presets

Reverb zones also determine which gunshot tail/echo sound layers play. These are separate from the Roblox reverb presets — they select different recorded gunshot samples for each environment:

-   `field` — Open field, used when outside any zone
-   `forest` — Wooded area
-   `urban` — City streets, large urban area
-   `urban_small` — Tight alley or small urban space
-   `indoor_large` — Large indoor space
-   `indoor_small` — Small room

If the player is not inside any reverb zone, gunshots default to `field`.
