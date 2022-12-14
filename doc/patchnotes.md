**Legend**
> new : New features  
> chg : Change in existing functionality  
> dep : Soon-to-be removed feature  
> rmv : Removed feature  
> fix : Bug fixes.  
> sec : Security, in case of vulnerabilities.  
> ... : Part of the feature listed above it
---

```
# TODO
new : ogg loading
new : Menu items use a scale property (was hardcoded to scale = 1)
chg : Text drawing: Vertical alignment support
new : Kua logo
chg : UI color scheme, not Q3 based
new : YAML based Settings menu (libcyaml)
new : Move credits to its own menu item (lower right corner)
chg : Credits menu goes back to StartMenu
new : SQlite based Play menu
new : Basic Settings menu
new : UI asset palette (debug mode)
bld : Reduced release download filesize (curl and other deprecated libs/binaries are no longer packed)
fmt : Removed qboolean
fmt : Formatted the whole project with clang-format

chg : Map Loading screen
... : Aspect correct image
... : Unknown map shader
... : Check weapon icons
... : Font drawing
... : Gametype struct

bld : Freetype2 windows compiling
new : List items can be double clicked
```

```
new : Basic Play menu
... : Fixed ugly Roboto aliasing
... : Maplist background (? maybe ?)
... : Font color non-selected
... : Map thumbnail
... : List Item mouse selection boundaries
... : Image Item mouse selection boundaries
```

---
# Unreleased
## 0.35a
2022.11.22  
```
new : UI Accept icon
```

2022.11.18  
```
new : Image menu items now draw with the new UI coordinate system
```

2022.11.17  
```
new : New Assets licensing notice
```

2022.11.17  
```
new : Random song on loading (TODO: fix big files crashing the engine)
chg : New UI feedback sounds (move, cancel, error, silence)
new : UI Cancel icon
new : Entering the game for the first time now plays a song.
fix : Menu item mouse selection (core.c/uiEvent_mouse)
```

2022.11.16  
```
chg : Cleaner Exit confirm menu (no credits)
fix : Exit confirm background drawing correctly
chg : Alternative background is now the main background but darkened, to make it more seamless
chg : menuBack and menuBackNoLogo renamed to bgMain and bgAlt
chg : showlogo menu property renamed to isMain
```

2022.11.15  
```
new : Logo Background (temporarily Q3, will be changed for Kua when its made)
fix : Cursor constraints are now aspect correct
new : Start menu now uses fonts !!
new : Font file: heyNovember (used for ActionKey)
new : Font type: Action (temporarily uses Roboto, could be changed)
new : PText menu items now draw with fonts
new : TextDraw now accepts styling (pulse, shadow and inactive)
chg : UI_INVERSE renamed to UI_INACTIVE
new : UI: Multiple default font types
```

2022.11.03  
```
new : UI font support
```

2022.11.03  
```
doc : License text: Changed name to Kua, was osdf
bld : New ui is now default. Windows version disconnected temporarily
```

2022.10.31  
```
new : Automatic updater/downloader app. Simple version, will be upgraded over time. Made with nim/raygui
```

2022.10.19  
```
chg : Recent item pickups now draw in the middle-bottom third of the screen, and use the default font for their text.
chg : Score points now show on the top left third of the screen when active, and use the default font.
chg : Scoreboard drawing has been temporarily disabled (drawing is requested, but nothing is shown. Requires an entirely new scoreboard)
```

2022.10.18
```
chg : Powerups now draw in the bottom-center of the screen. They don't show a timer if they have > 99s left
chg : Default model changed from "sarge" to "ranger/blue"
chg : Changed Hud icons to be 2D by default (temporary until new models). Can be reverted with `cg_draw3Dicons 1`
chg : Gauntlet is now the default weapon on first spawn. Doesn't change behavior on /kill (aka. preserves previous weapon)
chg : Changed status and powerup colored numbers to something more reasonable than the default in-your-face yellow/red.
chg : Most HUD elements have been fixed to draw with aspect correct ratio
chg : cg_gun* cvars no longer locked as cheats. cg_gunX default changed from 0 to 7
```

2022.10.17
```
chg : Speedometer, fps meter, skim, holdboost, crouchslide and run timers, all now use font to draw
new : Game+Engine Version text drawing on the bottom right of the screen
new : Default Font: Roboto Bold 16pt
new : New function in cg_draw to draw Text using fonts. TODO: vertical alignment and font size improvements.
fix : Run mode: Fraglimit set to 0 in some places that was missing
chg : Model cvars renamed: (headmodel, team_model, team_headmodel) = (model_playerhead, model_team, model_teamhead);  (TODO: model to model_player)
new : Cvar hud_fontFile : Path of the standard font. Will use FONT_DEFAULT_FILE if empty
new : Cvar hud_fontSize : Size of the standard font. 0=FONT_DEFAULT_SIZE; negative=12pt
new : Created CG_Text* drawing functions, based on TeamArena code. They expect a valid fontInfo and do not hardcode any fonts
```

2022.10.16
```
bld : Several bug changes and fixes to python/tools
chg : r_saveFontData default changed from 0 to 1
chg : Renderer1 font system now stores data files to cache/fonts/ instead of just fonts/
bld : Added a pkg-config parse entry for Freetype2 to the Linux Engine. Will need revision for windows support
new : Renderer1 Freetype2 font support now enabled by default (needs compiler key to disable, instead of the opposite like before)
```

2022.10.01  
```
fix : Several bug fixes to the build.py and run.py scripts
new : build.py script now accepts cleaning option
new : New confy.python utility functions. rm, toPath, isPath, etc
chg : confy.python tools now always use pathlib.Path objects
new : (VQ4) Crouch-jumping is now possible
new : (VQ1) Crouch-jumping is now possible
new : Engine -> Support for independent jump-crouch inputs
chg : Updated roadmap. All osdf goals ported to the new file. Needs prioritization and version planning.
chg : Changed all OSDF code change keys to KUA
```

2022.09.30  
```
chg : Updated roadmap, to better reflect Kua goals
chg : Engine -> map_restart default delay changed from 5sec to 0
fix : Config files restored. Were being wiped out by the automated packing script
new : Resources folder. Autopacked with the buildscript
new : Added script to run the game from the root folder. For easier access and file updating on version change
new : Automated buildscript changed to python
dep : Automated nimscript buildscript moved to root. Will be removed eventually
chg : Jumped version to 0.35a, to indicate the shift from osdf-gpl to Kua
chg : Changed versioning system from X.X.X to X.XXa
chg : Engine and Game repositories merged into Core. Modules sounded good on paper, but were really clumsy to work with
```
... :  

# History
## 0.3.0
_v0.3.0-r0_  
2022.08.04  
```
fix : Fixed a buildsystem bug. After changing to SCons nodes, the engine wasn't being built
```

2022.07.18  
```
new : Initial accel hud code has been added to the buildsystem. Currently inactive (WIP)  
```

2022.07.15  
```
new : (VJK) New Mechanic: Jump Holdboost  
   ..  While holding jump, and moving at +375ups, you get extra jumpvel on each jump (375 is 1.5x of 250basespeed)  
   ..  It will reach the same heigh than vq3 in 8jumps, but will keep growing  
   ..  Starts at 225 base jumpvel, and increases by 5u each jump  
   ..  5u is 12% of 45. Which is the difference between vq3 and vjk jumpvel (270-225)  
new : (VJK) HoldBoost hud element  
```

2022.07.14  
```
new : Sound event control system in cg_event.c  Can be used to stop any type of sound spam (autojump, rampslides, etc)  
new : (CQ3) New physics: VQ3 aircontrol, with CPM tech (dj/ramps/slick/etc)  
```

2022.07.13  
```
new : pm_time hud element   (mainly related to skimming, but general purpose)  
```
```
new : New mechanic: Rampslides from Q2  (currently active for VQ4 physics)  
chg : (VQ1) Added Q3 Overbounces  
fix : (VQ1) Fixed visual glitch on physics change without `/map` command  
fix : (VQ1) Fixed downramps sometimes not giving a speed boost
new : (VQ1) New mechanic: Feetraise
... :       Crouching mid-air raises your feet by 14u (sbj). Allows jump to reach higher and further.  
new : (VQ4) Crouching mid-air raises your feet by 12u (sbj). Allows jump to reach higher and further.  
```

2022.07.12  
```
fix : (VQ3) Fixed upramps giving the wrong amount of velocity on jump  
chg : (VJK) Reverted jumpvel back to 225 (in preparation for a new jump height mechanic)  
```
```
new : (VQ4) New physics : Quake 4 Inspired.  Activate with `/exec phy_vq4`  
   ..       Will have crouchsliding, rampslides (from q2/q4) and vq3 aircontrol  
new : (VQ4) Set groundaccel to 15 (same as original Q4 and cpm)  
new : (VQ4) New mechanic: Crouchslide  
   ..       Earns 2x frames of crouchslide per 1x frame spent in the air, capped at 2000ms   
   ..       Has 0 friction, and a separate accel value of 20  (could change after testing)  
```

## 0.2.0
2022.06.21  
_v0.2.0-r0_  
```
new : OBfix. Applied on SURF_NOOB surfaces (cvar to be done)
chg : bg_pmove restructure. Moved all custom code to phy/ subfolder
```

2022.06.20
```
new : Initial work on Strafehud porting. Not connected, but doesn't break compiling
chg : (VJK) Changed jumpvel from 225 to default vq3 (270), to allow easier clearing of defrag maps
```
```
fix : (Q1) "Stepdown" bug is fixed (wasn't stepdown, it was q1 downramp behavior happening on incorrect dotproduct)
fix : (Q1) W/S movement working properly in q1 physics  
fix : (Q1) Crouch works again in q1 physics  
fix : (Q1) Surf ramps no longer stick you to the ramp on exit
new : (Q1) Variable Jump Heights. Activated with +speed. 
... :      Flatground = x0.5 jumpvel
... :      Downramps behave like q1 (additive, based on your current Zvel)
... : (code) VectorReflectOS. Sets backoff = 0 when facing away from the surface
```

2022.06.18  
```
chg : CPM Item Pickup: Above size increased from 36u (32u doesn't trigger) to 66 (62u doesn't trigger)  
new : VJK physics. VQ3 with 4airaccel, 12groundspeed, 250speed and 225jumpvel. `/exec phy_vjk`  
```
```
chg : Moved all custom bg_pmove.c code into subfolder sgame/phy/  (not connected to the buildsystem yet)   
new : Added basic buildsystem instructions (sketch)  
... : Added Native windows build instructions for the `chocolatey/mingw` method  
... : Added disclaimer for WSL cross-compilation  
new : Initial edits to the buildsystem for native windows compilation  
... : Fixed native win32 SCons environment resolution  
... : Changed file path resolution, so that it remains system-agnostic (uses SCons Nodes wherever possible)  
```

2022.06.11
```
fix : CPM Rocket Launcher: Vertical self knockback scaling reduced to 1  
```

2022.06.10  
_v0.2.0-r0_  
```
new : (cfg) VM configuration disables QVM loading (vm_cgame 0, vm_game 0, vm_ui 0)  
new : (cfg) Server Pure is deactivated, to allow Library Loading (sv_pure 0)  
new : Buildsystem ported to SCons. No longer uses make  
... : Buildsystem handles Cross-Compiling for both win/lnx  
... : Libraries are not packed in a .pk3 (they don't work from inside one)  
... : Buildscript creates and zips both platform binaries  
new : Custom fork of oDFe. Loads osdf mod directly
rmv : Removed bash shell script for launching the mod (was system dependent)  
```
```
chg : CPM Rocket Launcher: Self knockback increased to 1.2  
fix : /cpm and /vq3 commands now work with osdf
```

2022.05.10  
```
rmv : Removed bash shell script used for automating the build process. Temporarily stored in `+` subfolder, but will be deleted.
new : Linux automated build script has been fully rewritten in nimscript (bash becomes {cr}ypt!$C real fast)  
chg : The build system no longer compiles into QVM by default. It creates Dynamic Libraries instead.  
dep : This mod will no longer support the QVM architecture moving forward. Incoming features will make the mod fully incompatible with QVM compilation  
```

## 0.0.2
```
new : Local Timer. Best per session. All maps have TimeReset (temporary hack until better Timer support)  
new : target_startTimer entity support  
new : target_stopTimer entity support  
```
```
new : Full cpm strafing (double jumps, slick haste, telejumps, stairjumps, rampjumps, etc)  
new : CPM weapon behavior  
... : Instant weapon switch on CPM  
... : Rocket Launcher speed increased from 900 to 1000  
chg : Q1-qw deactivated. Q1 physics default to AG-style  
new : Q1 AD movement, balanced similarly to QW (77fps/32as/100aa)  
new : Q1 AD movement, balanced similarly to AG (125fps/35as/100aa)  
new : Physics type Selection (phy_movetype NUMBER .. 0=CPM, 3=VQ3, 1:Q1-ag)  
```
```
new : Initial Main Menu UI layout, background and theme
```

## 0.0.1
```
new : Basic cpm strafing (Correct accel, aircontrol and A/D strafing)  
new : Instant respawn.   
... : player_die() has no delay.   
... : g_forcerespawn now means miliseconds, instead of seconds  
... : g_forcerespawn default value changed to 1. Previous behavior is now `g_forcerespawn 20000`  
new : Gamemode "run" (basic). Replaces FFA, `g_gametype 0`  
... : Powerups no longer drop on dead
chg : Changed default pmove_fixed value to 1. It doesn't need to be changed by cfg to work correctly.  
new : Created default .cfg files. Solves pmove_fixed not being used automatically, and some other configuration basics.  
```
```
new : Basic Linux automatic qvm compiling setup. Script at: src/qvm.sh  
... : Automated compilation from makefile  
... : Automated packing  
```

## 0.0.0 (Mod Compiling Basics)  
```
new : Initial setup & compilation (manual)  
... : Changes to the code actually affect gameplay through `.qvm` files  
```
```
.. Worked by default  
: Surface flags (uses shader properties)  
: Vq3 movement (`pmove_fixed 1`)  
: Vq3 Weapons  
: Vq3 Teleports  
: vq3 Hurt Trigger  
: target_score  
: Map loading  
```

# TODO
#..............
_Urgent    : Cause us to react. We stop what we're currently doing and work on the urgent task instead._
_Important : Lead us towards our mission/goals. Require planning, organization and initiative._
#..............
# 1 : IMP.URG : Critical
#.............:

#...............
# 2 : IMP.notU : Planned Goals
#..............:

#...............
# 3 : notI.URG : Non-critical Fixes
#..............:

#................
# 4 : notI.notU : Implement when possible
#...............:
