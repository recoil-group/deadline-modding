# Kill Box

Parts tagged with `kill_box` act as death zones. Any alive player whose position is inside the part will be killed instantly.

## Usage

1. Create a `BasePart` in your map (any shape/size)
2. Add the `kill_box` tag via CollectionService or the Tags editor
3. The part will kill any player that enters it

The part can be transparent and non-collidable to act as an invisible death zone (e.g. out-of-bounds areas, fall pits).

## Luau alternative

If you need custom behavior (e.g. delayed kills, damage over time), you can use a script instead:

```luau
local function is_point_inside_part(point, part)
    local offset = part.CFrame:pointToObjectSpace(point)
    return math.abs(offset.X) <= part.Size.X / 2
        and math.abs(offset.Y) <= part.Size.Y / 2
        and math.abs(offset.Z) <= part.Size.Z / 2
end

time.heartbeat("check_killbox", function()
    for _, killbox in pairs(tags.get_tagged("kill_box")) do
        for _, player in pairs(get_players()) do
            local position = player.get_position()
            if not position then continue end

            if is_point_inside_part(position, killbox) then
                player.kill()
            end
        end
    end
end)
```
