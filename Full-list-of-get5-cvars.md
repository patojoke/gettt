Note: these are auto-executed on plugin start by the auto-generated (the 1st time the plugin starts) file ``cfg/sourcemod/get5.cfg``.

You should either set these in the above file, or in the match config's ``cvars`` section. Note: cvars set in the ``cvars`` section will override other settings.

## Pausing

- ``get5_max_pauses``: maximum number of pauses a team can use, 0=unlimited
- ``get5_max_pause_time``: maximum number of time the game can spend paused by a team, 0=unlimited
- ``get5_reset_pauses_each_half``: whether pause limits are reset each halftime period (default 1)
- ``get5_fixed_pause_time``: if nonzero, the fixed length all pauses will be
- ``get5_pausing_enabled``: whether pausing (!pause command) is enabled


## File name formatting

Note: for these, setting the cvar to an empty string ("") will disable the file writing entirely. Valid substitutions are (when surrounded by {}): TIME, MAPNAME, MAPNUMBER, MATCHID, TEAM1, TEAM2.

- ``get5_time_format``: time format string (default ``"%Y-%m-%d_%H``), only affects if a {TIME} tag is used in other file-name formatting cvars
- ``get5_demo_name_format``: format to name demo files in (default ``{MATCHID}_map{MAPNUMBER}_{MAPNAME}``)
- ``get5_event_log_format``: format to write get5 event logs to (default ``logs/get5_match{MATCHID}.log``)
- ``get5_stats_path_format``: path where stats are output each map end if set

## Backup system

- ``get5_last_backup_file``: last match backup file get5 wrote in the current series, this is automatically updated by get5 each time a backup file is written
- ``get5_max_backup_age``: number of seconds before a get5 backup file is automatically deleted, 0 to disable

## Miscellaneous

- ``get5_autoload_config``: a config file to autoload on map starts if no match is loaded
- ``get5_check_auths``: whether the steamids from a "players" section are used to force players onto teams (default 1)
- ``get5_kick_when_no_match_loaded``: whether to kick all clients if no match is loaded
- ``get5_live_cfg``: config file executed when the game goes live
- ``get5_live_countdown_time``: number of seconds used to count down when a match is going live
- ``get5_message_prefix``: The tag applied before plugin messages
- ``get5_stop_command_enabled``: whether the !stop command is enabled
- ``get5_time_to_start``: time (in seconds_ teams have to ready up before forfeiting the match, 0=unlimited
- ``get5_time_to_make_knife_decision``: time (in seconds) a team has to make a !stay/!swap decision after winning knife round, 0=unlimited
- ``get5_warmup_cfg``: config file executed in warmup periods