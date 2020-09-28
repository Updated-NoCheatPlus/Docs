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
| **slowfalling**        | Slowfalling is handled by CreativeFly. |
| slowfalling _horizontal speed_ |Maximum horizontal speed allowed with slowfalling active. The formula is as it follows: (horizontal value / 100 * 0.6).|
| slowfalling _vertical ascend speed_ |Maximum ascend speed allowed with slowfalling active. The formula is as it follows: (vertical value / 100). Set to 0 here since players cannot ascend while being exposed to slowfall. Setting it to a different value may allow slowly fly upwards.|
| slowfalling _vertical maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| slowfalling _vertical gravity_|Set whether NCP should calculate the ordinary falling friction with slowfalling active.|
| slowfalling _modifiers_|Set whether NCP should increase the base slowfalling speed by the attribute/potion modifiers value.|
| slowfalling _ground_|Set whether NCP should perform a ground check and collect all ground flags with slowfalling active.|
| **creative**           | Creative mode fly modelling, this also applies to players in survival who can fly: players in Creative (or that can fly) are checked by the CreativeFly by default (unless ignorecreative/allowflight is set to true)|
| creative _horizontal speed_|Maximum horizontal speed allowed in creative mode. The formula is as it follows: (horizontal value / 100 * 0.6).|
| creative _vertical ascend speed_|Maximum ascend speed allowed in creative mode. The formula is as it follows: (vertical value / 100). |
| creative _vertical maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| **spectator**         | Spectator mode is handled by CreativeFly only. |
| spectator  _horizontal speed_ |Maximum horizontal speed allowed in spectator mode. The formula is as it follows: (horizontal value / 100 * 0.6).|
| spectator  _vertical ascend speed_ |Maximum ascend speed allowed in spectator mode. The formula is as it follows: (vertical value / 100).|
| spectator  _vertical maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height)|
| spectator  _vertical gravity_|Set whether NCP should calculate the ordinary falling friction for players in spectator mode.|
| spectator  _modifiers_|Set whether NCP should increase the base speed for players in spectator mode by the attribute/potion modifiers value.|
| spectator  _ground_|Set whether NCP should perform a ground check and collect all ground flags for players in spectator mode.|
| **levitation**        | Levitation is handled by CreativeFly. |
| levitation _horizontal speed_ |Maximum horizontal speed allowed with levitation active. The formula is as it follows: (horizontal value / 100 * 0.6).|
| levitation _vertical ascend speed_ |Maximum ascend speed allowed with levitation active. The formula is as it follows: (vertical value / 100). Set to 0 here since players cannot ascend while being exposed to levitation. Setting it to a different value may allow slowly fly upwards.|
| levitation _vertical maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| levitation _vertical gravity_|Set whether NCP should calculate the ordinary falling friction with levitation active.|
| levitation _modifiers_|Set whether NCP should increase the base levitation speed by the attribute/potion modifiers value.|
| levitation _ground_|Set whether NCP should perform a ground check and collect all ground flags with levitation active.|
| **elytra**           | Gliding with an elytra is handled by CreativeFly only.|
| elytra _horizontal speed_|Maximum horizontal speed allowed when gliding. The formula is as it follows: (horizontal value / 100 * 0.6).|
| elytra  _horizontal modsprint_|The horizontal sprint modifier multiplier.|
| elytra _vertical ascend speed_ |Maximum ascend speed allowed when gliding. The formula is as it follows: (horizontal value / 100 * 0.6). Set to 0 here since players cannot intentionally glide upwards.|
| elytra _maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| elytra _modifiers_|Set whether NCP should increase the base speed for players gliding with an elytra by the attribute/potion modifiers value|
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
