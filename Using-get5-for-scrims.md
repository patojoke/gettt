While get5 is intended for matches (league matches, lan matches, cups, etc.), it can be used for everyday scrims/gathers/whatever as well. If that is your use case, you should do a few things differently.

Note: these features are new to the 0.5.0-dev builds.

## Cvars

By default, get5 kicks all players from the server if no match is loaded. You should disable this for a practice server. To do so, edit ``cfg/sourcemod/get5.cfg`` and change:
- ``get5_kick_when_no_match_loaded 0``: this will enable players to join before starting

## Adding your team's steamids

You **must** edit [addons/sourcemod/configs/get5/scrim_template.cfg](https://github.com/splewis/get5/blob/master/configs/get5/scrim_template.cfg) and add your team's players to the "team1" section by their steamids (any format works). Any other player on the server will implicitly be on "team2".

## Starting the match

Rather than creating a [match config](https://github.com/splewis/get5#match-schema), you should use the ``get5_scrim`` when the server is on the correct map. You can use this via rcon (``rcon get5_scrim``) or as a regular console command if you have the sourcemod changemap admin flag. You could also type ``!scrim`` in chat.

This command takes optional arguments: ``get5_scrim [other team name] [map name] [matchid]``. For example, if you're playing fnatic on dust2 you might run ``get5_scrim fnatic de_dust2``. The other team name defaults to "away" and the map name defaults to the current map. matchid defaults to "scrim".

Once you've done this, all that has to happen is teams to ready up to start the match.

## Changing scrim settings

You can (and should) edit [addons/sourcemod/configs/get5/scrim_template.cfg](https://github.com/splewis/get5/blob/master/configs/get5/scrim_template.cfg). In this you can set any scrim-specific cvars in the ``cvars`` section. 

The default settings will playout all 30 rounds and shorten up the halftime break.