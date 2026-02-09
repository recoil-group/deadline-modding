# Light Tags

Tags you can add to BaseParts to make them behave as animated lights. The part material is set to Neon automatically. Child Light, Beam, and ParticleEmitter instances are toggled along with the part. If the parent of the tagged part is also Neon, it gets toggled too. All tagged lights play fluorescent toggle sounds and can be shot out.

## Tags

-   `flickering_light`
    -   Broken bulb effect. Rapidly flickers on and off at random intervals
-   `brief_flash_light`
    -   Mostly off. Briefly flashes on every few seconds
-   `equal_interval_light`
    -   Blinks on and off at steady equal intervals
    -   Attributes:
        -   `interval` (number) - Full on/off cycle duration in seconds. Defaults to 2
