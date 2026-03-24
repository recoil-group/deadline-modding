# Lens Flare

Parts tagged with `lens_flare` create a lens flare effect on the player's screen when looking at the part. This is useful for bright light sources like the sun, spotlights, or lasers.

The lens flare also adds a dirt/bloom overlay on the screen and adjusts the camera's exposure compensation based on how directly you're looking at it.

## Setup

1. Create a `BasePart` positioned where the light source is
2. Add the `lens_flare` tag

## Attributes

All attributes are optional.

-   `flare_color` (Color3, white) — Color tint of the lens flare
-   `flare_strength` (number, 1) — Intensity of the flare effect
-   `flare_distance` (number, 1) — How far away the flare is visible. Higher values make it visible from further away
-   `flare_type` (string, "default") — Type of flare effect. Options:
    -   `"default"` / `"flash"` — Standard bright flash flare
    -   `"laser"` — Laser-style flare with stronger exposure/bloom
    -   `"test"` — Test flare for debugging
