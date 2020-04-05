
"etmover" is the lua script.

copy the folder "etmover" to your LUA mods folder.
In my case that is "legacy\luamods"

include the etmover mod to the cvar "lua_modules".
In my case, i set:
/set lua_modules "luamods/etmover/etmover.lua"



"trilist" is the tool.
The tool generates some values that the LUA-script needs.
The executable is located in the folder: "trilist\Debug". It's called "trilist.exe" (a console app for Windows).
The source code of the tool is in the folder: "trilist\trilist".

You can copy the tool to any location you want.
The tool reads a .map file "trilist.map" that must be put into the same folder as the "trilist.exe" console application.

If you want to generate a new list, you must select all triangular shaped terrain brushes in your map, and save that selection to a new map called "trilist.map". Copy that file into the same folder as the .exe, and execute the tool.

If the tool does not encounter any error, it will process all brushes in the trilist.map, and then it will ask for the X- & Y-coordinates of the script_mover.
These are the coordinates you put your etmover at in Radiant. (The tool does not need the Z value). Enter the X- & Y-values as integer values (whole numbers). You see those two coordinates in the top view of Radiant, looking straight down on the terrain.

Note about the brushes that you select:
- All brushes must be the typical terrain type triangular shaped brushes.
- All brushes must have "common/caulk" on all sides, except for the top surface (where you walk on).
- All brushes must have the top surface have any texture    other than "common/caulk".

The brushes you save in the trilist.map do not have to be used in your playable map at all.
Once the list is generated, and copied into the LUA-script, the etmover only knows about the triangles in the list.
The etmover does not use the real map to navigate around. The etmover just uses the list to calculate it's movement.
If your list does not correspond to the actual shape/terrain of your playable map, the etmover's positioning in the world will go wrong.


any questions? => dev/null :)
or at discord:  C..#4546