If your match config enabled the veto (not setting ``skip_veto`` to 1 or true), then the plugin will give veto menus to a player on each team. The player it gives it to will generally be the first player listed in the ``players`` section in the match config. All veto information given here assumed a 7-map pool. Other map-pool sides may not work as described here. It also assumes ``side_type`` is "standard" when describing side choices.

Note: team1 always gets the first veto.

#### BO1 Veto
Each team alternatives vetoing, vetoing 3 maps each. The 7th map left will be played. A knife round will be used to decide what the starting sides are.

tldr: ban/ban/ban/ban/ban/ban/last map is played

#### BO2 Veto
Each team alternatives vetoing, vetoing 2 maps each. After those vetoes, 3 maps are left. Each team picks a map, letting the other team choose side on it. The last map left will not be used in the series.

tldr: ban/ban/ban/ban/pick map 1/pick map 2/last map unused

#### BO3 Veto
Each team vetoes 1 map, then each team picks one map. The team that did not pick a map gets the side choice on it. After this veto/veto/pick/pick, each team will veto another map until only 1 map is left. The 1 map left will be the 3rd map in the series, and a knife round will be used to decide starting sides.

tldr: ban/ban/pick/pick/ban/ban/last map is 3rd map in series

#### BO5 Veto
Each team vetoes 1 map, then alternating picking the maps (really only deciding the order of them). When a team picks a map, the other team will get side choice. A knife round will be used on map 5 to decide sides.

tldr: ban/ban/pick/pick/pick/pick/last map is 5th map in series
