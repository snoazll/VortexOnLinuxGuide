# VortexOnLinuxGuide
This is my guide after many trials and errors.

The biggest problems with Steam Deck / Linux scene when it comes to Windows-only software is that (1) most guides just rely on other people's scripts, (2) what they fix isn't generalisable at all.

Hence this guide.

## Pre-Ops

When it comes to Skyrim or Fallout 4, one should launch these games at least once to make sure proper configuration is established and/or necessary downloads and pre-caching are done.

Specifically, the Anniversary Edition download should be completed before going forward, as this will prove very painful later on. This is such a bad management of content, and I have so many things to say about Creation Club - but it's irrelevant to this guide.

## Symbolic Linking

Whether you use Nautilus (Gnome) or Dolphin (KDE), you have an easier way to link files and folders.

* Using Nautilus, you can right-click on an item to Create Link which might not be available as default, so it's better to check out the Nautilus preferences menu first.
* Dolphin can create links when drag-and-drop is being used. Dragging the item to the desired location prompts a menu which contains linking option.

ln isn't necessary, but learning ln is a good skill. It's 2024, Linux and its tools are a standard, not a hobby. I work in Logistics, but even I wouldn't hire someone who can't use ln. I also famously didn't give my blessings to my granddaughter as she wanted to marry someone who didn't even post on r/unixporn. Disgusting.

### SymLink Game Folder

The ideal way of doing this is by symlinking the .../steamapps/common/game folder to somewhere like ~/Games/ so that Proton and Vortex won't have to look for permissions to write on other prefixes.

### SymLink AppData Folder

This is essential as Vortex makes use of this folder to do things and stuff. Vortex relies on AppData folder to deploy mods.

[Method Here]

Please don't confuse AppData and ApplicationData as ApplicationData is itself a symbolic link of AppData.

### SymLink Documents Folder

This is to ensure your Skyrim configuration is made use of Vortex's Proton prefix.

Symlink 

### (Optional?) Install SKSE/F4SE

I'm not entirely sure if this is necessary, but manual installation of Script Extenders can be a big help.

## Some Thingies
### Why not use ModOrganizer2?

There's nothing wrong with MO2, and that is why this guide exists. Vortex can be run on Linux/Steam/Proton, but deployment is a nightmare. ModOrganizer2 has a different way of deploying mods, so it has no problems at all. MO2 works so well that it doesn't even require a guide - just run it on the Proton prefix, rename the prefix; symlink the gamefolder, and rename it to MO2 proton prefix folder, which you previously backed-up by renaming. Done. MO2 works.

The fonts are really bad (since corefonts aren't installed out of the box), but it works nevertheless.

### So why would you use Vortex?

Because you can. That's the motivation here.

### Are there any advantages to Vortex?

Not that I make use of. In my opinion, both tools have horrible user interfaces.

### Are there any other alternatives to both?

I'm not too informed in this regard, but Nexus Mods are developing the successor of Vortex which is Nexus Mods App and it runs on Linux. I don't know when it would be released or be ready for general use, but it looks really promising and its UI is miles better than both of these things.
