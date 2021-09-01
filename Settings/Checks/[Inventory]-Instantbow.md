Config path: `checks.inventory.instantbow`  
Permission (bypass): `nocheatplus.checks.inventory.instantbow`  
Exemption: `INVENTORY_INSTANTBOW`  

This check will make sure that your players use the proper fire speed to shoot arrows with a bow. InstantBow will take actions against players that try to go over the allowed limit.

| Option              | Description |
| :------------------ | :---------- |
| strict              | If set to true, this monitors time from pulling to firing. If set to false, this only regards the time between shots - use for problems with lag/latency, at the cost of allowing one instant shot always. |
| delay               | The legit speed NCP will accept from pulling the string to the actual shot. |

**Related**  
* This check will auto-disable itself on newer versions (1.9+) since it's not possible to use this kind of cheat anymore.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
