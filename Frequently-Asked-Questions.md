This page is meant for commonly asked questions that **aren't** answered in the [README](https://github.com/splewis/get5/blob/master/README.md).


## How can I use get5 for private scrims/pugs?
[Pugsetup](https://github.com/splewis/csgo-pug-setup) is better for private pugs/10 mans, but you can also use get5 for this. You should set ``get5_kick_when_no_match_loaded`` to 0 in ``cfg/sourcemod/get5/cfg``, and then once all ten players are connected and on the teams you want, run ``get5_creatematch`` (either via rcon or on your client if you have sourcemod admin). For more detail,see https://github.com/splewis/get5/wiki/Using-get5-for-scrims.