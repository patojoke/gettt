## Getting a debug dump

This is the most useful piece of information in bug reports.

Run ``get5_debuginfo`` on the server, and check the server's root ``csgo`` directory for a file called get5_debug.txt. Paste it (**not** a link to it) directly in the bug report. 

## Finding get5 version

You can either check the ``get5_version`` cvar or the version info from ``sm plugins``.

If you have access to the server console or have sourcemod admin:
``sm_cvar get5_version`` 

Otherwise, type 
``sm plugins``, ``sm plugins 11``, ``sm plugins 22``, ... until you find get5.


## Finding sourcemod version

From the server console or in a client console, type:

``sm version``
## Getting error logs

Check ``addons/sourcemod/logs``. The files are called something like ``error_20170831.log``.


## Getting debug logs

You have to set ``get5_debug 32`` for this to work. It's easiest to set the cvar in your match configs or ``cfg/sourcemod/get5.cfg``.

Then check ``addons/sourcemod/logs/get5_debug.log``. You can also set ``get5_debug`` to a different value, see https://github.com/splewis/get5/blob/master/scripting/include/logdebug.inc#L31 for details.

If you're using the web panel with the get5_apistats plugin, you should also set get5_apistats_debug (to the same value as get5_debug). 