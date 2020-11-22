Config path: `checks.fight.direction`  
Permission (bypass): `nocheatplus.checks.fight.direction`  
Exemption: `FIGHT_DIRECTION`  

The Fight.Direction check prevents players from hitting entities out of FOV/crosshair

| Option              | Description |
| :------------------ | :---------- |
| strict              | Extra strict interpretation method, will also check the angle between the viewing direction and the direction towards the target, making the check more accurate in a close combat, at cost of (potentially) more false positives. This only applies to PVP, not versus mobs. |
| failall             | Only set off the direction check if no suitable looking direction during the loop can pass. |
| loopprecision       | How much should NoCheatPlus expand the target hitbox by? (Mitigates false positives) Higher value, higher leniency thus a higher chance of cheating (minimum: 0.5)
| strictangleprecision| If the strict mode is active, what should the max angle be between the vector from attacker to target and the look vector? Max 100.0, min 50.0.
| penalty             | How long should a player have to wait to hit other entities after triggering the check. |

**Notes**  
* Disabling this would allow players to fight entities while having their back turned on them.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
