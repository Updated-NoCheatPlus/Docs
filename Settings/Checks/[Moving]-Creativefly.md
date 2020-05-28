Config path: `checks.moving.creativefly`  
Permission (bypass): `nocheatplus.checks.moving.creativefly`  
Exemption: `MOVING_CREATIVEFLY`  
Better with: `[Moving] Morepackets`  

The CreativeFly checks aims to handle movement related to flying, it's more tailored for players who are in special gamemode modes or are exposed to particular effects (e.g.: levitation)
CreativeFly is also the check responsible to validate the player's movement when gliding with an elytra.

| Option              | Description |
| :------------------ | :---------- |
| ignoreallowflight   | Should CreativeFly **ignore** players who are set to be allowed to fly and let SurvivalFly handle them instead? Provided there aren't side conditions forcing use of the CreativeFly check regardless of the ignoreallowflight being set to false. If this option is set to false, players in Survival who are set to be allowed to fly will be able to use almost **any kind of movement cheat** as SurvivalFly will not be run for the player. |
| ignorecreative      | If set to false, the creativefly check will run for players who are in the _creative_ game mode, regardless if they're flying or not. If set to true, the SurvivalFly check will run instead, provided there are not other side conditions forcing use of the CreativeFly check. **This does not disable the creativefly check**. |
| horizontalspeed     | Modifier for the maximally allowed horizontal speed. 100 means "normal" creative mode speed. 200 would be twice the speed. |
| maxheight           | This is a height limit which is counted from above the worlds maximum height (usually resulting in 256 + maxheight). |
| verticalspeed       | Modifier for the maximally allowed vertical speed. 100 means "normal" creative mode speed. 200 would be twice the speed. |

**Notes**
The following conditions can force use of the creativefly check, regardless of options 'ignoreallowflight' and 'ignorecreative'
* The survivalfly check is not activated for the player (activation, exemption, permissions).
* The player is flying.
* The player is gliding with an elytra.
* The player is exposed to the levitation effect.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [SurvivalFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Survivalfly.md)
