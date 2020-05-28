This page explains configuration options which affect or support multiple moving checks.

| Option                          | Description |
| :------------------------------ | :---------- |
| vehicles _preventdestroyown_    | Prevent to destroy a vehicle while they are riding/mounting it.|
| vehicles _enforcelocation_      | Attempt to track extreme deviations from the vehicle position and correct them. Experimental (hopefully-) legacy option. Likely inoperable and useless, subject to removal.|
| velocity _activationcounter_    | Queued unused velocity is removed after this amount of incoming moving packets. Decreasing this will nerf some abuses (such as long-jump) but it could also create more false positives (lag(...))|
| velocity _activationticks_      | Queued unused velocity is removed after this amount of server ticks. Decreasing this will nerf some abuses (such as long-jump) but it could also create more false positives (lag(...))|
| velocity _strictinvalidation_   | More strict invalidation of queued velocity.|
| splitmoves                      | TODO: |
| ignorestance | Ignore the bounding box check for players. This can be used to prevent compatibility issues on legacy setups. Set to default, it will disable from 1.8 on. Force set with true/false. |
| tempkickillegal                 | Setting this to false will just kick a player that does a illegal movement instead of actually tempbanning him for 24 hours. Technically NCP uses its deny login feature, only counting until next restart, not the ban command.|
| loadchunks _join_               | Should NCP load chunks around the player when joining the server before checking? (Prevents some types of false positive caused by lag)|
| loadchunks _move_               |Should NCP load chunks around the player when moving before checking? (Prevents some types of false positive caused by lag)
| loadchunks _teleport_           |Should NCP load chunks around the player when teleporting before checking? (Prevents some types of false positive caused by lag)
| loadchunks _worldchange_        |Should NCP load chunks around the player when changing world before checking? (Prevents some types of false positive caused by lag)
| sprintinggrace                  | Grace period for which SurvivalFly will let the player walk at sprinting speed even though their sprint has been toggled off (latency) (seconds).|
| assumesprint                    |  Workaround for the long-standing bug that has been introduced in MC 1.7 with the CTRL sprint feature. The server doesn't properly reflect the sprinting state of the client, causing a ton of false positives. This workaround will let NCP assume that the player is ALWAYS sprinting whenever *possible*.|
| speedgrace                      |  Grace period for which SurvivalFly will let the player walk at as if the speed effect is still active (latency) (seconds).|
| enforcelocation                 | Track if the player has somehow managed to get to ridiculous places without a moving event firing. Fixed the vehicle-teleport exploit. Legacy option for some time before Spigot 1.7.10. Setting to default will activate/deactivate based on the detected Minecraft version. Force set with true/false.|
| setback _method_                | Technique of setting back players. Legacy before MC 1.9: "set_to" The set_to setting will lead to problems since MC 1.11.2 since 2017-03-24, because TeleportCause.PLUGIN will result there, leaving potential for misinterpretation by other plugins. For MC 1.11.2 but also for 1.9 and later, the setting "cancel+update_from+schedule" is the default, it would cancel moving events, and induce teleporting to the set back location by updating the from location, with a fall-back check on-tick (schedule). The defaults can be referenced via their ids: default.legacy for pre-1.9, default.modern for latest (currently post-1.9), default.cautious for the latest with potential risks disabled (such as the teleport skipping condition using packet level ack). |
| illegalplayermove| Kick and log this message to players who try to use certain exploits.|

There are also hidden options, which give more access to internals. Use with care, as these might allow different kinds of cheats or lead to other false positives, if changed. Ask back if in doubt or test changes made.

|Hidden Option                    | Description |
| :------------------------------ | :---------- |
| yonground                       | Control the vertical distance to blocks, at which NCP will assume the player to touch ground. This affect any moving-related checks, dealing fall damage etc. Capped at a maximum value of 0.0625, and a minimum of 0.00001. The default value may be around 0.016. Adjusting this to something higher might allow moving slightly above cactus without taking damage, but it might also help on certain false positives. Changes should be tested with issues that can be reproduced at will. |

**Notes**
* Players could do a illegal movements which would crash the server, so we made a check against it that would tempban a player for 24 hours if they exploit that. However some users wanted to just kick such players and for that reason we put boolean to activate/deactivate temporary banning called `tempkickillegal`.
* Minecraft fixed the "destroyown vehicle" bug so vehicles preventdestroyown option is just here for legacy servers. Leaving it enabled won't conflict with anything either.
* *If you use plugins that allow 0 delay between two hits, reduce `velocity.activationcounter` and `velocity.activationticks` to something lower.*
* The Minecraft client moves (well more falls) even if no chunks are loaded up which could trigger a tiny Passable false positive. We tried to smooth this further out by loading up the chuncks on join as fast as possible with `loadchuncks _join_`. It seems that Mojang allows the client to move inside unloaded chunks, for the vanilla fly check because it would prevent false positives with it.
