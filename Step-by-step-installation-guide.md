This is meant to be a more comprehensive explanation of how to install than in the readme: https://github.com/splewis/get5#download-and-installation

Before you start, make sure the CS:GO server is not running.

#### 1. Install Metamod:Source
Download from http://www.sourcemm.net/downloads. Make sure you get the latest version and for your server's operating system. To install, just merge the download's ``addons`` directory with the ``csgo/addons`` directory on the server.

#### 2. Install Sourcemod 
Download from http://www.sourcemod.net/downloads.php. Make sure you get the latest version and for your server's operating system. To install, just merge the ``addons`` and ``cfg`` directory with the ``addons`` and ``cfg`` directories in the server's root ``csgo`` directory.

You may want to add youself as sourcemod admin, see https://wiki.alliedmods.net/Adding_Admins_(SourceMod). Otherwise, get5 commands will have to be used via rcon or directly on the server.

#### 3. Install get5

Extract the download archive into the csgo/ directory on the server. The only required file is actually just the ``get5.smx`` plugin binary in the ``addons/sourcemod/plugins`` directory. The example configs and plugin source code do not have to be uploaded.

You can download from either the [last release](https://github.com/splewis/get5/releases) or the [last development build](http://ci.splewis.net/job/get5/lastSuccessfulBuild/).

#### 4. Install SMJansson (optional)
Download the smjansson_2.3.1.3_binaries.zip archive from https://forums.alliedmods.net/showthread.php?t=184604. Then take either the .so file (linux server) or .dll file (windows server) and put it in the ``addons/sourcemod/extensions`` directory.

#### 5. Install SteamWorks (optional)

Download the smjansson_2.3.1.3_binaries.zip archive from https://forums.alliedmods.net/showthread.php?t=229556, specifically the latest build from http://users.alliedmods.net/~kyles/builds/SteamWorks/. Merge the ``addons`` directory in the download with the server's ``addons`` directory.

#### 6. Create a match config

The readme describes the match schema format: https://github.com/splewis/get5#match-schema

I recommend starting from the [example file](https://github.com/splewis/get5/blob/master/configs/get5/example_match.cfg) and modifying it. Note that many fields are optional. Only the "team1" and "team2" sections are actually required. So you can remove the "favored_percentage_team1" field, if you don't want it displayed/have no data for it.