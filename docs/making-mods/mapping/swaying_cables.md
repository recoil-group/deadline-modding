# Swaying Cables

Parts tagged with `swaying_cable` generate a procedural hanging cable between two attachment points. The cable sways with Perlin noise and reacts to `Workspace.GlobalWind`.

## Setup

1. Create a `BasePart` and add the `swaying_cable` tag
2. Add two child `Attachment` instances named `start` and `target`
3. The cable will be drawn between the two attachments' world positions

The part's `Color` is used for the cable segments. Segments are cylindrical, anchored, non-collidable, Metal material, with shadows disabled.

## Attributes

All attributes are optional. Defaults are shown in parentheses.

-   `segments` (number, 12) — Number of segments the cable is divided into. More segments = smoother curve but more parts
-   `thickness` (number, 0.1) — Diameter of each cable segment in studs
-   `sag` (number, 2) — How far the cable droops at its midpoint in studs
-   `wind_influence` (number, 1) — Multiplier for how much `Workspace.GlobalWind` affects the cable
-   `noise_speed` (number, 1.6) — Speed of the Perlin noise animation
-   `noise_force` (number, 5) — Strength of the Perlin noise displacement
-   `neighbor_pull` (number, 0.8) — How strongly adjacent cable vertices pull toward each other. Higher values make the cable more rigid
