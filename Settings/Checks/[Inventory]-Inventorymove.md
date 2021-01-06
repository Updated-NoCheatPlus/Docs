Config path: `checks.inventory.inventorymove`  
Permission (bypass): `nocheatplus.checks.inventory.inventorymove`  
Exemption: `INVENTORY_INVENTORYMOVE`  

InventoryMove checks for impossible inventory clicks (e.g.: while sneaking, swimming, moving etc...).

| Option | Description |
| :----- | :---------  | 
| disable_creative | Set to true if you want InventoryMove to skip players in creative mode. |
| hdist_leniency | The difference between current and last horizontal move (A VL will be triggered if (difference < hDistLeniency)). Higher the value, less the leniency. |
| hdist_diff | The minimum horizontal distance required for this check. Higher the value, higher the leniency. |

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
