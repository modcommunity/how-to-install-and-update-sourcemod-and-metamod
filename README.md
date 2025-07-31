A guide on how to **install** and **update** both [MetaMod](https://www.sourcemm.net/) and [SourceMod](https://www.sourcemm.net/).

[**View Guide On TMC (Recommended Due To Better Formatting)**](https://blog.moddingcommunity.com/how-to-install-update-sourcemod-metamod/)

## Table Of Contents
* [Requirements](#p-66-requirements-1)
* [How To Install MetaMod](#p-66-how-to-install-metamod-2)
    * [Updating](#p-66-updating-3)
    * [Confirmation](#p-66-confirmation-4)
 * [How To Install SourceMod](#p-66-how-to-install-sourcemod-5)
     * [Updating](#p-66-updating-6)
     * [Confirmation](#p-66-confirmation-7)
* [Games That Utilize MetaMod & SourceMod](#p-66-games-that-utilize-metamod-sourcemod-8)
* [What Is MetaMod (MM)?](#p-66-what-is-metamod-mm-9)
* [What Is SourceMod (SM)?](#p-66-what-is-sourcemod-sm-10)
* [See Also](#p-66-see-also-11)

## Requirements
* A [SRCDS](https://developer.valvesoftware.com/wiki/Source_Dedicated_Server#:~:text=The%20Source%20Dedicated%20Server%20or,same%20computer%20as%20they%20can.) server running on Windows, Linux, or Mac.
* Access to the SRCDS file system (e.g. FTP or File Explorer).
* If your client is running Windows and your server is running Linux/Mac, you'll need a file archiver/extractor application such as [7-ZIP](https://www.7-zip.org/).

## How To Install MetaMod
MetaMod is required to run SourceMod. Therefore, I typically install MetaMod first.

1. Download the correct package for your operating system [here](https://www.metamodsource.net/downloads.php).
2. Extract the downloaded file using ZIP or Tar/GZIP for example.
3. Copy the **addons/** folder from your extracted file to your server's main game directory. For example, on Counter-Strike: Source, this would be **/path/to/server/cstrike/**. Team Fortress 2 would be **/path/to/server/tf/**.

If it asks you to override folders or files, select yes. After installation, ensure you have a **metamod.vdf** file located in the **addons/** folder. All recent versions of MetaMod should include this file already, but if there isn't a **metamod.vdf** file, you may generate one [here](https://www.metamodsource.net/vdf).

### Updating
1. Shut down your game server (technically, on Linux you won't have to, but the server may crash after map change).
2. Perform steps 1 - 3 above.

### Confirmation
To confirm MetaMod is installed on the game server, you may run the **meta version** command to verify the version installed. If you receive an "unknown command" error, MetaMod was not installed properly.

```
meta version
 Metamod:Source Version Information
    Metamod:Source version 1.12.0-dev+1165
    Plugin interface version: 16:14
    SourceHook version: 5:5
    Loaded As: Valve Server Plugin
    Compiled on: Dec 19 2022 17:29:31
    Built from: https://github.com/alliedmodders/metamod-source/commit/63c5c15
    Build ID: 1165:63c5c15
    http://www.metamodsource.net/
```

## How To Install SourceMod
To install SourceMod, use the following steps.

1. Download the correct package for your operating system [here](https://www.sourcemod.net/downloads.php?branch=stable).
2. Extract the downloaded file using ZIP or Tar/GZIP for example.
3. Copy the **addons/** and **cfg/** folders from the extracted file to your server's main game directory. For example, on Counter-Strike: Source, this would be **/path/to/server/cstrike/**. Team Fortress 2 would be **/path/to/server/tf/**.

### Updating
1. Shut down your game server (technically, on Linux you won't have to, but the server may crash after map change).
2. Follow steps 1 and 2 from above.
3. Copy all folders and files in the extracted file's **addons/sourcemod/** folder **excluding** the **configs/** folder to your game server's SourceMod directory. For example, on Counter-Strike: Source, this would be **/path/to/server/cstrike/addons/sourcemod/**.

The reason we exclude the **configs/** folder is to prevent overriding any custom configuration you had such as the common **databases.cfg** file.

### Confirmation
To confirm SourceMod is installed on the game server, you may run the **sm version** command to verify the version installed. If you receive an "unknown command" error, SourceMod was not installed properly.

```
sm version
 SourceMod Version Information:
    SourceMod Version: 1.11.0.6926
    SourcePawn Engine: 1.11.0.6926, jit-x86 (build 1.11.0.6926)
    SourcePawn API: v1 = 5, v2 = 16
    Compiled on: Dec 20 2022 14:00:51
    Built from: https://github.com/alliedmodders/sourcemod/commit/fd63fff8
    Build ID: 6926:fd63fff8
    http://www.sourcemod.net/
```

## Games That Utilize MetaMod & SourceMod
Here is a small list of games where community and modded game servers utilize MetaMod and SourceMod. Keep in mind there are other games outside of this list as well.

* Half Life 2
* Counter-Strike: Source
* Counter-Strike: Global Offensive
* Team Fortress 2
* Left 4 Dead 1/2
* Day of Defeat: Source
* Zombie Panic: Source
* Fistful of Frags

## What Is MetaMod (MM)?
[MetaMod](https://www.sourcemm.net/) is a C++ plugin for Valve's Half Life 2/Source Engine that allows other plugins/addons such as SourceMod to operate. Here is the full description from AlliedModders.

> Quote
>
>
>
>
>
> Metamod:Source is a C++ plugin environment for Half-Life 2. It acts as a "metamod" which sits in between the Game and the Engine, and allows plugins to intercept calls that flow between. It provides a mechanism called SourceHook, a very powerful library for intercepting, overridding, and superseding virtual function calls.
>
>
>
> Although Valve provides their own C++ plugin environment, we found two major reasons to develop Metamod:Source:
>
>
>
> 1. If separate plugins use their own hooking mechanisms, conflicts will arise. The centralized SourceHook environment solves that by providing a unified gateway.
> 2. Valve's layer has idiosyncracies, such as not fully unloading from memory and poor console and programmatic control. Metamod:Source is explicit, flexible, and open source.
>
>
>
> It is important to note that Metamod:Source is not the same as "Mani Admin Plugin," "SourceMod," or "EventScripts." It is a very small library wrapper designed to load and pass a few pointers to C++ plugins. It provides almost no unneeded functionality (such as gameplay mods or MySQL support) and incurs no overhead on its own.
>
>
>
> Metamod:Source is licensed under a very liberal, open-source license. You are not required to release any source code to your plugins, as the license allows commercial/proprietary use. (Note that you might have to follow the license agreements of third-party software, such as Valve SDKs or other libraries.)

## What Is SourceMod (SM)?
[SourceMod](http://sourcemod.net/) is an addon to MetaMod that allows users and server owners to script/develop plugins using its own programming language, SourcePawn. It also comes with commands and tools that makes server administration a lot easier. Here is the full description from AlliedModders.

> Quote
>
>
>
>
>
> SourceMod is server modification for any game that runs on the Half-Life 2 engine. It is a powerful, highly optimized platform for scripting plugins and handling server administration. The default package comes with a base set of plugins, but there are over 2,500 plugins in the community.
>
>
>
> **Basic Features (Users)**
>
>
>
> * An easy to use, deeply fine-grained permissions system (SQL compatible)
> * A highly configurable admin menu
> * Reserved slots
> * Flexible map management plugins (nominations, rock the vote, etc)
> * Basic commands such as kicking/banning/slapping/muting players, changing cvars, etc
> * Various voting commands
> * Chat spam protection
> * Comprehensive chat triggers for both users and administrators
> * Easily translatable
> * SourceMod is highly optimized and ideal for getting the most performance out of your Source servers, without the complexity of writing C++ code.
>
>
>
> **Scripting Features (Developers)**
>
>
>
> * Administration - Comprehensive API for developing administration systems.
> * Clients - Working with in-game client information and callbacks.
> * Commands - Creation, hooking, and overriding of client and server console commands.
> * ConVars - Creation, hooking, and retrieval of console variables.
> * Database - Abstracted database access.
> * Engine - Access to many Half-Life 2 engine features, with more constantly being added.
> * Entities - Changing and retrieving entity properties, both named and numbered.
> * Events - Creating, firing, and hooking of Half-Life 2 GameEvents.
> * Files - Access to the filesystem.
> * IPC - Advanced inter-plugin communication, similar to AMX Mod X.
> * Menus - Abstracted menu API for creating uniform menus across mods
> * Messages - Sending and hooking UserMessages.
> * Parsing - Advanced, highly optimized text parsing.
> * Timers - Creation of timed events.
> * Translation - Multi-Lingual phrase file lookup.
>
>
>
> **What makes SourceMod different? (Developers)**
>
>
>
> * **Speed** - SourceMod is lightning fast, and this is not an idle boast. Every plugin is loaded into memory and converted to raw CPU code. Great care is taken to make sure every hot area in SourceMod is as fast as it should be. The scripting language is statically typed and does not require garbage collection.
> * **API** - The majority of work in SourceMod occurs in making the API the best we can. When adding any interface or function, we ask the following questions:
> * Does it represent an optimized solution?
> * Would anyone use it?
> * How confusing is it?
> * Does it match the most probable common usage?
> * Will it be possible to extend it in the future?
> * Does its name represent what it does?
> * Does its name conform to other similar functions?
> * **Extensibility** - SourceMod is completely extensible. SourceMod provides a complete C++ API for extending both SourceMod and the Plugin event/native API.
> * **Open-Source** - SourceMod, its extensions, and its plugins, are all open source under the GNU General Public License!

## See Also
* [How To Manage User Permissions In SourceMod](https://blog.moddingcommunity.com/how-to-compile-sourcemod-plugins/)
* [How To Compile SourceMod Plugins](https://blog.moddingcommunity.com/how-to-compile-sourcemod-plugins/)

## Conclusion
That's it! By now you should know to install and update both SourceMod and MetaMod.

If you have any questions or feedback, please reply to this topic!