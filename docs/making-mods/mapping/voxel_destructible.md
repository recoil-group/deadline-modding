# Voxel Destructible

Models or parts tagged with `voxel_destructible` can be blown apart by explosions. When an explosion hits, the object is converted into a voxel grid and the cells within the blast radius are removed, leaving a hole. The removed pieces fly off as debris.

## Setup

1. Create a `Model` or `BasePart`
2. Add the `voxel_destructible` tag

The object is not voxelized until it actually gets hit by an explosion, so there's no performance cost for placing many of them.

## Attributes

All attributes are optional.

-   `GridSize` (number) — Size of each voxel cell in studs. Smaller values = more detailed destruction but more parts. If not set, uses `voxel_default_grid_size`

## Shared Variables

These can be changed at runtime via the insitux console or mods.

-   `voxel_destruction_radius` (number, 10) — Radius in studs of the hole created by explosions
-   `voxel_bullet_destruction_radius` (number, 0) — Radius of destruction from bullet hits. Set to 0 by default (bullets don't destroy voxels). Increase to allow gunfire to chip away at objects
-   `voxel_default_grid_size` (number, 0.5) — Default voxel cell size in studs when the part doesn't have a `GridSize` attribute. Going lower than 0.5 causes heavy lag
-   `voxel_default_voronoi_density` (number, 0.01) — Controls how the flying debris chunks are split up. Higher values = more, smaller debris pieces
-   `voxel_throw_force` (number, 40) — How hard debris is launched away from the explosion. Higher values = debris flies further
