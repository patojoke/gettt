Get5 offers several cvars for how pausing will work:

- ``get5_max_pauses``: maximum number of pauses a team can use, 0=unlimited
- ``get5_max_pause_time``: maximum number of time the game can spend paused by a team, 0=unlimited
- ``get5_reset_pauses_each_half``: whether pause limits are reset each halftime period (default 1)
- ``get5_fixed_pause_time``: if nonzero, the fixed length all pauses will be
- ``get5_pausing_enabled``: whether pausing (!pause command) is enabled


These can be set in ``cfg/sourcemod/get5.cfg``, or in a match config's ``cvars`` section.

The default settings will allow each team 300 seconds (5 minutes) of overall pause time per half. That is:
- ``get5_max_pauses = 0``
- ``get5_max_pause_time = 300``
- ``get5_reset_pauses_each_half = 1`` 
- ``get5_fixed_pause_time = 0`` 
- ``get5_pausing_enabled = 1`` 


To use the newer pausing ruleset of "each team has 4 30-second pauses", you would use the following cvars:
- ``get5_max_pauses = 4``
- ``get5_reset_pauses_each_half = 0`` 
- ``get5_fixed_pause_time = 30`` 
- ``get5_pausing_enabled = 1`` 