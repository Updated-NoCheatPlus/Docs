Config path: `checks.moving.passable`  
Permission (bypass): `nocheatplus.checks.moving.passable`  
Exemption: `MOVING_PASSABLE`  
Better with: `[Combined] Enderpearl`

The Passaable check prevents moving into or inside of blocks.

| Option                                    | Description |
| :---------------------------------------- | :---------- |
| untracked _teleport active_               | This is to prevent players setting home at or teleport to another player who is at an untracked location (currently only COMMAND teleport reason). Untracked locations exist due to CraftBukkit trying to be nice to plugins, by not firing events for moves that don't cover enough distance/turning, effectively allowing to shift a tiny bit into a block without plugins being able to notice in an effective way. |
| untracked _command active_                | NCP supports detecting potential abuse by detecting players running certain commands at untracked locations. Typically a cheater could try to move into a block just by a tiny bit, so plugins won't notice, then they'd set home there, move back the tiny bit and teleport into the other block in a 'legal' way. |
| untracked _command tryteleport_           | Control if NCP is only to warn, or to try to teleport the player to the last tracked position. |
| untracked _command prefixes_              | The commands to track. This should be all commands that let you set home/warp/back and similar locations you could teleport to. "warp" for example also includes "warp xyz ...". You can distinguish by using 'warp set' instead of covering unneeded commands with just 'warp', depends on the plugins/command syntax. |

There are also hidden options, which give more access to internals. Use with care, as these might allow different kinds of cheats or lead to other false positives, if changed. Ask back if in doubt or test changes made.
| Option                                    | Description |
| :---------------------------------------- | :---------- |
| horizontalmargins                         | Control the XZ (horizontal) raytracing factor strictness for which the player will be considered as colliding with a block. (Max: 1.0, min: 0.1, default: 0.999999) |
| verticalmargins | Control the Y (vertical) raytracing factor strictness for which the player will be considered as colliding with a block. (Max: 1.0, min: 0.1, default: 0.999999) |                          

**Notes**
- Violations might trigger if players teleport or join and start moving while not having received or rendered the chunk they stand on. This causes the client to think that there are only air blocks around so it "falls down" and accidently clips a little into the solid blocks on your server. So please DO NOT quickly ban on Passable violations.
- The more lag, the more time it takes for the world to load up and the more likely it is for Passable to throw a false positive on join/teleport.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
