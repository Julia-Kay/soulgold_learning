# New Region ROM Hack Plan

> **Working document:** Fill this in as the region, story, maps, and encounters
> are designed. Use stable IDs so notes can be cross-referenced between
> sections. `TBD` means a decision or detail is still needed; `N/A` means it
> was considered and intentionally omitted.

## Project direction

### The goal

Create a new Pokémon GBA adventure with an original region, story, cast,
locations, and world map. Use this Soulgold/pokeemerald-expansion codebase as
the technical foundation, preserving the all-generation Pokémon overworld
sprites, Pokémon follower system, and selected quality-of-life features.

The existing Johto/Soulgold content is a source of implementation examples and
reusable systems, not the story or map specification for the new game.

### Design pillars

| Pillar | What it means for this game | Decisions / notes |
| --- | --- | --- |
| Original identity | New setting, route names, settlements, characters, conflict, and visual motifs | TBD |
| Readable exploration | Players can understand where paths lead and what currently blocks them | TBD |
| Meaningful backtracking | New traversal abilities reveal optional rewards and useful shortcuts, not just dead ends | TBD |
| Character continuity | Recurring NPCs remember important encounters and visibly progress | TBD |
| Pokémon adventure | Pokémon, battles, discovery, and the player's team remain central | TBD |

### Project decisions

Record decisions here when they affect several parts of the game. Link to the
relevant tracker IDs.

| ID | Decision | Options considered | Chosen direction | Date / status |
| --- | --- | --- | --- | --- |
| DEC-001 | Region name and real-world inspiration | TBD | TBD | Open |
| DEC-002 | Story tone, audience, and themes | TBD | TBD | Open |
| DEC-003 | Main progression structure | Linear / hub-and-spoke / branching / TBD | TBD | Open |
| DEC-004 | HM / field-move unlock model | Traditional HM / key item / story unlock / other | TBD | Open |
| DEC-005 | Starter selection and opening location | TBD | TBD | Open |

## Storyline

### Premise

- **Working title:** TBD
- **Region:** TBD
- **Player character:** TBD
- **Starting location:** TBD
- **Opening situation:** TBD
- **Central conflict:** TBD
- **Antagonist or opposing force:** TBD
- **Legendary / regional mystery:** TBD
- **Why the player gets involved:** TBD
- **What is at stake if the player fails:** TBD
- **Resolution:** TBD
- **Postgame direction:** TBD

### Story summary

Write one paragraph that explains the adventure from beginning to end. Keep it
short enough to use as a continuity check when adding routes, characters, and
side quests.

> TBD

### Setting and lore

| Topic | Established facts | Where the player learns this | Open questions |
| --- | --- | --- | --- |
| Region history | TBD | TBD | TBD |
| Towns, cultures, and local identities | TBD | TBD | TBD |
| Pokémon and people | TBD | TBD | TBD |
| Legendary lore | TBD | TBD | TBD |
| Antagonist's history and goals | TBD | TBD | TBD |
| Technology, travel, and communication | TBD | TBD | TBD |

### Continuity rules

Use this list to avoid contradictions as the script and map count grows.

- A character's knowledge must match the story events they have witnessed.
- Every major story revelation should have an earlier clue or a deliberate
  reason it is surprising.
- A route's gates, exits, landmarks, and encounter habitats should agree with
  the world map and neighboring maps.
- Every ability gate should have a clear first teaching/unlock moment and a
  practical first use soon afterward.
- A one-time event should have an explicit flag/state and a defined result if
  the player returns later.
- TBD

## Story beats

Track the main plot in the order the player is expected to encounter it. Give
each beat a stable ID (`BEAT-01`, `BEAT-02`, ...) and record the maps, NPCs,
flags, and progression changes it touches.

| Beat ID | Chapter / order | Trigger and prerequisites | Location(s) | What happens | Player learns / does | State change, reward, or unlock | Follow-up / return behavior | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| BEAT-01 | Opening | New game | TBD | Establish the region and immediate goal | TBD | Starter / first objective: TBD | TBD | Outline |
| BEAT-02 | Early journey | TBD | TBD | TBD | TBD | TBD | TBD | Outline |
| BEAT-03 | First major turning point | TBD | TBD | TBD | TBD | TBD | TBD | Outline |
| BEAT-04 | Midpoint revelation | TBD | TBD | TBD | TBD | TBD | TBD | Outline |
| BEAT-05 | Climax | TBD | TBD | TBD | TBD | TBD | TBD | Outline |
| BEAT-06 | Resolution / postgame | TBD | TBD | TBD | TBD | TBD | TBD | Outline |

### Beat checklist

For each major beat, note:

- What the player knows before the beat, and what changes afterward.
- Whether the beat is mandatory, optional, or can happen in multiple orders.
- Which NPCs appear and how their relationship/state changes.
- Which map events, object events, flags, variables, battles, and rewards are
  required.
- What happens if the player leaves, loses a battle, or returns after the beat.
- How the player learns their next objective without relying on an untracked
  assumption.

## Recurring NPC tracking

Give every recurring character a stable ID (`NPC-001`, `NPC-002`, ...). Record
their appearances in order, what they know, how they change, and where their
team changes occur. This includes rivals, companions, antagonists, professors,
gym leaders, recurring helpers, and important optional characters.

### Character index

| NPC ID | Name | Role | First appearance (map / beat) | Ongoing goal | Relationship to player | Final state | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| NPC-001 | TBD | Rival / TBD | TBD | TBD | TBD | TBD | Outline |

### Character arc and appearances

Use one row per appearance or meaningful state change. For dialogue continuity,
write down the character's knowledge and attitude at that exact point in the
story.

| NPC ID | Appearance # | Beat ID | Map ID | Entry condition | Knowledge / attitude | Action or dialogue purpose | Exit / next appearance | Script / event notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| NPC-001 | 1 | BEAT-01 | MAP-TBD | TBD | TBD | TBD | TBD | TBD |

### Recurring trainer teams

Keep each battle as a separate team version (`TEAM-NPC-001-01`, `TEAM-NPC-001-02`).
Record the intended level curve and battle context as well as species. Fill
moves, abilities, held items, and battle format when they are designed.

| Team ID | NPC ID | Story point / map | Player level expectation | Battle type | Team purpose / difficulty | Rematch or later version |
| --- | --- | --- | --- | --- | --- | --- |
| TEAM-NPC-001-01 | NPC-001 | TBD | TBD | Single / double / other | TBD | TEAM-NPC-001-02 / N/A |

#### Team details

Copy this block for each team version:

**Team ID:** `TEAM-TBD`

**NPC ID / display name:** `NPC-TBD` / TBD

**Story beat and map:** `BEAT-TBD` / `MAP-TBD`

**Prerequisite / battle trigger:** TBD

**Expected player level and party strength:** TBD

**Battle format / special rules:** TBD

**Reward / post-battle scene:** TBD

**Rematch conditions:** TBD

| Slot | Species / form | Level | Ability | Held item | Moves | Role / notes |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | TBD | TBD | TBD | TBD | TBD | TBD |
| 2 | TBD | TBD | TBD | TBD | TBD | TBD |
| 3 | TBD | TBD | TBD | TBD | TBD | TBD |
| 4 | TBD | TBD | TBD | TBD | TBD | TBD |
| 5 | TBD | TBD | TBD | TBD | TBD | TBD |
| 6 | TBD | TBD | TBD | TBD | TBD | TBD |

## Region and world-map plan

### Region overview

- **Region name:** TBD
- **Map orientation and scale:** TBD
- **Major geographic features:** TBD
- **Starting corner / hub:** TBD
- **League / final challenge location:** TBD
- **Main travel loop(s):** TBD
- **Island, cave, or remote areas:** TBD
- **How the region map is revealed to the player:** TBD
- **World-map visual reference or draft:** Add a link or image when available.

### Map index

Assign stable IDs (`MAP-001`, `MAP-002`, ...), independent of final in-game
map-group numbers. Use the same ID in story beats, routes, secrets, and spawn
tables. Split a location into multiple map IDs when floors, rooms, or gameplay
states are implemented as separate maps.

| Map ID | Display name | Map kind | Neighbors / exits | Main beat(s) | First access | Revisit changes | Porymap / asset status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| MAP-001 | TBD | Town / route / interior / dungeon / other | TBD | BEAT-TBD | Start / TBD | TBD | Concept |

### Map implementation notes

The new region will need coordinated edits to map data and the in-game region
map. Track the new setting across the existing data sources instead of treating
the world-map picture as the only region-map change:

- Map JSON, group ordering, connections, events, and layouts under
  `data/maps/` and `data/layouts/`.
- Region-section IDs and display names in
  `src/data/region_map/region_map_sections.json`, including any dependent
  templates and generated constants.
- Region-map layout data and graphics under `src/data/region_map/` and
  `graphics/pokenav/region_map/`.
- Map names, player-facing destinations, warps, scripts, encounters, and any
  Pokégear / Pokédex / location references that use map-section IDs.

Use Porymap for map structure and events where appropriate. Use Porytiles for
tileset/metatile work and Aseprite for pixel-art assets. Keep authored source
files distinct from build-generated outputs.

## Editing workflow with Porymap, Poryscript, and Porytiles

Use the tool that owns the kind of data being changed. These tools complement
one another; none replaces the project build or an in-game playtest.

| Tool | Use it for | Typical project inputs / outputs |
| --- | --- | --- |
| **Porymap** | Drawing maps; editing metatile placement, collision, elevations, map properties, connections, events, encounters, and region-map data. | Reads and writes project sources, including map and layout data under `data/maps/` and `data/layouts/`. It edits the decompilation project, not a built `.gba` file. |
| **Poryscript** | Writing readable map scripts, dialogue, conditions, battles, flags, and event sequences. | Author scripts in `.pory` source files under `data/`. The project build compiles these into generated `.inc` files; edit the `.pory` source, not the generated output. |
| **Porytiles** | Preparing and compiling tileset art and metatile data for use by the game and map editor. | Starts from tileset source art and configuration, and produces tileset data/assets. Its commands and expected files depend on the Porytiles version and project setup. |

### Before editing

1. Keep the project building before starting a change, so new failures are easy
   to identify. The normal project build is `make`; see `INSTALL.md` if the
   development environment is not set up yet.
2. Check the map, route, story-beat, gate, and asset entries above, and give
   each new location the planned stable ID before implementing it.
3. Check `git status` and make a checkpoint before opening or saving changes
   from Porymap. Porymap writes directly to the project sources, and some event
   property edits do not have editor undo/redo.
4. Edit authored sources. Do not hand-edit generated map data or Poryscript
   `.inc` output; rebuild to regenerate outputs from their sources.

### Map and event workflow

1. Open the decompilation project folder with Porymap (`File > Open Project…`).
   Choose or create the map and layout for the planned `MAP-*` entry, then
   paint the blockout and tune collision/elevation before polishing decoration.
2. Set map properties and tilesets, then add exits. For seamless neighbors,
   create matching connections on both maps; if using Porymap's **Mirror to
   Connecting Maps** option, save all affected maps.
3. Use the Events tab to place NPCs, warps, signs, and triggers. Check each
   warp's destination and destination warp, and place it on a valid exit
   metatile. Give story-critical NPCs a stable local ID where practical.
4. Put behavior and dialogue in an authored `.pory` script, then point the
   event at that script in Porymap. Use flags/variables to represent tracked
   story state and traversal gates; record those IDs and intended changes in
   the story-beat and movement-gate tables above.
5. Save, run `make`, reopen/reload the edited map as needed, and test the
   route in an emulator. Verify both directions of connections, warps,
   event visibility, collision, and what happens before and after the relevant
   story flag or ability is obtained.

**Example — first route with a recurring NPC:** Add the route and its
connection to the neighboring town in Porymap. Place the NPC and give it a
named local ID; author its first-visit dialogue and any flag changes in
`.pory`. Record the appearance as a story beat and update the NPC tracker with
the map ID, dialogue state, and team. Build and test entering and leaving the
route, speaking to the NPC again, and returning after the next beat.

### Script and story-event workflow

1. Decide the trigger, prerequisites, outcome, and replay behavior first.
   Record important changes in the story-beat, recurring-NPC, secret, or gate
   trackers so the implementation matches the intended progression.
2. Write the event in `.pory`, using the project's existing script patterns
   and named flags/variables. Keep separate states explicit, such as before
   meeting a character, after the meeting, and after a later revelation.
3. Assign the script to the correct Porymap event, and confirm that its event
   flag, local ID, position, and trigger type match the script's assumptions.
4. Run `make` so the configured Poryscript rule regenerates the corresponding
   `.inc` file and the full project build checks the result. Do not modify the
   generated `.inc` as the lasting fix.
5. Test each branch in-game, including repeated interaction, reload/re-entry,
   and both sides of any progression gate.

**Example — Surf unlocks a cove:** Record a `GATE-*` entry and the cove's
`MAP-*` / `SECRET-*` entries. Add the Surf barrier and any connecting maps in
Porymap; author the unlock dialogue and state changes in `.pory`. Check that
the cove is inaccessible beforehand, reachable afterwards, and that the
player can return through the intended route without becoming trapped.

### Tileset and metatile workflow

1. Decide whether the target tileset is already supported by the project's
   current asset pipeline. Porytiles is a separate compiler in this workspace;
   the root `Makefile` does not currently invoke it as part of `make`.
2. Create or edit the source art in the appropriate pixel-art tool and prepare
   the inputs/configuration required by the Porytiles version being used.
   Consult that version's user documentation for setup, supported input
   formats, and exact command syntax rather than copying commands from a
   different version.
3. Compile the tileset with Porytiles only when the project's tileset sources
   and target format are configured for it. Review the generated assets and
   place them in the project paths expected by its existing tileset workflow;
   do not assume Porytiles outputs are automatically consumed by the root
   build.
4. Open the affected tileset/map in Porymap, verify metatiles, palettes,
   animations, collision, and map appearance, then save and run `make`.
   Test the result in-game, including any animated or edge metatiles.
5. Record the source art, compiler/configuration version, and credits in the
   asset tracker so the tileset can be regenerated and maintained.

### Change-sized workflows

- **Visual-only map pass:** Use Porymap to paint and save; build and inspect the
  map in-game. No script change is needed unless event behavior changes.
- **Dialogue or story logic:** Edit `.pory`, attach or confirm the event in
  Porymap, run `make`, and test every state/branch in-game.
- **New area with custom art:** Plan its map and gate entries, prepare and
  compile tileset assets as supported by the project, build the map/events in
  Porymap, implement scripts in `.pory`, then build and test the connected
  progression.

## Routes and location guide

Track each route or explorable location as a player-facing guide entry, in the
same practical style as a game wiki: where it is, how to get there, what is
there, what it connects to, and what can be missed or revisited.

### Route index

| Route ID | Display name | Connects | Terrain / identity | First available after | Required for main story? | Key landmarks |
| --- | --- | --- | --- | --- | --- | --- |
| ROUTE-001 | TBD | MAP-TBD ↔ MAP-TBD | TBD | TBD | Yes / No | TBD |

### Route details

Copy this for each route, town, dungeon, or other explorable area:

#### ROUTE-TBD — [Display name]

- **Map IDs:** `MAP-TBD` (include floors / connected maps)
- **Position in region:** TBD
- **Connects to:** TBD (direction and exit/entrance)
- **First access:** TBD
- **Later access / shortcuts:** TBD
- **Main story use:** `BEAT-TBD` / optional / none
- **Landmarks and orientation cues:** TBD
- **People, services, and battles:** TBD
- **Items and secrets:** `SECRET-TBD` / none
- **Wild encounters:** `SPAWN-TBD` / none
- **Traversal gates:** `GATE-TBD` / none
- **One-way transitions or missable content:** TBD
- **Return visit changes:** TBD
- **Map editor / visual notes:** TBD

## Player movement and traversal gates

Treat progression as a graph: maps are nodes and traversable connections are
edges. Record the prerequisite on the edge, not only on the destination map.
This makes it possible to see whether an ability opens a new region, a shortcut,
or an optional secret.

### Movement abilities and unlocks

| Gate ID | Ability / key item | How and when it is unlocked | Unlock beat / NPC | First required use | Other areas opened | Can the player return without it? |
| --- | --- | --- | --- | --- | --- | --- |
| GATE-001 | Surf / TBD | TBD | BEAT-TBD / NPC-TBD | ROUTE-TBD / MAP-TBD | TBD | Yes / No |

For an HM-based progression choice, document the full player-facing and
implementation behavior. For example, if receiving the Surf HM is the actual
unlock, distinguish receiving it, being allowed to use it outside battle, and
having a Pokémon that can perform the move. Record whether the game keeps
traditional badges, uses a story flag, or uses another rule.

### Connection and access graph

Use one row per meaningful connection. Add separate rows for one-way drops,
locked doors, water crossings, cave entrances, and shortcuts.

| From map / exit | To map / entrance | Direction | Requirement / gate ID | Main path or optional? | First available after | Reverse route / return method | Tested? |
| --- | --- | --- | --- | --- | --- | --- | --- |
| MAP-TBD | MAP-TBD | N / S / E / W / warp | None / GATE-TBD | Main / optional | TBD | TBD | No |

### Player route-through checklist

For every main-story chapter, verify the expected player path and alternatives.

| Chapter / beat | Starting map | Expected next maps | Required gate(s) | Optional detours | Intended return path | Softlock / wrong-turn checks |
| --- | --- | --- | --- | --- | --- | --- |
| BEAT-TBD | MAP-TBD | MAP-TBD → MAP-TBD | GATE-TBD / None | TBD | TBD | TBD |

## Secrets, side quests, and rewards

Use stable IDs (`SECRET-001`, `QUEST-001`, ...). Track the clue as well as the
solution so optional content can be discovered fairly. Record whether the
content is repeatable, missable, or changes after story progress.

### Secret and quest index

| ID | Name / short description | Location(s) | Clue / hint source | Prerequisite | Discovery / activation | Reward / outcome | Repeatable / missable? | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SECRET-001 | TBD | MAP-TBD | NPC-TBD / sign / visual clue | GATE-TBD / None | TBD | TBD | TBD | Outline |

### Secret detail template

#### SECRET-TBD — [Name]

- **Where:** `MAP-TBD`, exact landmark or event position TBD
- **How the player hears about it:** `NPC-TBD` / `BEAT-TBD` / environmental
  hint / none
- **Clue wording or visual cue:** TBD
- **Prerequisites:** `GATE-TBD`, flag, item, or none
- **How to activate / solve:** TBD
- **Reward / consequence:** TBD
- **Can it be missed or repeated?:** TBD
- **Return-state behavior:** TBD
- **Script, flag, and map-event notes:** TBD

## Wild encounters and other spawns

Use stable IDs (`SPAWN-001`, ...). Track encounter data by map and encounter
method, including any progression-dependent changes. Give species, levels,
forms, time, weather, season, special conditions, and rates a place to be
recorded as the design becomes concrete.

### Spawn index

| Spawn ID | Map / area | Method | Unlock / prerequisite | Story phase | Unique behavior |
| --- | --- | --- | --- | --- | --- |
| SPAWN-001 | MAP-TBD | Grass / water / fishing / cave / gift / other | None / GATE-TBD | TBD | TBD |

### Encounter table

#### SPAWN-TBD — [Map / encounter method]

- **Map IDs / sub-areas:** `MAP-TBD`
- **Encounter method:** Grass / surf / fishing / rock smash / gift / static /
  other
- **Prerequisite or unlock:** None / `GATE-TBD` / story flag TBD
- **Time, weather, season, or other conditions:** TBD
- **DexNav / swarm / grotto / special behavior:** TBD
- **Changes after story beats:** `BEAT-TBD` / none

| Slot / rate | Species / form | Min level | Max level | Time / condition | Notes |
| --- | --- | --- | --- | --- | --- |
| TBD | TBD | TBD | TBD | TBD | TBD |

Document NPC gifts, trades, roaming encounters, legendary/static encounters,
and quest rewards in the method/location where the player obtains them. Link
them to their `NPC`, `BEAT`, `SECRET`, or `SPAWN` ID rather than maintaining
conflicting duplicate notes.

## Items, services, and battle progression

Track important rewards and services so that map exploration supports the
intended difficulty curve.

| ID | Item / service / reward | Location | Source (NPC, secret, event) | Prerequisite | Intended availability | Balancing notes |
| --- | --- | --- | --- | --- | --- | --- |
| REWARD-001 | TBD | MAP-TBD | NPC-TBD / SECRET-TBD / BEAT-TBD | TBD | TBD | TBD |

| Milestone | Expected player level / party state | Important battles | Available healing / shop access | Notes |
| --- | --- | --- | --- | --- |
| First badge / milestone | TBD | TBD | TBD | TBD |
| Midgame | TBD | TBD | TBD | TBD |
| Final challenge | TBD | TBD | TBD | TBD |

## Art, audio, and presentation

| Asset / theme | Purpose and locations | Source file / planned format | Tool | Credits / provenance | Status |
| --- | --- | --- | --- | --- | --- |
| Region map | `MAP-TBD` | TBD | Aseprite / other | TBD | Concept |
| Tileset / metatiles | `MAP-TBD` | TBD | Porytiles | TBD | Concept |
| Character sprites | `NPC-TBD` | TBD | Aseprite | TBD | Concept |
| Music / ambience | `MAP-TBD` / `BEAT-TBD` | TBD | TBD | TBD | Concept |

Keep source art editable where possible. Before adding or adapting third-party
assets, record the creator, source, license or permission, and required credit.

## Implementation and progress tracking

### Suggested phases

Treat these as an order of work, not a promise that every phase must be
completed before prototyping the next.

1. **Define the premise:** fill the storyline, region identity, design
   decisions, and major story beats.
2. **Block out the world:** create the route index, map IDs, world-map draft,
   map connections, and progression gates.
3. **Prototype the opening:** build a small connected slice with the starting
   location, first route, first recurring NPC appearance, first encounter
   tables, and one testable story beat.
4. **Plan the full progression:** check route-through order, HM/field-move
   unlocks, backtracking, optional areas, and return-state behavior.
5. **Populate characters and content:** add NPC arcs and teams, secrets,
   quests, items, and encounter tables using the trackers above.
6. **Create and integrate assets:** build tilesets, maps, region-map art,
   character sprites, and other assets in their appropriate tools.
7. **Implement and validate:** wire map data, scripts, events, flags, and
   content into the ROM; build and test in an emulator.
8. **Polish and document:** verify the whole region, update player-facing
   guides, fix continuity gaps, and preserve asset credits.

### Content status

Use one consistent status value in the tables:

- `Outline` — concept exists, details incomplete.
- `Designed` — player-facing behavior and dependencies are specified.
- `In progress` — being implemented or authored.
- `Implemented` — present in source.
- `Tested` — verified in a built ROM / editor as applicable.
- `Revisit` — known gap, issue, or polish pass remains.
- `N/A` — intentionally excluded.

### Playtest checklist

- [ ] A new player can identify the main objective and next step.
- [ ] Every story-critical map connection is reachable when needed.
- [ ] Every gate is taught before it is required, with no accidental softlocks.
- [ ] Newly unlocked traversal abilities have clear uses and reveal the
      intended optional areas.
- [ ] Returning to earlier maps after major beats produces the intended NPC,
      event, and access state.
- [ ] Recurring NPC appearances, knowledge, dialogue, and teams match their
      tracked story progress.
- [ ] Encounter species and levels fit the location and current party curve.
- [ ] Secrets have discoverable clues and correct prerequisites / rewards.
- [ ] The region map, map names, route connections, and actual in-game exits
      agree.
- [ ] Pokémon followers, all-generation overworld sprites, and retained QoL
      features still work in the new areas.
- [ ] New or adapted assets have their provenance and credits recorded.
- [ ] The ROM builds, relevant tests pass, and the affected areas are checked
      in an emulator.

## Open questions

Add unresolved design questions here; promote decisions that affect multiple
systems to the **Project decisions** table above.

- What is the region called, and what is its geography or cultural inspiration?
- What is the central conflict, and how does the player become involved?
- Who is the rival / companion, and how do their team and attitude evolve?
- What is the gym, trial, or equivalent progression structure?
- Which traversal abilities are used, and what exactly unlocks each one?
- Which existing Soulgold features and systems are kept, altered, or removed?
- What is the target scope for the main story, postgame, and optional content?
