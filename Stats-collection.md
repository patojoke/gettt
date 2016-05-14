When a get5 match is live, the plugin will automatically record match stats for each player, across each map in the match. These are recorded in an internal KeyValues structure, and are available at any time during the match (including the postgame waiting period) via the ``Get5_GetMatchStats`` native and the ``get5_dumpstats`` command.

## Stats KeyValues structure
The root level of the KV contains data for the full series: the series winner (if one exists yet) and the series type (bo1, bo2..., etc).

Under that root level, there is a level for each map ("map1", "map2"), which contains the map winner (if one exists yet), the mapname, and the demo file recording.

Under the map level, there is a section for each team ("team1" and "team2) which contains the current team score (on that map) and the team name.

Each player has a section under the team level under the section name of their steam64id. It contains all the personal level stats: name, kills, deaths, assists, etc.


## What stats are collected
See the [get5 include](https://github.com/splewis/get5/blob/master/scripting/include/get5.inc#L106) for what stats will be recorded and what their key in the keyvalues structure is.

## What to do with the stats
