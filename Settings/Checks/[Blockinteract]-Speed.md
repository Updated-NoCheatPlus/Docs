Config path: `checks.blockinteract.speed`  
Permissions: `nocheatplus.checks.blockinteract.speed`  
Exemption: `BLOCKINTERACT_SPEED`  

The speed check limits the amount of interactions a player can do within a given time frame.

| Option    | Description |
| :-------- | :---------- |
| interval  | How long should the check last? (ms). |
| limit     | Maximal amount of interactions that can be done in the given interval |

**Notes**
* Be aware that its possible to do 20-30 interactions in 2 seconds even without a modified client given the right circumstances.
* Trying to constantly break grass in a protected area (WorldGuard) can create about 35-45 interactions in 2 seconds.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
