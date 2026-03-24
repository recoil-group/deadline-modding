# Breaker Box

A breaker box is an interactable that controls a group of lights. When a player interacts with it, all lights inside the model toggle on or off. It plays a loud switch sound both locally and map-wide so all players can hear when someone flips the breaker.

## Setup

1. Create a `Model`
2. Add the `interactable` tag to it
3. Set the `interactable_type` attribute to `breaker_box`
4. Create an `Attachment` named `display_point` somewhere inside the model — this is the interaction prompt point

### Lights

The breaker box automatically finds all `Light` instances (PointLight, SpotLight, SurfaceLight) that are descendants of the model. Whatever settings you give them (Brightness, Color, Range, etc.) are kept — the breaker box only toggles them on and off.

When a light is toggled, the parent part's material switches between Neon (on) and Glass (off) to match.

#### Fluorescent lights

If a light's parent part has a `fluorescent` attribute set to `true`, the light will flicker randomly when toggled on (like a fluorescent tube warming up) and play fluorescent buzzing/clicking sounds. The buzzing loop plays continuously while the light is on.

The breaker box itself also plays an ambient electric hum sound near the display point.

### Lights can be shot out

Lights controlled by the breaker box can be destroyed by shooting the part they're attached to.

## Attributes

All attributes are optional.

-   `breaker_team` (string) — Which team can fully control (toggle on and off) the breaker. Accepted values:
    -   `"attacker"` — Only attackers can toggle freely. Defenders can only turn lights off
    -   `"defender"` — Only defenders can toggle freely. Attackers can only turn lights off
    -   `"both"` — Both teams can toggle freely
    -   Not set — Both teams can toggle freely (same as `"both"`)

    When a player from the wrong team interacts, they can only turn the lights off. They cannot turn them back on. If the lights are already off, nothing happens.

## Differences from Light Switch

The `light_switch` interactable type works similarly but is simpler — it just toggles lights on interact with no team restrictions, no map-wide sound, and no ambient hum. Use `breaker_box` when you want team-gated control or the full audio treatment.
