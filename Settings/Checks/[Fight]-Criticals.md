Config path: `checks.fight.criticals`  
Permission (bypass): `nocheatplus.checks.fight.criticals`  
Exemption: `FIGHT_CRITICALS`              
Better with: `[Moving] NoFall` 

This check prevents players from doing more damage to players and mobs by faking critical hits.

| Option              | Description |
| :------------------ | :---------- |
| falldistance        | Jumping lower than this limit allows criticals violations. |

**Tags**
`falldist_mismatch`: This tag indicates a mismatch between Minecraft's fall distance and our calculated fall distance (the fall distance is taken from te NoFall).
`lowjump`: The player tried to jump lower than normal in order to get more critical hits.
`silent_jump`: The player somehow accumulated some fall distance while still being on ground (often the case with packet-based critical cheats).

**Notes**
* In MC you need to hit someone while falling to get a critical hit.
* Check `checks.moving.nofall.anticrticals` if you wish to further tweak settings concerning critical cheats.
* This checks uses NoFall's internal fall distances to determine if players could be using critical cheats, so disabling NoFall will cripple this check.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [NoFall](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Nofall.md)
