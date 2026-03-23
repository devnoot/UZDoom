# Installation

## Download from ZDoom.org

The latest stable release can be found here: https://zdoom.org/downloads

## Download from GitHub

Download a latest stable release or a latest development build of UZDoom:

* Latest stable release: https://github.com/UZDoom/UZDoom/releases/latest
* Latest devbuild: https://github.com/UZDoom/UZDoom/releases/tag/nightly

Each of these links contains a number of files under the "Assets" section:

- Download this one to play on **Windows**: `Windows-UZDoom-XXXXX.zip`
- Download this one to play on **Linux**: `Linux-UZDoom-XXXXX.AppImage`
- Download this one to play on **MacOS**: `MacOS-UZDoom-XXXXX.zip` 
- Source code (ignore unless you're a developer): `Source code (zip)`
- Source code (ignore unless you're a developer): `Source code (tar.gz)`

The release page will contain some notes that you should read. If the release is a stable one, there will also be a link to it in the [release forum thread](https://forum.zdoom.org/viewforum.php?f=1). Come hang out!

# How to play

1. Unpack the release archive into a folder of your choice.
2. To play, you will need to own a copy of one of the supported games, such as Doom, Heretic, Hexen, etc.
   - Doom, Heretic, Hexen and Strife can be purchased on Steam. Any version will work, including the modern remasters.
   - [Chex Quest](https://store.steampowered.com/app/804270/Chex_Quest_HD) can be downloaded from Steam for free.
   - You can also download [Freedoom](https://freedoom.github.io/download.html) for free. Freedoom is a free "reskin" of Doom: it uses the same weapons and enemies, but features custom assets and maps, so it doesn't interfere with the actual Doom IP. (You can learn more about Freedoom [here](https://freedoom.github.io/about.html).)
3. Either copy the game's core .WAD file (such as doom.wad, doom2.wad, tnt.wad, evilution.wad, hexen.wad, strife1.wad, chex.wad) into the same folder as UZDoom, or just have those games installed - UZDoom will automatically parse your Steam games folder and find those .WAD files.
4. Start uzdoom.exe. Pick the game you want to play from the list and hit "Play game."

## How to play with mods

<details><summary>Standalone mods</summary>

Technically, these are not "mods" but rather standalone games made for the UZDoom or compatible engine. Often, they will come with their own build of UZDoom (or another port like GZDoom), but can still be launched in your copy of UZDoom. These projects come with their own maps and assets and don't need anything besides UZDoom to be playable: simply copy all PK3/IPK3/WAD files that come with the project into your UZDoom folder, launch UZDoom, and the project will appear in the list of games you can launch.

</details>

<details><summary>Non-standalone mods</summary>

Most ZDoom/GZDoom/UZDoom projects fall into this category. To play these, aside from the mod itself, you will an IWAD. An IWAD is a .WAD file from one of the main supported games: doom.wad for Doom, doom2.wad for Doom II, hexen.wad for Hexen, etc. The mod's description will tell you which IWAD you need; most mods are specifically made for Doom II, or Doom I, or another game. (Note, if you don't own Doom, you can substitute it with Freedoom WADs.)

Mods can be found on [Doomworld](https://www.doomworld.com/files/), [ZDoom Forums](https://forum.zdoom.org/viewforum.php?f=41), or [ModDB](https://www.moddb.com/games/doom/mods), although some have their own websites. Most of the time mods come in the form of a .PK3 or a .WAD file. It can also be several files — in this case refer to the mod's description/readme for information on what each of them does (for example, one file may contain maps, the other - sprites and sounds, etc.).

Note, not all mods will be compatible with UZDoom, so pay attention to what the mod's description says about the target source ports:

- Vanilla / DOS Doom, Limit Removing, Boom, MBF — mods made for these will always work in UZDoom (as well as any other source port)
- ZDoom or GZDoom — will usually work in UZDoom, unless the mod was made for a specific old version and relied on bugs or undocumented behavior that has since been patched
- Zandronum — may work if it doesn't rely on recent Zandronum-specific features
- EDGE, Eternity — will NOT work in UZDoom
- Anything else — there are quite a few ports, so this list is not exhaustive; when in doubt, the fastest way to check is to test.

Once you have that sorted out, you have one of several options:

Windows:

- Option 1: Drag & drop the mod's archive on top of uzdoom.exe.
- Option 2: Launch UZDoom with command line:
  - Windows: `uzdoom.exe -file "<path to mod file>"`
  - Linux: TODO
- Option 3: Use a launcher, such as [ZDL](https://github.com/lcferrum/qzdl/releases), [Doom Runner](https://github.com/Youda008/DoomRunner/releases) or others (you can learn more about available launchers on [The Doom Wiki](https://doomwiki.org/wiki/Launcher#Standalone_launchers)).

Linux: TODO

After launching, will be prompted to pick an IWAD — pick the one mentioned in the mod's description (usually, doom2.wad or freedoom2.wad), and the game will start with a mod.

Some mods can be combined with each other: for instance, map packs that don't feature custom enemies or weapons can be combined with gameplay mods that *only* feature weapons/enemies but no maps. However, multiple mods of the same type (such as two gameplay mods) will usually be incompatible.

</details>

# Frequently Asked Questions

<details><summary>How is UZDoom different from GZDoom and ZDoom?</summary>

ZDoom, GZDoom and UZDoom belong to the same family of source ports that started with ZDoom. ZDoom was discontinued in 2016, its latest version was 2.8.1.

GZDoom picked up from that point. While not "officially" discontinued, after version 4.14.2 in 2025 most of its developers moved on to UZDoom.

UZDoom is a fork and a direct continuation of GZDoom. At the moment, it aims to support everything that was available in the latest GZDoom dev builds prior to the move, and to add more features in the future. It maintains full reverse compatibility with GZDoom.

</details>

<details><summary>I have a mod that worked in ZDoom/GZDoom but doesn't work in UZDoom. What do I do?</summary>

The simplest (albeit inconvenient) solution is to play it in the version of ZDoom/GZDoom that was the latest at the time of the mod's release. If you are sure the mod *should* work on UZDoom but doesn't, contact the developer and let them know. If the developer is unreachable or isn't interested in fixing it, somebody else could probably develop a patch, but this may require a lot of scripting experience. You may try asking for help on [ZDoom Forums](https://forum.zdoom.org/viewforum.php?f=121) or the [Official ZDoom Discord server](https://dsc.gg/zdoom).

If you are sure that the mod isn't working on UZDoom because of a bug, you can [make a bug report](https://github.com/UZDoom/UZDoom/issues), although it's best if the mod's author does it, since they will likely be able to pinpoint the issue faster.

</details>

<details><summary>I'm having performance problems. What can I do?</summary>

First, some notes about UZDoom's performance in general:

- It's not just Doom; while it's based on Doom's source code, it comes with multiple features, so it would be unreasonable to expect it to run as well as the 1993 version of the engine.
- UZDoom (like GZDoom and ZDoom before it) aims to keep fulll reverse compatibility with all projects made for it, which at this point span over 2 decades. This prevents it from introducing some radical changes that could potentially improve performance.
- UZDoom's user base uses wildly different hardware, making it difficult to accommodate everyone.
- Most players play UZDoom with mods, but those mods can be unoptimized themselves — this has nothing to do with the engine itself, because it's not possible to optimize things like a mod spamming large volumes of in-game objects or high-resolution assets.

As for the steps you can take:

- Try playing without mods. If UZDoom performs fine, the problem is likely with the mods. If the performance issues arrise with *your own* project, it's time to think about optimization. Check [this article on ZDoom Wiki](https://zdoom.org/wiki/Optimizing_ZDoom_projects) and consider asking for help on the forums and/or [our Discord server](https://dsc.gg/zdoom).
- If your hardware is very old, you could try [LZDoom](https://zdoom.org/downloads). It's another fork of GZDoom that has largely the same features as UZDoom but more performant rendering. Note, it does not support certain rendering features.
- Some specific mods designed for different versions of Doom simply don't perform very well under ZDoom-based ports.</details>

<details><summary>How can start making my own project for UZDoom?</summary>

You will need [SLADE](https://slade.mancubus.net/index.php?page=news) to manage your project folder/archive and [Ultimate Doom Builder](https://ultimatedoombuilder.github.io/) to make maps, plus whatever other software you want to use to create assets (sprites, sounds, music, 3D models, etc.). There isn't a single all-encompassing guide on how to start modding, but here are some resources:

* [ZDoom Wiki](https://zdoom.org/w/index.php?title=Main_Page)
* [Getting Started with GZDoom/UZDoom Modding](https://dileepvr.github.io/gzdoom_modding_101/) by dileepvr
* [ZScript Basics](https://jekyllgrim.github.io/ZScript_Basics/) by Agent_Ash (jekyllgrim)
* [Ultimate Doom Builder Tutorials](https://youtube.com/playlist?list=PLQrQ055Wd7p77pBCmTQT6kW-K8Plmw_D-&si=Nskzqcn4Ffh02Nm3) by Bridgeburner

Other than that, feel free to ask for help on [ZDoom Forums](https://forum.zdoom.org/viewforum.php?f=121) and [our Discord server](https://dsc.gg/zdoom).

</details>

<details><summary>Can I use UZDoom to make a standalone game?</summary>

Yes! There are plenty of games that have already been released or are in development for this engine (or one of its versions). UZDoom is an open-source project under [GNU General Public License ver. 3](https://www.gnu.org/licenses/quick-guide-gplv3.html), which allows commercial use. Note, for the same reason (being open-source) UZDoom is not available on consoles, so your game will only work on PC.

</details>

# Resources

* [Compilation](https://github.com/UZDoom/UZDoom/wiki/Compilation) - instructions on compiling UZDoom
* [ZDoom Wiki](https://zdoom.org/w/index.php?title=Main_Page) - UZDoom engine documentation and editing guides
* [SLADE](https://slade.mancubus.net/index.php?page=news) - archive manager for creating/editing UZDoom mods
* [Ultimate Doom Builder](https://ultimatedoombuilder.github.io/) - map editor for all Doom-engine games and ports
