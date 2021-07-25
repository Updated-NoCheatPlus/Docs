Config path: `checks.moving.survivalfly`  
Permission (bypass): `nocheatplus.checks.moving.survivalfly`  
Exemption: `MOVING_SURVIVALFLY`  
Better with: `[Moving] Morepackets` and `[Combined] Bedleave`

SurvivalFly is the main check for player movement. It checks both horizontal and vertical moves in/on all kind of mediums (water, air, etc...)

| Option                              | Description |
| :---------------------------------- | :---------- |
| extended _vertical-accounting_      | Whether the *vertical-accounting* sub-check(vAcc) should be active (See tags) |
| extended _horizontal-accounting_    | Whether the *horizontal-accounting* sub-check(hAcc) should be active (See tags) |
| extended _reset-activeitem_         |  If true, SurvivalFly won't allow the player to use the item held upon a noslowdown violation, instead of setting them back. (See notes)  |
| extended _noslow_                   | Whether the noslowdown detection should be active at all.|
| stepheight                          | The height a player can from ground upwards to ground, without jumping. This is set to 'default' by default, so NCP will adjust it automatically with the Minecraft version. In case NCP can't detect the version properly, e.g. with custom builds, setting an explicit value might help. Used to be 0.5 before MC 1.8 and 0.6 from then on. |
| leniency _hbufmax_ | The cap value for the horizontal buffer. Horizontal moving violations get compensated with emptying the buffer. It fills up with moving below the applicable base moving speed (not accounting for special accelerations like with bunny hopping). The higher the number, the more the time it will take for NCP to setback speed cheaters. |
| leniency _ViolationFrequency_| The following feature aims at preventing the abuse of SurvivalFly's violation level relaxation mechanic (VLs will go down over time with legit moves) if you don't have set in your configuration to always cancel/setback on violations (see notes) by keeping track of the flag frequency in a custom amount of moves. If this option is set to true, SurvivalFly won't cancel any detected move if the generated violation is under your `maxleniencyvl` threshold, however, if the player is *repeatedly and continiously* triggering SurvivalFly under said threshold, then the violation level will start to increase so that (potential) cheaters will get setbacked much faster while granting to legit players a better gameplay experience as *sporadic and occasional* low violations won't immediately lead to a setback.|
| leniency _ViolationFrequency_ _active_| Should this hook be enabled for SurvivalFly? If false, SurvivalFly will always setback players upon violations, no matter how small they are (normal behaviour). Do note that this hook requires that you have set a `cancel` flag in your actions.|
| leniency  _ViolationFrequency_  _debug_| Debug flag, for debugging issues about this hook.|
| leniency  _ViolationFrequency_  _maxleniencyvl_| Maximum violation after which SurvivalFly will setback players normally and stop using this hook.|
| leniency  _ViolationFrequency_ _mintoadd_| Minimum violation level for which SurvialFly will not escalate lower violations by the `morevls` amount.|
|leniency  _ViolationFrequency_ _morevls_| How much should SurvivalFly increase lower violation levels by when a player is continiously triggering SurvivalFly under your set ` maxleniencyvl` value?|
|leniency _ViolationFrequency_ _movecount_| Move counter after the last *violated* move for which SurvivalFly will escalate lower violations by the `morevls` amount. |
| leniency _freezecount_ | The number of moves, for which the violation level can't decrease, after a violation has happened. |
| leniency _freezeinair_ | If set to true, the violation level can't decrease, while the player is moving in-air. |
| setbackpolicy _falldamage_          | Deal the amount of fall damage players are supposed to get if they happen to fall and get setbacked on ground. This prevents people from exploiting NoCheatPlus to avoid fall damage by purposelly triggering SurvivalFly to force a setback. |
| setbackpolicy _voidtovoid_          | Should players be setbacked directly into the void instead of the last valid ground location (if no ground has been detected by NCP beneath the player)? This is meant to prevent cheaters from exploiting the set-back logic by purposelly trigger a detection to never fall down (SkyWars/Block) [BETA feature, not recommended to enable as of now]. |
| hover _step_                        | Tick-period for which to perform hover checking. |
| hover _ticks_                       | Ticks after which a player is assumed to hover if still in-air and not moving. |
| hover _logingticks_                 | Extra ticks added to hoverticks directly after login, to give more leniency. Set this on problems with hover + loging in. |
| hover _falldamage_                  | Deal fall-damage according to fall-distance, to make avoiding fall-damage harder. |
| hover _sfviolation_                 | A hover violation is counted as a survivalfly violations with this amount of violation level. |
 
There are also hidden options, which give more access to internals. Use with care, as these might allow different kinds of cheats or lead to other false positives, if changed. Ask back if in doubt or test changes made.
(They need to be added manually to the configuration file, before the `vAcc` and `hAcc` entry)

|Hidden Option                    | Description |
| :------------------------------ | :---------- |
| walkingspeed | Multiplier for the horizontal walking speed. Value is per-cent, 100 means no change (default), 200 doubles the allowed walking speed. Does not apply with sprinting! |
| sprintingspeed | Multiplier for the horizontal sprinting speed. Value is per-cent, 100 means no change (default) , 200 doubles the allowed sprinting speed. Does only apply with sprinting! Due to the sprinting state on server side not always reflecting the client side, NCP will assume the player to be sprinting whenever technically possible (setting: _assumesprint_) - this means that this setting will take effect when the player isn't too hungry. |
| blockingspeed | Multiplier for the horizontal walking speed, when blocking. Value is per-cent, 100 means no change (default), 200 doubles the allowed blocking speed. Overrides the modifiers above. |
| sneakingspeed | Multiplier for the horizontal walking speed, when sneaking. Value is per-cent, 100 means no change (default), 200 doubles the allowed sneaking speed. Overrides the modifiers above. |
| swimmingspeed | Multiplier for the horizontal swimming speed. Value is per-cent, 100 means no change (default), 200 doubles the allowed swimming speed. Overrides the modifiers above. |
| speedingspeed | Multiplier for the horizontal speed. Value is per-cent, 100 means no change, 200 doubles the allowed horizontal speed (default). This always applies extra to other modifiers, regardless of the side conditions, provided a player has the permission _nocheatplus.checks.moving.survivalfly.speeding_. |
| groundhop | Hidden option to account for a special case in legacy (< 1.7.) servers where the player is able to hop without y distance increases at moderate horizontal speed.|
| slownesssprinthack | Hidden option to allow Survivalfly to adjust the horizontal speed limit when players sprint-jump with the slowness potion active. |

**Tags**
* `vDistRel`: This move does not follow our vertical-distance rules (violation).
* `HoneyAsc`: Player tried to ascend more than allowed while being on a honey block (The block halfs(+-) the jump height).
* `GroundStep`: Indicates that the `stepheight` distance is currently being enforced, not necessarly triggering a VL. (This applies if the movement is fully on ground (from->to), otherwise the `vDistRel` distance will be applied).
* `hSpeed`: This move exceeds our horizontal limits.
* `Waterwalk`: Indicates that the player is walking on water (walking in/on water without any change in y distances.).
* `Watermove`: Indicates that the player is moving with very little y deltas above water.
* `Lostground_[tag]`: A LostGround case has been detected and applied to the player. This will allow the movement.
* `yChInc/yChIncFly/yChDec/AirJump`: Change of y direction checks, AirJump represents moving upwards after falling without having touched the ground first. (yChangeIncrease/yChangeDecrease/(...)).
* `vAcc`. The vertical-accounting check. Demands players to start to fall after having been in air for a specific amount of time. Acts as a "gravity enforcer", sort of. 
* `hAcc`: The horizontal-accounting check. It monitors average combined-medium (e.g. air+ground or air+water) speed, with a rather simple bucket(s)-overflow mechanism.
* `Bunnyhop/Bunnyenv/any tag containing "bunny"`: This movement is related to our bunnyhop detection method. This will often result in the player being allowed to perform such move.
* `Badsprint`: The player tried to sprint with blindness active.
* `Backsprint`: The player tried to sprint backwards.
* `vDistSb`: The player went further than the set-back distance.
* `Dirty`: This in-air phase has been affected by velocity.
* `vAccDirty`: In-air velocity with vAcc being triggered.
* `LostSprint`: The sprint status of the player has been lost (see notes).
* `UsingItem`: Indicates that the player is using/consuming an item (Blocking/Eating(...)).
* `LowJump/LowJump_set/ceil`: This move was a low jump (likely cheating). Ceil represents a legit lowjump due to the player jumping in a 2-blocks high area.
* `Data_reset/missing`: Indicates that the allowed y distance of the player has been reset due to a teleport/join/respawn.
* `hVel`: Some velocity has been applied to the player.
* `hBufUse`: The player has used some of the available horizontal buffer.
* `SwimUp/Down`: This move went further than our rule set for moving vertically in water.
* `ClimbSpeed`: The player went beyond our vertical speed limits for climbable blocks.
* `CilmbDetached`: The player tried to climb up a block that's not possible to climb (This applies for vines that are not attached to other blocks).
* `vFrict_Climb`: Friction with velocity on climbable (e.g.: being hit while climbing a ladder).
* `vWeb/vWedDesc`: Webs vertical distance checking (Ascending/Descending).
* `vBush/vbushDesc`: In berry bush vertical distance checking (Ascending/Descending).
* `MaxPhase`: Indicates a too high jump or step phase for this move. 
* `Itemreset`: The reset workaround has been applied.
* `SnowAsc/SnowDesc`: Powder snow vertical distance checking (Ascending/Descending).

**Notes**
* If you don't set in your configuration to always cancel movements on violations (especially on lower ones), cheaters can tipically abuse this by creating small and repeateed violations which stay under your tolerance threshold and use cheats; a fair amount of fly 'bypasses" exploit this exact scenario. The ViolationFrequency hook will mitigate this by a lot, as cheaters cannot repeatedely create smaller violations without making them escalate over time, reaching the next VL interval where a cancel flag is set.
* A powerful tool for issues with moving is provided with the _on-the-fly debug logging feature_, significantly improving the odds for a quick fix: https://github.com/NoCheatPlus/Docs/wiki/Debugging#on-the-fly-debug-output-for-individual-players
* Hover is a sub-check of SurvivalFly which prevents players from hovering around in mid-air.
* The _leniency/freeze_ settings mainly aim at configurations that don't cancel for low violation levels. With the freezing option, cheaters can't create repeated small violations as easily.
* The `LostGround` workarounds check if touching the ground was lost (because the client did not send, or the server did not put it through) [This is due to a Minecraft bug](https://bugs.mojang.com/browse/MC-90024)
* The `LostSprint` workarounds, likewise the `LostGround` ones, check if the sprinting status has been lost. This is often occours during a combat. Without this, players would be setbacked a lot during a fight.
* The `hAcc` subcheck acts as a sort of last line of defense against speed hacks, in case all other method get bypassed, so it's not recommended to disable.
* Around MC 1.8.x/1.13.x the server would sometimes desync the player when using items, making them look like as if they were using noslowdown cheats (the player is blocking server-side but not client-side). The itemsreset workaround will attempt to mitigate this by refreshing the player's item after failing our noslow detection instead of penalizing the player by cancelling their move.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [NoFall](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Nofall.md)
* [CreativeFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Creativefly.md)
