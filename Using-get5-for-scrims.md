While get5 is intended for matches (league matches, lan matches, cups, etc.), it can be used for everyday scrims/gathers/whatever as well. If that is your use case, you should do a few things differently.

Note: many of features are new to the 0.3.0-dev builds.

## Cvars

The default cvar values are fit for most match systems, so you should change their values. Edit ``cfg/sourcemod/get5.cfg`` and change the following cvars to these recommend values:
- ``get5_kick_when_no_match_loaded 0``: this will enable players to join before starting
- ``get5_demo_name_format "scrim_{TIME}_{MAPNAME}"``: this will make the recorded demo names more useful
- ``get5_check_auths 0``: this will disable team locking/steamid checking on client connections, so you should make sure the server has a password (this setting isn't required, but recommend for scrim/practice usage)
- ``get5_max_pause_time_per_half 0``: this sets unlimited pausing (300 seconds by default, also not required, but recommended)

## Starting the match

Rather than creating a [match config](https://github.com/splewis/get5#match-schema), you should use the ``get5_scrim`` when the server is on the correct map. You can use this via rcon (``rcon get5_scrim``) or as a regular console command if you have the sourcemod changemap admin flag. This will force playout of all 30 rounds and skip the knife round. 

Once you've done this, all that has to happen is teams to ready up to start the match.