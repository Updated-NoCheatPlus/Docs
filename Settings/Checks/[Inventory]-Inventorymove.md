Config path: `checks.inventory.inventorymove`  
Permission (bypass): `nocheatplus.checks.inventory.inventorymove`  
Exemption: `INVENTORY_INVENTORYMOVE`  

InventoryMove checks for impossible inventory clicks (e.g.: while sneaking, swimming, moving etc...).

| Option | Description |
| :----- | :---------  | 
| disable_creative | Set to true if you want InventoryMove to skip players in creative mode. |
| hdistdivisor | Divisor used to calculate the minimum horizontal distance. Higher the value, less the leniency. |
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data. Currently applies only for clicking in inventory and attacking at the same time.|
| Improbable _weight_ |The weight this check should have when feeding improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
