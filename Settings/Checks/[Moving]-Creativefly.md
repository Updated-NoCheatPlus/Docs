Config path: `checks.moving.creativefly`  
Permission (bypass): `nocheatplus.checks.moving.creativefly`  
Exemption: `MOVING_CREATIVEFLY`  
Better with: `[Moving] Morepackets`  

The CreativeFly checks aims to handle movement related to flying; it's more tailored for players who are in special gamemodes (Creative/Spectator) or are exposed to particular effects (e.g.: levitation)
CreativeFly is also the check responsible to validate the player's movement when gliding with an elytra.

| Option              | Description |
| :------------------ | :---------- |
| ignoreallowflight   | Should CreativeFly **ignore** players who are set to be allowed to fly and let SurvivalFly handle them instead? Provided there aren't side conditions forcing use of the CreativeFly check regardless of the ignoreallowflight being set to false. If this option is set to false, players in Survival who are set to be allowed to fly will be able to use almost **any kind of movement cheat** as SurvivalFly will not be run for the player. |
| ignorecreative      | If set to false, the creativefly check will run for players who are in the _creative_ game mode, regardless if they're flying or not. If set to true, the SurvivalFly check will run instead, provided there are not other side conditions forcing use of the CreativeFly check. **This does not disable the creativefly check**. |
| slowfalling        | If the player is exposed to the slowfalling potion, they'll be checked by Creativefly. |
| slowfalling _horizontal speed_ ||
| slowfalling _vertical ascend speed_ ||
| slowfalling _vertical maxheight_||
| slowfalling _vertical gravity_||
| slowfalling _modifiers_||
| slowfalling _gravity_ ||
| slowfalling _ground_||
| creative           | Creative mode fly speed/model, this also applies to players in survival who can fly: players in Creative (or that can fly) are checked by the CreativeFly by default (unless ignorecreative/allowflight is set to true)|
| creative _horizontal speed_||
| creative _vertical ascend speed_||
| creative _vertical maxheight_||
| spectator         | Players in Spectator mode are always checked by the CreativeFly check. |
| spectator  _horizontal speed_ ||
| spectator  _vertical ascend speed_ ||
| spectator  _vertical maxheight_||
| spectator  _vertical gravity_||
| spectator  _modifiers_||
| spectator  _gravity_ ||
| spectator  _ground_||
| levitation        | If the player is exposed to the levitation effect, they'll be checked by Creativefly. |
| levitation  _horizontal speed_ ||
| levitation  _vertical ascend speed_ ||
| levitation  _vertical maxheight_||
| levitation  _vertical gravity_||
| levitation  _modifiers_||
| levitation  _gravity_ ||
| levitation  _ground_||
| elytra           | Elytra checking is shared between Survival/CreativeFly. When the player is gliding, CreativeFly will validate the player movements.|
| elytra _horizontal speed_||
| elytra  _horizontal modsprint_||
| elytra _vertical ascend speed_ ||
| elytra _maxheight_||
| elytra _modifiers_||
| elytra _resetFwOnGround_ | Reset the firework boost time if NCP detects the player to be on ground. |
| elytra _strict_ | Enable extra elytra checking methods. With this disabled, it'll be much easier for cheaters to exploit the elytra and fly around in Survival.|

**Notes**
* `hFrict`: Horizontal friction has been applied.
* `hDist`: Indicates that the player went beyond the horizontal limits.
* `hVel`: Player has velocity active.
* `MaxHeight`: Indicates that the player tried to fly too high up.
* `AntiLevitate`: Player triggered the "anti-levitate" subcheck.
* `vDist`: Indicates that the player went beyond the vertical limits.
* `Bunnyhop`: This move was (most likely) a bunnyhop and all conditions have been applied.
* `vFrict_g`: Horizontal friction + gravity.
* `Jump_gain`: Ordinary jump.
* `Step_up`: Ordinary step-up.
* `Fw_speed`: The player is boosting their elytra with a firework.
* `Elytra_v_keep`: The player is retaining the same (or changing very little) altitude with the elytra (which is not possible)
* `Elytra_v_asc`: Vertical ascending phase with the elytra.
* `Elytra_v_desc`: Vertical descending phase with the elytra.
* `Elytra_h_asc`: The player glided horizontally more than allowed for this gliding phase.


**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [SurvivalFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Survivalfly.md)
