# A Vortex Usage Guide for Linux
This is my guide after many trials and errors.

The biggest problems with the Steam Deck / Linux scene when it comes to Windows-only software are that (1) most guides just rely on other people's scripts, (2) what they fix isn't generalisable at all. I'm not a massive fan of running people's scripts on my devices, even if they're open-source. Instead, I look into what they do right and what others do wrong to figure out how things should be structured.

Hence, this guide.

## Pre-Ops

When it comes to Skyrim or Fallout 4, one should launch these games at least once to make sure proper configuration is established and/or necessary downloads and pre-caching are done.

Specifically, the Anniversary Edition download should be completed before going forward, as this will prove very painful later on. This is such a bad management of content, and I have so many things to say about Creation Club - but it's irrelevant to this guide.

## Symbolic Linking

Whether you use Nautilus (Gnome) or Dolphin (KDE), you have an easier way to link files and folders.

* Using Nautilus, you can right-click on an item to Create Link, which might not be available by default, so it's better to check out the Nautilus preferences menu first.
* Dolphin can create links when drag-and-drop is being used. Dragging the item to the desired location prompts a menu which contains a linking option.

<em>ln</em> isn't necessary, but learning <em>ln</em> is a good skill. It's 2024, and Linux and its tools are a standard, not a hobby. I work in Logistics, but even I wouldn't hire someone who can't use <em>ln</em>. I also famously didn't give my blessings to my granddaughter, as she wanted to marry someone who didn't even post a single screenshot on r/unixporn. Absolutely disgusting.

## Important Bits
### Where to position Vortex Mods

The VortexMods folder (or whatever you name it) where mods are being stored should be positioned within your game's Proton prefix, because Vortex doesn't allow mods to be stored on different drives - and prefixes are registered as different drivers.

You can also symlink your VortexMods folder to your game's Proton prefix, but I'm not entirely sure if this would work. It should theoretically work, but the world is a simulation, so it might not.

#### A Fair Warning About This Staging Folder
Back this folder up. One Proton Prefix change on Skyrim's side, and this folder is gone; you're going back to adding your mods over and over again in that case.

It might be possible to make this folder not removable by Proton, but I wouldn't bet my money on that - and that would just make things unnecessarily complex. So, it would be better to back this folder to an external HDD just in case and copy over in case of a Proton version change etc.

### SymLink Game Folder

The ideal way of doing this is by symlinking the 

> .../steamapps/common/gamefolder

to somewhere like 

> ~/Games/

so that Proton and Vortex won't have to look for permissions to write on other prefixes.

### SymLink AppData Folder

This is essential as Vortex relies on this folder and wants this folder to be in the same drive as the game in order to properly deploy mods.

You will have to symlink the AppData folder in your Vortex Proton prefix into the game's Proton prefix.

So symlink,

> .../compatdata/$VortexPrefixID/.../AppData

as

> .../compatdata/$SteamGameID/.../AppData

Please don't confuse AppData and ApplicationData, as ApplicationData is itself a symbolic link to AppData.

### SymLink Documents Folder

This is to ensure your Skyrim configuration is used by Vortex's Proton prefix, because you will be running Vortex's proton, not your game's. It will update your game's prefix over Vortex's prefix.

So symlink,

> .../compatdata/$SteamGameID/.../Documents

as,

> .../compatdata/$VortexPrefixID/.../Documents

Symlink the Documents folder in your game's Proton prefix into the Vortex Proton prefix.

### (Optional?) Install SKSE/F4SE

I'm not entirely sure if this is necessary, but manual installation of Script Extenders can be a big help.

## Some Thingies
### Why not use ModOrganizer2?

There's nothing wrong with MO2, and that is why this guide exists. Vortex can be run on Linux/Steam/Proton, but deployment is a nightmare. ModOrganizer2 has a different way of deploying mods, so it has no problems at all. MO2 works so well that it doesn't even require a guide - just run it on the Proton prefix, rename the prefix; symlink the gamefolder, and rename it to MO2 proton prefix folder, which you previously backed up by renaming. Done. MO2 works.

The fonts are really bad (since corefonts aren't installed out of the box), but it works nevertheless.

### So why would you use Vortex?

Because you can. That's the motivation here. Also, it has a "better" name.

### Are there any advantages to Vortex?

Not that I make use of. In my opinion, both tools have horrible user interfaces.

### Are there any other alternatives to both?

I'm not too informed in this regard, but Nexus Mods are developing the successor of Vortex which is Nexus Mods App and it runs on Linux. I don't know when it would be released or be ready for general use, but it looks really promising and its UI is miles better than both of these things.
