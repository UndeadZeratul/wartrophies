### Installation
---
Download the zip and load it into GZDoom. No need to change its extension to .pk3. However, a .pk3 extension is required when loading the mod with Delta Touch.

### Important
---
- The mod is not multiplayer compatible!
- Requires a dev build of GZDoom! Prior to dev builds, the mod relied on undefined behaviour to keep data saved between save games. This was extremely dangerous and at the time I didn't know why it even worked. A proper fix has been applied, but it would only work with a dev build. Specifically, anything starting from **g4.3pre-640-geeddd7245** (incl.) would work.  
***DO NOT ATTEMPT TO LOAD THIS WITH GZDOOM 4.3.1! YOU WILL LOSE ALL PROGRESS ON EXIT! YOU HAVE BEEN WARNED! This is because the "nosave" CVARINFO keyword does not do what it's supposed to do in that version!***

### Do this if you want addon support
---
- Add a Tag property to your weapons/monsters.  
*The mod will work without it, but raw class names will be displayed instead and it won't look good unless your class names are sensible.*

### Library
---
The mod allows defining of custom categories and tags for weapons. To use this feature, create a lump called WTLBRARY and use the following syntax:  
`<weapon class name>,<category>,[custom tag]`

**Examples:** `SuperShotgun,Shotguns,Bearkiller`, `Shotgun,None,Hunter`, `BFG9000,Energy,Doomsday Cannon`

**NOTES:**
- One definition per line.
- Do not use spaces after the commas!
- Comments are also parsed, so don't bother adding them.
- Tags are optional. They override the real weapon tags, if any.
- Support for this feature is limited. Don't expect me to extend it much.