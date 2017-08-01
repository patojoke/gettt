## Getting error logs

Check ``addons/sourcemod/logs``. The files are called something like ``error_20170831.log``.


## Finding get5 version

You can either check the ``get5_version`` cvar or the version info from ``sm plugins``.

If you have access to the server console or have sourcemod admin:
``sm_cvar get5_version`` 

Otherwise, type 
``sm plugins``, ``sm plugins 11``, ``sm plugins 22``, ... until you find get5.


## Finding sourcemod version

From the server console or in a client console, type:

``sm version``


## Getting debug logs

Set ``get5_debug 32``. It's easiest to set the cvar in your match configs or ``cfg/sourcemod/get5.cfg``.

Then check ``addons/sourcemod/logs/get5_debug.log``. You can also set ``get5_debug`` to a different value, see https://github.com/splewis/get5/blob/master/scripting/include/logdebug.inc#L31 for details.