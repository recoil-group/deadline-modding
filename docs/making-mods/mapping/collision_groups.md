# Collision Groups

The game uses collision groups to control what objects can physically collide with each other. You can assign a collision group to any part by setting its `CollisionGroup` property in Studio.

## Custom Collision Groups

### walls

**Blocks players but not anything else.** Only collides with `player` and `humanoid_root_part`. Does not collide with `Default`, grenades, shells, ragdolls, or any other group.

Use this for invisible barriers that should stop players from going somewhere but let grenades and projectiles pass through.

## Common Use Cases

-   **Invisible player barrier (blocks players, not grenades):** Set the part's `CollisionGroup` to `walls`
