### Installation
---
Download the zip and load it into GZDoom. No need to change its extension to .pk3. However, a .pk3 extension is required when loading the mod with Delta Touch.  
NOTE: Loading through command line doesn't seem to work with certain launchers, such as DoomRunner, so get a better launcher, [like ZDL](https://github.com/lcferrum/qzdl/releases).

### Important
---
##### *There is currently a memory leak with the dictionaries in the engine. A mod patch has been applied to almost neutralize this issue. Crashes should NOT be expected. Will be properly fixed engine-side eventually. If you are reading this, a fix does not yet exist.*
- Requires at least GZDoom 4.3.3! Playing it on anything lower that that won't work right and you may lose progress. You have been warned.
- The mod is likely not multiplayer compatible! Not tested.
- Due to the way data is saved, mod may cause ini bloat if played with too many mods for a long time. The data is at the bottom of your config file in a separate section. If ini bloat really bothers you, this mod probably isn't for you. At the moment there is no other way to store data between saves.
- Stats do not persist between IWADs. Due to how CVars are stored in the ini file, the only workaround is to use JPL's [WadSmoosh](https://forum.zdoom.org/viewtopic.php?f=232&t=52757) and use Doom_Complete as an IWAD.
---
- If you have played a version of this mod prior to v1.0.0, you *may* encounter the following error message: `Dictionary is expected to be a JSON object`.  
To fix this, you have four options, three of which require config editing:
1. If the data is split into several CVars, i.e. `wt_stats_weapons_kills_x`, where x is a number from 1-20, combine the value of all CVars starting from `*_1` until you run out of text, and put it in the `wt_stats_weapons_kills` CVar at the bottom of the config under the section `ConfigOnlyVariables`.
2. If the data is only in one CVar called `wt_stats_weapons_kills`, but has lots of `@` in the string, replace all `@` with `\`, and replace the CVar with the same name at the bottom of the config under the section `ConfigOnlyVariables` with the one you just edited.
3. Erase all encounters of `wt_stats_*` and let the mod generate those again. This will result in progress loss.
4. Delete the config and let GZDoom generate it again. Will result in progress loss. Obviously this is the least convenient solution, but it's guaranteed to work.

### First time playing? Read this.
---
- At first you won't see any weapons or monsters. The list is populated as you use them to kill monsters.
- The IWAD filters are enabled by default, meaning you will always see vanilla Doom/Heretic/Hexen/Strife weapons. If playing with mods that add custom weapons, set the weapon filter to "None". If the mod adds monsters, do the same for the monster filter.
- Check out the "Scorecard Keys" submenu in the options. It will give useful information.

### (In)Compatibility
---
Certain mods don't play too well with War Trophies. They will work, but not always the way you'd expect them to. A few examples:
- **Combined Arms (and probably lots of other mods):** Some weapons don't have icons or pickup sprites, so the weapon icon in the scorecard would instead be the first frame from the Ready state. It's only a visual "bug".
- **Kriegsland/Doom Incarnate:** Dual-wielded weapons are separate weapons, meaning their stats are tracked separately from their single variants. This can be fixed if anyone is willing to make folders for those weapons so they count as one. PRs are welcome.
- **Hideous Destructor:** It's possible to attribute kills from a weapon to a different weapon that cannot physically kill anything. For example, throwing a grenade and switching to bandaging will attribute kills to the latter. Normally this isn't an issue in other mods, but HD handles things... differently.
- **Bullet-Eye**: Due to how weapons in Bullet-Eye function under the hood, i.e. a having separate weapon class for each slot, the only workaround is to enable the folders option for the Lite HUD.

### Do this if you want (proper) addon support
---
- Add a Tag property to your weapons/monsters.  
*The mod will work without it, but raw class names will be displayed instead and it won't look good unless your class names are sensible.*
- Add an Icon property to your weapons or define a Spawn state sprite.  
*Again, will work without it, but sometimes Ready state sprites may be used and it'd look bad.*