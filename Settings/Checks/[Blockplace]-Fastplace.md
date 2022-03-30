Config path: `checks.blockplace.fastplace`  
Permission: `nocheatplus.checks.blockplace.fastplace`  
Exemption: `BLOCKPLACE_FASTPLACE`  

The FastPlace check will prevent players from using cheats that place blocks really quickly in order to work (E.g.: Scaffold and AutoBuild).

| Option             | Description |
| :--------------    | :---------- |
| limit              | How many blocks should a player be allowed to place in 2 seconds? |
| Shortterm _ticks_  | The amount of ticks to track for the short-term checking. 1 tick = 50ms. |
| Shortterm _limit_  | How many blocks should a player be able to place in the specified ticks? (Ex.: 10 blocks in 6 tick(300ms)) |
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|


**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
