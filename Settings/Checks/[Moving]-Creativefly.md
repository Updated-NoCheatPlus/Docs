Config path: `checks.moving.creativefly`  
Permission (bypass): `nocheatplus.checks.moving.creativefly`  
Exemption: `MOVING_CREATIVEFLY`  
Better with: `[Moving] Morepackets`  

CreativeFly aims to control special movements such as levitating, gliding and flying (in survival) as well as checking players in Creative and Spectator mode.

| Option              | Description |
| :------------------ | :---------- |
| ignoreallowflight   | Should CreativeFly **ignore** players who are set to be allowed to fly in _survival/adventure_ and let SurvivalFly handle them instead? Provided there aren't side conditions forcing use of CreativeFly (see notes) regardless of `ignoreallowflight` being set to false. If this option is set to false, players in _survival_ who are set to be allowed to fly will be able to use almost **any kind of movement cheat** as SurvivalFly will not be run for the player. |
| ignorecreative      | Should CreativeFly **ignore** players who are in creative mode and let SurvivalFly handle them instead? Provided there aren't other side conditions forcing use of CreativeFly (see notes), regardless of `ignorecreative` being set to true. **This does not disable CreativeFly**. |
| **riptiding**           | Riptide movement modelling |
| riptiding _horizontal speed_|Maximum horizontal speed allowed while riptiding. The formula is as it follows: (horizontal value / 100 * 0.6).|
| riptiding _vertical ascend speed_|Maximum ascend speed allowed in riptiding. The formula is as it follows: (vertical value / 100). |
| riptiding _vertical maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| riptiding _modifiers_|Set whether NCP should increase the base riptiding speed by the attribute/potion modifier value.|
| **slowfalling**        | Slowfalling is handled by CreativeFly. |
| slowfalling _horizontal speed_ |Maximum horizontal speed allowed with slowfalling active. The formula is as it follows: (horizontal value / 100 * 0.6).|
| slowfalling _vertical ascend speed_ |Maximum ascend speed allowed with slowfalling active. The formula is as it follows: (vertical value / 100). Set to 0 here since players cannot ascend while being exposed to slowfall. Setting it to a different value may allow slowly fly upwards.|
| slowfalling _vertical maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| slowfalling _vertical gravity_|Set whether NCP should calculate the ordinary falling friction with slowfalling active.|
| slowfalling _modifiers_|Set whether NCP should increase the base slowfalling speed by the attribute/potion modifier value.|
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
| spectator  _modifiers_|Set whether NCP should increase the base speed for players in spectator mode by the attribute/potion modifier value.|
| spectator  _ground_|Set whether NCP should perform a ground check and collect all ground flags for players in spectator mode.|
| **levitation**        | Levitation is handled by CreativeFly. |
| levitation _horizontal speed_ |Maximum horizontal speed allowed with levitation active. The formula is as it follows: (horizontal value / 100 * 0.6).|
| levitation _vertical ascend speed_ |Maximum ascend speed allowed with levitation active. The formula is as it follows: (vertical value / 100). Set to 0 here since players cannot ascend while being exposed to levitation. Setting it to a different value may allow slowly fly upwards.|
| levitation _vertical maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| levitation _vertical gravity_|Set whether NCP should calculate the ordinary falling friction with levitation active.|
| levitation _modifiers_|Set whether NCP should increase the base levitation speed by the attribute/potion modifier value.|
| levitation _ground_|Set whether NCP should perform a ground check and collect all ground flags with levitation active.|
| **elytra**           | Gliding with an elytra is handled by CreativeFly only.|
| elytra _horizontal speed_|Maximum horizontal speed allowed when gliding. The formula is as it follows: (horizontal value / 100 * 0.6).|
| elytra  _horizontal modsprint_|The horizontal sprint modifier multiplier.|
| elytra _vertical ascend speed_ |Maximum ascend speed allowed when gliding. The formula is as it follows: (horizontal value / 100 * 0.6). Set to 0 here since players cannot intentionally glide upwards.|
| elytra _maxheight_|The maximum height in blocks that players can travel after having gone beyond MC's 256 height limit. (maxheight + 256 = maximum world height).|
| elytra _modifiers_|Set whether NCP should increase the base speed for players gliding with an elytra by the attribute/potion modifiers value|
| elytra _resetFwOnGround_ | Reset the firework boost time if NCP detects the player to be on ground. |
| elytra _strict_ | Enable extra elytra checking methods. With this disabled, it'll be much easier for cheaters to exploit the elytra and fly around in Survival.|

**Tags**
* `hFrict`: Horizontal friction has been applied.
* `hFrict_lev`: Levitation horizontal friction.
* `hFrict_rip`: Riptide horizontal friction.
* `vRipGlide`: Vertical distance checking for riptiding and gliding at the same time.
* `hRipGlide`: Horizontal distance checking for riptiding and gliding at the same time.
* `hDist`: Indicates that the player went beyond the horizontal limits.
* `hVel`: Player has velocity active.
* `hDolphinsGrace`: Dolphin's grace amplifier.
* `MaxHeight`: Indicates that the player tried to fly too high up.
* `AntiLevitate`: Player triggered the "anti-levitate" subcheck.
* `vDist`: Indicates that the player went beyond the vertical limits.
* `Bunnyhop`: This move was (most likely) a bunnyhop and all conditions have been applied.
* `vFrict_g`: Vertical friction (gravity).
* `Jump_gain`: Ordinary jump.
* `Step_up`: Ordinary step-up.
* `Fw_speed`: The player is boosting their elytra with a firework.
* `e_vdiff`: Tag usually associated to elytra cheats (fly etc...).
* `e_vasc`: Vertical ascending phase with the elytra.
* `e_vdesc`: Vertical descending phase with the elytra.
* `e_jump`: Special elytra jump.
* `e_asc1/2/3`: Vertical ascending phase with the elytra (special cases).
* `e_hspeed/(liq)`: The player glided horizontally more than allowed for this gliding phase (`liq` means the player is gliding in a liquid)..
* `EXTREME_MOVE`: A sanity check. The player tried to cover a really high amount of distance with just one move.

**Notes**

The following conditions will _force_ the use of CreativeFly, regardless of the `ignoreallowflight/creative` option:
* The player is exposed to slowfalling or levitation.
* The player is in a gliding phase (not just wearing the elytra).
* The player is in Spectator mode.
* The player is riptiding
* SurvivalFly is disabled in the configuration (NCP will then fallback to the enabled check).
* The player is exempted from SurvivalFly.


**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [SurvivalFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Survivalfly.md)
