NOTE: Script is unfinished. More lines and groups should be added. Contributions are welcome!
Report all issues here on github, or send PM to nullifiedcat on reddit

# Edgy Killfeed Script (now with Quake Sounds!)
_that's what a lime scout would use!_

[Watch the video!](https://www.youtube.com/watch?v=aOt3R-S4Y7k)

Quake sounds use `playsound.exe` on Windows and `aplay` on linux (needs `alsa-utils`). Please note that sounds are quite loud.

All lines are configurable. You can easily add new weapon groups, new lines for groups/specific weapons. Upcoming features include more customization, like weapon blacklists/whitelists, killstreaks, kill counters, etc.

If you want help me spreading the script, set `promotion` to `true` in `data/modtaunt.json`! (disabled by default) That will send promotional messages every 60 seconds (can be configured)

Windows version of script uses compiled AutoHotKey script to send keystrokes to Team Fortress 2 window

# Step-by-Step

## Windows (script release 4 and above)

1. [Download package](https://github.com/nullifiedcat/tfscript/releases) with nodejs executable and script itself
2. Unzip the package to any folder
3. Run `install.bat`. It will ask for your `tf` folder (if your steam library is installed in non-default location). `tf` it should be located at `SteamLibrary\steamapps\common\Team Fortress 2\tf`
4. Put your `uid` in `data/uid.txt` file. Instructions on finding your `uid` are below
5. You are ready, but you might want to customize your messages or settings
6. Run the script with `start.bat`

### If you don't like pre-compiled binaries

Compile `playsound.cpp` using any c++ compiler

Compile `keypress32.ahk` using `Ahk2Exe` from AutoHotKey (google it)

Install `node.js` package from [official site](https://nodejs.org/en/download/)

## Linux (Ubuntu/Debian)

1. Install `nodejs` package (`sudo apt-get install nodejs`)
2. Install `xdotool` package (`sudo apt-get install xdotool`)
3. Clone this repository into any folder
4. Run `install.sh`
5. Set your uid in `data/uid.txt` file. A method to find uid is described below
6. You are ready, but you might want to customize your messages or settings
7. Run the script with `node tfscript`

# How to find UID
`uid` looks like `[U:1:111111111]`

Use [this site](https://steamid.io/lookup) to find your **steamID3** from your profile link, or

1. Join any server or create your own (`map itemtest` in console)
2. Type `status` in console
3. Find a line with your name
4. Get your uid from that line
5. Put it into `data/uid.txt`

# Updating the script

Just [download ZIP](https://github.com/nullifiedcat/tfscript/archive/master.zip) and unpack everything to your script folder (replace old files)

# Configuration

Configs are stored in `data` folder

`uid.txt` should contain your `uid`
`config.json` file contains tfse settings, like game folder and interaction key (don't change it unless you know what you are doing)
`modtaunt.json` contains tftaunt settings
`modquake.json` contains quake sounds settings
`english.json` file contains all the lines you'll say when killing someone
`groups.json` file contains weapon groups to use in language file (example: group `rockets` contains The Direct Hit, Black Box, etc..)

_note: & symbol means crit kill_

# Special Thanks

* __Sam__ for testing the script on Windows
* __Dragonisser__ for testing the script on Windows

# Known bugs

`killStreak` doesn't reset when preparing time ends/next round starts. I can't think of any fix because match start doesn't log anything to console

All kills made using Australium weapons are interpreted as **crit** kills, this cannot be fixed without hooking into tf2

# Planned features

* Killstreak announcing
* Weapon whitelist and blacklist modes, for example, announce only headshot-penetrate kills or melee kills
* Localization files updates
* Kill counters (soon)
* Rough class detection based on weapon used for last kill and triggers for it (not very soon)
* Possibly even more
* Proper weapon names as $2 (for example `Stickybomb Launcher` instead of `tf_projectile_pipe_remote`)

Stay tuned!
