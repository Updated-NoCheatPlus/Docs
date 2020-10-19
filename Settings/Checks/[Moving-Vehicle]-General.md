This page explains configuration options which affect vehicles.

| Option                          | Description |
| :------------------------------ | :---------- |
| vehicles _preventdestroyown_    | Prevent players from accidentally destroying their own minecart while riding it.|
| vehicles _enforcelocation_      | Attempt to track extreme deviations from the vehicle position and correct them. Experimental (hopefully-) legacy option. Likely inoperable and useless, subject to removal.|
| vehicle _schedulesetbacks_      | TODO: |
|vehicle _schedulesetpassenger_   | Keep the player into the vehicle -with the exception for boats- after a vehicle setback has recently happened. |
| illegalvehiclemove              | Kick and log this message to players who try to exploit vehicles.|

**Note**
* Minecraft fixed the "destroyown vehicle" bug so the `vehicle.preventdestroyown` feature is just here for legacy servers. Leaving it enabled won't conflict with anything.
* Set `vehicle.schedulesetpassenger` to true if you're noticing odd visual glitches/bugs (such as the player being off the vehicle client-side but still riding it server-side) after a vehicle setback. This is especially beneficiary for newer clients (1.16+) where such glitches are quite common.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
