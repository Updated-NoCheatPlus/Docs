Config path: `checks.blockbreak.frequency`  
Permission (bypass): `nocheatplus.checks.blockbreak.frequency`  
Exemption: `BLOCKBREAK_FREQUENCY`  

The BlockBreak.Frequency check hard-limits the amount of blocks a player can break in custom time frames in total.
It does not concern the speed at which players can break a single block (which is covered by the FastBreak check)


| Option              | Description |
| :------------------ | :---------- |
| intervalcreative    | The minimally allowed time to pass between breaking blocks in creative gamemode. |
| intervalsurvival    | The minimally allowed time to pass between breaking blocks in survival gamemode. |
| shortterm _ticks_   | Number of server ticks (50 ms each) to keep track for limiting short term bursts. |
| shortterm _limit_   | How many blocks are players allowed to break in the specified ticks? |

**Notes**
* There is a general buffer counting in 2 seconds by default and allowing to accumulate as many blockbreaks as fit into the time given the intervalcreative and/or intervalsurvival settings interpreted as durations.
* In addition it has a short term setting, also counting the blocks within the last n ticks and limiting the short term amount. This way players cannot break 80 blocks at once and then pause for two seconds.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
