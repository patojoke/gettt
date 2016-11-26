get5 contains an event-logging system that logs many client actions and what is happening in the game. These supplement the logs CS:GO does on its own, but adds additional information about the ongoing match.

An "event" is a json object that looks something like this:
```
{
    "matchid": "1",
    "event": "series_start",
    "params": {
        "team1_name": "EnvyUs",
        "team2_name": "Fnatic"
    }
}
```

Events will have variable parameters depending on what type of event it is. In the example, we see the event name is "series_start". All events include the "matchid" field and have a name under "event".

## Interfacing with events

From a plugin, you can use the ``void Get5_OnEvent(const char[] eventJson);`` forward to do anything you like with get5 events. 

You can also use the builtin ``logaddress_add`` command to add a server ip:port that is listening to the game server log and reading events (it could also read plain CS:GO server log lines - this is what eBot does).

Finally, events can be logged by setting the ``get5_event_log_format`` cvar, which will write out text that looks like:
```
L 11/26/2016 - 02:58:39: {
    "matchid": "example_match",
    "event": "series_start",
    "params": {
        "team1_name": "EnvyUs",
        "team2_name": "Fnatic"
    }
}
```
to a file. You'd have to do some processing to handle parsing the logging timestamp before each json event, but it isn't very hard (a simple regex replacement would be fine).  


## List of events

### Series flow
- series_start
- series_end
- map_veto
- map_pick
- side_picked

### Map flow
- knife_start
- knife_won
- going_live
- round_end
- map_end

### Client actions
- player_death
- bomb_planted
- bomb_defused
- bomb_exploded
- client_say

### Miscellaneous 
- match_config_load_fail
- backup_loaded
