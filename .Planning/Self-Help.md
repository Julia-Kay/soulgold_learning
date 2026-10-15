Open WSL, and: `cd git/Romhack/soulgold_learning/`
`Code .` opens VSCode
`porymap` opens PoryMap
or `~/git/Romhack/porymap/porymap`



## Workflow:
- Plan map out, including key terrain types and buildings
- Design primary (general, broad re-useable features) and secondary (focused for that specific map or area, like extra buildings, additional/colourful things) tilemap requirements
- Create a new map in PoryMap and note down the name of the map
- Run the initial Porytiles create-tileset
- Replace the top.png, middle.png and bottom.png files in the porytiles_src folder within the data/tileset/ with the actual tileset 
- Animated tiles: frames go in `porytiles_src/anim/<name>/` (`key.png`, `00.png`, `01.png`...).
- Compile the tilesets
- Reload PoryMap, and select the new tilesets for that map 
- Draw the map, then add objects, warps and BGs from the event tab, noting down their relevant ids 

- Set up map collisions
  - Collisions/height: Collision & Elevation tab in Porymap. 
  - Collision 0 = walkable, 1+ = blocked. 
  - Elevation 3 = normal ground. Neighbouring tiles with different elevations block walking. 
  - Elevation 0 ^v arrow tiles are transition points. 
  - Elevation 7 tiles act as bridges

- Open the Metatile Behaviour in the `attributes.csv` (in the map's `porytiles_src/`) and add various tile behaviours.


- Save the map and it will make the files in the project:
  - Map: `data/maps/<MapName>/map.json`. 
  - Layout: `data/layouts/<Name>/map.bin`.
  - Scripts: `data/maps/<MapName>/scripts.pory`. Edit this, not `scripts.inc` (generated from it).
  - Script names set in Porymap events must match a label in `scripts.pory`.


## PoryMap Notes

### Metatile Behaviour

- Metatile behaviour = what a tile DOES when stepped on / used (separate from collision & elevation).
  - Set in `attributes.csv` (in `porytiles_src/`): `id,behavior`, e.g. `3,MB_TALL_GRASS`. Unlisted tiles = `MB_NORMAL`.
  - Metatile id = its position in the PNG, left to right, top to bottom, from 0.
  - Full list: `include/constants/metatile_behaviors.h` (243 of them).
  - Common ones:
    - `MB_NORMAL`: plain ground.
    - `MB_TALL_GRASS`: wild encounters.
    - `MB_LONG_GRASS`: long grass animation.
    - `MB_SAND`: footprints in sand.
    - `MB_SHALLOW_WATER`, `MB_DEEP_WATER`, `MB_OCEAN_WATER`, `MB_POND_WATER`: surfable/wading water.
    - `MB_WATERFALL`: waterfall.
    - `MB_PUDDLE`: splash.
    - `MB_ICE`: slippery.
    - `MB_JUMP_EAST / _WEST / _SOUTH / NORTH` etc: ledge, hop one way.
    - `MB_IMPASSABLE_EAST / _WEST / _SOUTH / _NORTH` etc: blocks movement from that side (i.e. for cliffs).
    - `MB_IMPASSABLE_NORTHEAST ` etc: diagonal impassable. Blocks from both North and East, for example (cliff corner)
    - `MB_NON_ANIMATED_DOOR`, `MB_ANIMATED_DOOR`: door warps.
    - `MB_SOUTH_ARROW_WARP`: step down to warp. has other directions
    - `MB_LADDER`, `MB_ROCK_CLIMB`, `MB_CAVE`: ladder, rock climb, cave warp.
    - `MB_PC`, `MB_BOOKSHELF`, `MB_COUNTER`, `MB_SIGNPOST`: interaction tiles.
    - `MB_BRIDGE_OVER_OCEAN`: water bridge (not needed for land bridges).
    - `MB_NO_RUNNING`: can't run here.
  - Warps and signs still need an event in Porymap. The behaviour alone isn't enough.
  - Command to see the options for your tileset: `porytiles dump-attribute-schema gTileset_Name`


## Events (Porymap > Events tab)
Saved into `data/maps/<MapName>/map.json`. Scripts go in that map's `scripts.pory` (label must match what Porymap shows).
- Object (NPC, item ball, trainer): `script` = label in `scripts.pory`. `flag` = a `FLAG_HIDE_...` if it can disappear (item taken, NPC defeated).
- Warp: `dest_map` + `dest_warp_id` (the number of the warp on the OTHER map). Make both sides point at each other. Needs a door/stairs/warp metatile behaviour to trigger.
- BG event (sign/hidden item): sign = `script` label, facing direction. Hidden item = item + flag.
- Coord event (trigger tile): `var` + `var_value` makes it fire once. Script label as above.
- Flags: `include/constants/flags.h`. Pick a free `FLAG_UNUSED_...` (rename it), or add `FLAG_HIDE_...` for hidden objects. 
- Vars: `include/constants/vars.h`, same idea.
- Text: `.string` / `text` blocks in `scripts.pory`, always end with `$`.
- Item constants: `include/constants/items.h`. Trainers: `src/data/trainers.party`, `include/constants/opponents.h`.
- Shared scripts: `data/scripts/*.pory` / `.inc`.
- Edit `.pory`, never `scripts.inc`. Then `make`.

## Porytiles (run from `~/git/Romhack/soulgold_learning/`)
Your art lives in `data/tilesets/<primary or secondary>/<tileset_name>/porytiles_src/`: `bottom.png`, `middle.png`, `top.png`, `attributes.csv`.
`<tileset_name>` is the tileset's name in snake_case (gTileset_SwordOfMana -> `sword_of_mana`), not the map's name.
Never edit `porytiles_bin/`. Porymap reads that folder.

- Make a new tileset, ONCE only per new map: `porytiles create-tileset gTileset_Name`
- Make a secondary: `porytiles create-tileset <gTileset_Name> --secondary`
- secondaries are made specifically linked to a primary. Using a secondary with a primary it wasn't linked to can cause weird pallette things, unless this was planned for. 
- After editing the PNGs: `porytiles compile-tileset <gTileset_Name>`
- Then in Porymap: File > Reload Project
- If you changed things in Porymap instead: `porytiles decompile-tileset gTileset_Name`
- List tilesets: `porytiles list-tilesets`
- See the settings in use: `porytiles dump-tileset-config gTileset_Name`

Stuck or "frozen"? It is probably still packing palettes. Press Ctrl+C, then try:
`porytiles compile-tileset gTileset_Name --packing-strategy best-fusion`

Rules: 15 colours + transparent per 8x8 tile. Primary has 7 palettes, secondary has 6.
Transparent = magenta (255,0,255) or alpha 0.
Images are 128 px wide, height a multiple of 16. All 3 images are the same size.
If compile says "no palette has room": use fewer colours, or merge similar colours.


## PoryScript Notes

  Heal spot = Fly point + where you wake up after a whiteout.
- Defined in `src/data/heal_locations.json`:
    - `id`: unique `HEAL_LOCATION_X` 
    - `map`, `x`, `y`: Fly landing spot
    - `respawn_map`, `respawn_x`, `respawn_y`: whiteout spot (Pokémon Center / house)
    - `respawn_npc`: local ID of the NPC who greets you (nurse / mom)
- Activate it in a script: `setrespawn HEAL_LOCATION_X` (usually in the map's on-transition script for flying, or when healing at a center)
