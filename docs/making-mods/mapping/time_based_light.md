# Time-Based Lights

Parts tagged with `time_based_light` automatically turn on and off based on the in-game time of day. The on/off times are defined by the map's lamp settings.

When on, the part material is set to Neon. When off, it's set to Glass. All child Light, Beam, and ParticleEmitter instances are toggled along with it.

These lights can be shot out.

## Setup

1. Create a `BasePart` with a child Light (PointLight, SpotLight, etc.)
2. Add the `time_based_light` tag

You can also tag a `Model` — it will look for a child named `Light` or `light` inside it.

No attributes. Behavior is controlled by the map's lamp schedule set in the map properties.
