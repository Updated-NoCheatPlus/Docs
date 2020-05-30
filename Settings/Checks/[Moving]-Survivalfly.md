Config path: `checks.moving.survivalfly`  
Permission (bypass): `nocheatplus.checks.moving.survivalfly`  
Exemption: `MOVING_SURVIVALFLY`  
Better with: `[Moving] Morepackets` and `[Combined] Bedleave`

SurvivalFly is the main check for player movement. It checks both horizontal and vertical moves.

| Option                              | Description |
| :---------------------------------- | :---------- |
| extended _vertical-accounting_      | Enable/Disable the *vertical-accounting* sub-check (vAcc) |
| stepheight                          | The height a player can from ground upwards to ground, without jumping. This is set to 'default' by default, so NCP will adjust it automatically with the Minecraft version. In case NCP can't detect the version properly, e.g. with custom builds, setting an explicit value might help. Used to be 0.5 before MC 1.8 and 0.6 from then on. |
| leniency _hbufmax_ | The cap value for the horizontal buffer. Horizontal moving violations get compensated with emptying the buffer - it fills up with (allowed) moving below the applicable base moving speed (not accounting for special acceleration like with bunny hopping). The higher the number, the more the time it will take for NCP to setback speed cheaters. |
| leniency _ViolationFrequency_| By default, SurvivalFly will relax the total violation level of the player over time with legit moves. The following feature allows SurvivalFly to better discern false positives from potential cheaters for lower violation levels by keeping track of how frequently a player is triggering this check, between a custom amount of moves. SurvivalFly won't cancel any detected move if they are below your set `maxleniencyvl` VL, but if a player is continiously triggering SF under the set threshold, NCP will pick up on that and start to *increase* the violation level so that they will get blocked much faster. This will significantly grant a better gameplay experience to legit players as sporadic/occasional low violations won't get hard blocked immediately by SF.|
| leniency _ViolationFrequency_ _active_| Should this hook be enabled for SurvivalFly? If false, SurvivalFly will always setback players upon violations, no matter how small they are (normal behaviour). Do note that this hook requires that you have set a 'cancel' flag in your actions.|
| leniency  _ViolationFrequency_  _debug_| Debug flag, for debugging issues about this hook|
| leniency  _ViolationFrequency_  _maxleniencyvl_| Maximum violation after which Survivalfly will setback players normally.|
| leniency  _ViolationFrequency_ _mintoadd_| Minimum VL for which SurvialFly will not weight out lower violations.|
|leniency  _ViolationFrequency_ _morevls_| How much should NCP increase lower violation levels by when a player is continiously triggering SurvivalFly under your set ` maxleniencyvl`?|
|leniency _ViolationFrequency_ _movecount_| Move counter after the last *violated* move for which SurvivalFly will use this hook.
| leniency _freezecount_ | The number of moves, for which the violation level can't decrease, after a violation has happened. |
| leniency _freezeinair_ | If set to true, the violation level can't decrease, while the player is moving in-air.
| setbackpolicy _falldamage_          | Deal the amount of fall damage players are supposed to get if they happen to fall and get setbacked on ground. This prevents people from exploiting NoCheatPlus to avoid fall damage by purposelly triggering SurvivalFly to force a setback. |
| setbackpolicy _voidtovoid_          | Should players be setbacked into the void instead of the last valid ground position (if no ground has been detected by NCP beneath the player)? This is meant to prevent cheaters from exploiting the set-back logic by purposelly trigger a detection to never fall down (SkyWars/Block) [BETA feature, not recommended to enable as of now]. |
| hover _step_                        | Tick-period for which to perform hover checking. |
| hover _ticks_                       | Ticks after which a player is assumed to hover if still in-air and not moving. |
| hover _logingticks_                 | Extra ticks added to hoverticks directly after login, to give more leniency. Set this on problems with hover + loging in. |
| hover _falldamage_                  | Deal fall-damage according to fall-distance, to make avoiding fall-damage harder. |
| hover _sfviolation_                 | A hover violation is counted as a survivalfly violations with this amount of violation level. |
 
There are also hidden options, which give more access to internals. Use with care, as these might allow different kinds of cheats or lead to other false positives, if changed. Ask back if in doubt or test changes made.

|Hidden Option                    | Description |
| :------------------------------ | :---------- |
| walkingspeed | Multiplier for the horizontal walking speed. Value is per-cent, 100 means no change (default), 200 doubles the allowed walking speed. Does not apply with sprinting! |
| sprintingspeed | Multiplier for the horizontal sprinting speed. Value is per-cent, 100 means no change (default) , 200 doubles the allowed sprinting speed. Does only apply with sprinting! Due to the sprinting state on server side not always reflecting the client side, NCP will assume the player to be sprinting whenever technically possible (setting: _assumesprint_) - this means that this setting will take effect when the player isn't too hungry. |
| blockingspeed | Multiplier for the horizontal walking speed, when blocking. Value is per-cent, 100 means no change (default), 200 doubles the allowed blocking speed. Overrides the modifiers above. |
| sneakingspeed | Multiplier for the horizontal walking speed, when sneaking. Value is per-cent, 100 means no change (default), 200 doubles the allowed sneaking speed. Overrides the modifiers above. |
| swimmingspeed | Multiplier for the horizontal swimming speed. Value is per-cent, 100 means no change (default), 200 doubles the allowed swimming speed. Overrides the modifiers above. |
| speedingspeed | Multiplier for the horizontal speed. Value is per-cent, 100 means no change, 200 doubles the allowed horizontal speed (default). This always applies extra to other modifiers, regardless of the side conditions, provided a player has the permission _nocheatplus.checks.moving.survivalfly.speeding_. |

**Tags**
* `vDistRel`: The player went beyond our y (vertical) envelopes or did a move that does not follow our vertical-distance rules.
* `hSpeed`: The player went beyond our horizontal envelopes or did a move that exceeded our horizontal speed limits.
* `Waterwalk`: Indicates that the player is walking on water (walking in/on water without any change in yDistances.).
* `Watermove`: Indicates that the player is moving with very little y deltas above water.
* `Lostground_[tag]`: A LostGround case has been detected and applied to the player.
* `yChInc/yChIncFly/yChDec/yChIncAir`: Change of y direction checks, the yChIncFly one indicates moving upwards after falling without having touched the ground first. (yChangeIncrease/yChangeDecrease/yChangeIncreaseAir/(...).
* `vAcc`. The vertical-accounting check. Demands players to start to fall after having been in air for a specific amount of time. It enforces gravity for a minimum amount on players.
* `hAcc`: The horizontal-accounting check. It monitors average combined-medium (e.g. air+ground or air+water) speed, with a rather simple bucket(s)-overflow mechanism.
* `Bunnyhop/Bunnyenv/Bunny(...)`: The move performed by the player was (most likely) a bunnyhop and all mechanisms/conditions have been applied.
* `Badsprint`: The player tried to sprint with blindness active.
* `Backsprint`: The player tried to sprint backwards.
* `Step`: Most likely a step-like movement.
* `vDistSb`: The player went beyond the absolute y-distance to set back.
* `Dirty`: Indicates that the player got velocity while being in-air.
* `vAccDirty`: In-air velocity with vAcc being triggered.
* `LostSprint`: The LostSprint workaround has been applied to the player.
* `UsingItem`: Indicates that the player is using/consuming an item (Blocking/Eating(...))
* `Hack_vEnv`: A vertical envelope case has been applied to the player, allowing the move.
* `LowJump/LowJump_set/ceil`: This move was most likely a low jump (cheating). Ceil represents a legit lowjump due to the player jumping in a 2-blocks high area.
* `Data_reset/missing`: Indicates that the allowed y distance of the player has been reset due to a teleport/join/respawn.
* `Permchecks(out/inliquid)`: After (horizontal) failure permission checks.
* `hVel`: Some velocity has been applied to the player.
* `hBufUse`: Indicates that the player used up all the available horizontal buffer.
* `SwimUp/Down`: The player went beyond our in-water y (vertical) envelopes or did a move that does not follow our vertical-distance rules while being in water.
* `ClimbSpeed`: The player went beyond our vertical speed limits for climbable blocks.
* `CilmbDetached`: The player tried to climb up a block that's not possible to climb. (This applies for vines that are not attached to other blocks)
* `vFrict_Climb`: Friction with velocity on climbable (e.g.: being hit while climbing a ladder)
* `vWeb/Bush`: The player went beyond our vertical speed limits for web-like blocks (includes bushes as well)
* `MaxPhase`: Indicates a too high jump or step phase for this move. 

**Notes**
* If you alter the actions in the configuration to not always cancel, you might be allowing glide-like cheats. Issues with horizontal speed are easier to work a around by configuration, than issues with the vertical part of a move.
* A powerful tool for issues with moving is provided with the _on-the-fly debug logging feature_, significantly improving the odds for a quick fix: https://github.com/NoCheatPlus/Docs/wiki/Debugging#on-the-fly-debug-output-for-individual-players
* Hover is a sub-check of SurvivalFly which prevents players from hovering around in mid-air.
* The _leniency/freeze_ settings mainly aim at configurations that don't cancel for low violation levels. With the freezing option, cheaters can't create repeated small violations as easily.
* The LostGround workarounds check if touching the ground was lost (because the client did not send, or the server did not put it through) [This is due to a Minecraft bug](https://bugs.mojang.com/browse/MC-90024).
* The LostSprint workaround allows for smoother transitions between sprinting/walking. It checks if the player is still (legitimately) moving at sprinting speed even though the server has caused their sprinting status to expire (lag/latency)

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [NoFall](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Nofall.md)
* [CreativeFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Creativefly.md)
