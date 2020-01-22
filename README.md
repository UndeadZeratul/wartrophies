### Installation
---
Download the zip and load it into GZDoom. No need to change its extension to .pk3. However, a .pk3 extension is required when loading the mod with Delta Touch.

### Important
---
- Requires at least GZDoom 4.3.3! Playing it on anything lower that that won't work right and you may lose progress. You have been warned.
- The mod may not be multiplayer compatible! Not tested.
- Due to the way data is saved, mod may cause ini bloat if played with too many mods for a long time. The data is at the bottom of your config file in a separate section. If ini bloat really bothers you, this mod probably isn't for you. At the moment there is no other way to store data between saves.
- Stats do not persist between IWADs. Due to how CVars are stored in the ini file, there is no workaround for this at the moment.
---
- If you have played a version of this mod prior to v1.0.0, you *may* encounter the following error message: `Dictionary is expected to be a JSON object`.  
To fix this, you have four options, three of which require config editing:
1. If the data is split into several CVars, i.e. `wt_stats_weapons_kills_x`, where x is a number from 1-20, combine the value of all CVars starting from `*_1` until you run out of text, and put it in the `wt_stats_weapons_kills` CVar at the bottom of the config under the section `ConfigOnlyVariables`.
2. If the data is in one CVar called `wt_stats_weapons_kills` but has lots of `@` in the string, replace all `@` with `\`, and replace the one with the same name at the bottom of the config under the section `ConfigOnlyVariables` with that.
3. Erase all encounters of `wt_stats_*` and let the mod generate those again. This will result in progress loss.
4. Delete the config and let GZDoom generate it again. Will result in progress loss. Obviously this is the least convenient solution, but it's guaranteed to work.

### Do this if you want addon support
---
- Add a Tag property to your weapons/monsters.  
*The mod will work without it, but raw class names will be displayed instead and it won't look good unless your class names are sensible.*