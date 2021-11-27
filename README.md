### Installation
---
Download the zip and load it into GZDoom. No need to change its extension to .pk3.

### Important
---
- Requires at least GZDoom 4.5.0.
- The mod has been tested in multiplayer and works just fine. If any abnormalities are observed, please report them.
- Due to the way data is saved, the mod may cause ini bloat if played with too many mods for a long time. The data is at the bottom of your config file in a separate section. If ini bloat really bothers you, this mod probably isn't for you. At the moment there is no other way to store data between saves.
- Stats do not persist between IWADs. Due to how CVars are stored in the ini file, the only workaround is to use JPL's [WadSmoosh](https://forum.zdoom.org/viewtopic.php?f=232&t=52757) and use Doom_Complete as an IWAD.

### First time playing? Read this.
---
- At first you won't see any weapons or monsters. The list is populated as you use them to kill monsters.
- The IWAD filters are enabled by default, meaning you will always see vanilla Doom/Heretic/Hexen/Strife weapons. If playing with mods that add custom weapons, set the weapon filter to "None". If the mod adds monsters, do the same for the monster filter.
- Check out the "Scorecard Keys" submenu in the options. It will give useful information.

### (In)Compatibility
---
Certain mods don't play too well with War Trophies. They will work, but not always the way you'd expect them to. A few examples:
- **Combined Arms (and probably lots of other mods):** Some weapons don't have icons or pickup sprites, so the weapon icon in the scorecard would instead be the first frame from the Ready state. It's only a visual "bug".
- **Kriegsland/Doom Incarnate:** Dual-wielded weapons are separate weapons, meaning their stats are tracked separately from their single variants. This can be fixed if anyone is willing to make folders for those weapons so they count as one. Pull requests are welcome.
- **Hideous Destructor:** It's possible to attribute kills from a weapon to a different weapon that cannot physically kill anything. Most such weapons have been blacklisted, but some may have been overlooked.

### Do this if you want (proper) addon support
---
- Add a Tag property to your weapons/monsters.  
*The mod will work without it, but raw class names will be displayed instead and it won't look good unless your class names are sensible.*
- Add an Icon property to your weapons or define a Spawn state sprite.  
*Again, will work without it, but sometimes Ready state sprites may be used and it'd look bad.*
- Prefix your weapon classes! There have been reports of weapons from one mod affecting a weapon from another because they both shared the same class name.

### Blacklisting Classes
---
- You don't need to touch War Trophies to do that. If you have classes in your own mod that you wish to be blacklisted, add a WTBLKLST lump to your mod's root directory, then separate each blacklisted class with a comma. You can place them on new lines and such, but don't use comments.

Example: `LostSoul, Revenant, SpiderMastermind, Cyberdemon, BossBrain`

### Miscellaneous
---
- `netevent WT_ToggleSaving`: temporarily makes all kills "fake". The numbers on the HUD will update, but the stats will not be saved if you exit the game. The old numbers will be reverted when you toggle this again. Limited use.
- `netevent WT_Cleanup #`: this will remove all monsters stats with kills under #. Can be used in combination with WT_ToggleSaving to non-destructively test the result of the command. Toggle saving off, then use the cleanup command. If you are satisfied with the results, turn saving back on and do the cleanup again. This is useful if your weapons are plagued with some rare kills of which you only have a very small number of that you wish to get rid of.