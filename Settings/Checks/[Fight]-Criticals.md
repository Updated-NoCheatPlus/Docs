Config path: `checks.fight.criticals`  
Permission (bypass): `nocheatplus.checks.fight.criticals`  
Exemption: `FIGHT_CRITICALS`              
Better with: `[Moving] NoFall` 

This check ensures that critical hits performed by players are legit.

| Option              | Description |
| :------------------ | :---------- |
| falldistance        | Jumping lower than this limit allows criticals violations. |
| falldistleniency    | The leniency value used to compare fall distance differences. Higher the value, higher the leniency.|

**Tags**
* `falldist_mismatch`: This tag indicates a mismatch between Minecraft's fall distance and our calculated fall distance (the fall distance is taken from the NoFall check).
* `lowjump`: The player tried to jump lower than normal in order to get more critical hits.
* `silent_jump`: The player accumulated fall distance while still being on ground (often the case with packet-based critical cheats).

**Notes**
* In MC you need to hit someone while falling to get a critical hit.
* Check `checks.moving.nofall.anticrticals` if you wish to further tweak settings concerning critical cheats.
* The `falldist_mismatch` module uses NoFall's internal calculations to determine if players could be cheating, so disabling NoFall will partially cripple this check.
* Some packet-based critical cheats may trigger MorePackets if cheaters hit their target too many times while moving.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [NoFall](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Nofall.md)
