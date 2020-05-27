Config path: `checks.blockplace.fastplace`  
Permission: `nocheatplus.checks.blockplace.fastplace`  
Exemption: `BLOCKPLACE_FASTPLACE`  

FastPlace prevents players from placing blocks too quickly. This will prevent players from using cheats that place blocks really quickly in order to work (E.g.: Scaffold and AutoBuild).

| Option             | Description |
| :--------------    | :---------- |
| limit              | How many blocks should a player be allowed to place in 2 seconds? Mind lag spikes and server tps drops.|
| Shortterm _ticks_  | The amount of ticks to track for the short-term checking.|
| Shortterm _limit_  | How many blocks should a player be able to place in the specified ticks? |
| Improbable _feedonly_ | If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable.|


**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
