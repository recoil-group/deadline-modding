# Index

Scripts are written in barebones Luau with Deadline-only globals (game is replaced with game modules). Modfiles are developed in Roblox Studio, so download that if you want to make maps

## How-to

To make mods in Deadline you need the deadline plugin([download here](https://github.com/recoil-group/deadline-modfile-plugin/releases/download/0.23.0-dev-3-5/Plugin.rbxmx)) and an example map([download here](https://recoil-group.github.io/deadline-modding/example/source/map_template_map.rbxl)).

## Setup

-   Open roblox studio
-   Click on any of the presets below ![](img/1.png)
-   Click on the PLUGINS tab ![](img/2.png)
-   Then click on Plugins folder ![](img/3.png)
-   Open your downloads folder and drag the plugin into the newly opened folder ![](img/4.png)
-   Now close the plugin folder and roblox studio
-   Right click on the example map file and select “Open with": ![](img/5.png)
-   Select always, now the example map is open.
-   Doubleclick “Workspace” on the right of the screen ![](img/6.png)
-   Click on “Camera” once
-   In the properties explorer scroll down
-   Click on “CameraType” and select “Custom” ![](img/7.png)
-   Setup is done

## Modifying the map

Note: The map will not work if you don’t include the info folder

Any new blocks or map pieces you want to add need to be moved into the “map” folder. Remember you can’t export regular meshes, only special ones. For more info on special meshes look [here](https://create.roblox.com/docs/reference/engine/classes/SpecialMesh). Other things you can't export include: terrain, custom material variants, SurfaceAppearance, Particle Emitters. ![](img/8.png)

Under the ignore folder you can find various other folders. By placing parts into defender_spawn>default (Syno) or attacker_spawn>default (Anto) players will spawn on a random point of those parts.

![](img/9.png)

To create parts that allow bullets to pass through but not players create a new folder under ignore called “map_ignore” and move the parts in there.

![](img/10.png)

The restricted folder contains spawn protection, if a player is inside those parts they won’t get killed.

![](img/11.png)

The gamemode folder houses the blocks that determine where the points are located for KOTH and domination. The capture points’ names start from zero, you can have any amount.

![](img/12.png)

Parts under Slowzones are supposed to be water and bushes, this is what their properties should look like

Bushes:

![](img/12.png)

Water:

![](img/13.png)

If you want to disable collision for parts disable canCollide **AND** canQuery, if you only disable the former your game will break

![](img/14.png)

## Using the plugin

-   Open the plugins tab again (see Setup step 3)
-   Click on the Deadline Modding plugin ![](img/15.png)
-   This will appear ![](img/16.png)
-   Select the mod folder in the explorer ![](img/17.png)
-   Click on “export selected instance” ![](img/18.png)
-   Copy the link
-   Join your deadline private server
-   Press ` on your keyboard
-   The following menu will come up: <br/> ![](img/19.png)
-   Click on Server Luau Console <br/> ![](img/20.png)
-   Type in `require(“paste the link here”)`

    > example: `require(“https://deadlinegame.com/api/mod/get/370b7c25-cf14-424b-b3f1-9154c7c616a8”)`
    > Remember this link is a one time use, to export the map again repeat these last steps or save the file.

-   This will come up <br/> ![](img/21.png)

-   To use your map type: `map.set_map('template_map')`. Make sure template_map is written between ' or "

## Reference

-   For scripting please refer to the [api](https://recoil-group.github.io/deadline-modding/making-mods/scripting/api/). All code can be run in the server console.
-   For other example mods look [here](https://recoil-group.github.io/deadline-modding/mod-list/), and you can find info on interactables [here](https://recoil-group.github.io/deadline-modding/making-mods/mapping/interactables/).
