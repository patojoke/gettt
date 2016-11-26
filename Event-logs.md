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


## List of events and their params

Some rules are followed in these settings:

1. "Winner" is a match team, i.e. "team1" or "team2"
1. "team" is a match team, i.e. "team1" or "team2"
1. "side" is a CS team, i.e. "CT" or "T"
1. "map_number" is 0-indexed
1. client fields ("client", "attacker", "victim", etc.) will use %L sourcemod formatting
1. "site" is "A" or "B"

### Series flow
- ``series_start``:
    * team1_name
    * team2_name

- ``series_end``
    * team1_series_score
    * team2_series_score
    * winner 

- ``map_veto``
    * team 
    * map_name

- ``map_pick``
    * team 
    * map_name
    * map_number

- ``side_picked``
    * team
    * map_name
    * map_number
    * side 

### Map flow
- ``knife_start``
    * map_name
    * map_number

- ``knife_won``
    * map_name
    * map_number
    * winner
    * selected_side
    
- ``going_live``
    * map_name
    * map_number
    
- ``round_end``
    * map_name
    * map_number
    * winner_side
    * winner
    * team1_score
    * team2_score
    
- ``map_end``
    * map_name
    * map_number
    * winner
    * team1_score
    * team2_score
    

### Client actions
- ``player_death``
    * map_name
    * map_number
    * attacker
    * victim
    * headshot
    * weapon
    * assister (optional)
    * flash_assister (optional)
    
- ``bomb_planted``
    * map_name
    * map_number
    * client
    * site
    
- ``bomb_defused``
    * map_name
    * map_number
    * client
    * site
    
- ``bomb_exploded``
    * map_name
    * map_number
    * client
    * site
    
- ``client_say``
    * map_name
    * map_number
    * client
    * message
    

### Miscellaneous 
- ``match_config_load_fail``
    * reason
    
- ``backup_loaded``
    * file
