The match config is described in the readme: https://github.com/splewis/get5#match-schema

This page aims to give advice on managing these config files.

## Managing team data 

One strategy for storing all the team data is to create a config for each team, then you can use the "fromfile" field when creating match configs.

For example:
``match.cfg``:
```
"Match"
{

	"maps_to_win"		"1"
	"skip_veto"		"0"
	"side_type"		"standard"

	"maplist"
	{
		"de_cache"		""
		"de_cbble"		""
		"de_dust2"		""
		"de_mirage"		""
		"de_nuke"		""
		"de_overpass"		""
		"de_train"		""
	}

	"players_per_team"		"5"

	"team1"
	{
		"fromfile"		"addons/sourcemod/configs/get5/team_nip.cfg"
	}

	"team2"
	{
		"fromfile"		"addons/sourcemod/configs/get5/team_nv.cfg"
	}

	"cvars"
	{
		"hostname"		"Match server #1"
	}
}
```

``team_nip.cfg``:
```
"team"
{
	"name"		"NiP" 
	"flag"		"SE"
	"logo"		"nip"
	"matchtext"		""
	"players"
	{
		"STEAM_0:1:52245092"		""
	}
}
```

``team_nv.cfg``:
```
"team"
{
	"name"		"EnvyUs" 
	"flag"		"FR"
	"logo"		"nv"
	"matchtext"		""
	"players"
	{
		"STEAM_0:1:52245092"		""
	}
}
```