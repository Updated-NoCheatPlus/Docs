Config path: `checks.blockplace.speed`  
Permission: `nocheatplus.checks.blockplace.speed`  
Exemption: `BLOCKPLACE_SPEED`  

The BlockPlace.Speed check prevents players from throwing projectiles (experience bottles, eggs, monster eggs, eyes of ender, ender pearls) too quickly.

| Option    | Description |
| :-------- | :---------- |
| interval  | The time (in milliseconds) between each thrown projectile. In theory it takes more than 150 ms if the player is keeping their right button pressed. Lower the value, the quicker the time players can throw projectles. |
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable.|


**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
