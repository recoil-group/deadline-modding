# Swaying Cables

Parts tagged with `swaying_cable` generate a procedural hanging cable between two attachment points. The cable sways with Perlin noise and reacts to wind. It uses verlet integration (a physics chain), so the cable behaves like a real hanging rope.

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
-   `wind_influence` (number, 1) — Multiplier for how much wind affects the cable
-   `noise_speed` (number, 1.6) — Speed of the Perlin noise animation
-   `noise_force` (number, 5) — Strength of the Perlin noise displacement
-   `damping` (number, 0.98) — Velocity damping per frame, between 0 and 1. Lower values make the cable lose energy faster (less swinging). Higher values make it swing for longer
-   `constraint_iterations` (number, 4) — How many times the distance solver runs per frame. More iterations = stiffer, more rigid cable. Fewer = looser, more elastic
