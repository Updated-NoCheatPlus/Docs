Config path: `checks.inventory.inventorymove`  
Permission (bypass): `nocheatplus.checks.inventory.inventorymove`  
Exemption: `INVENTORY_INVENTORYMOVE`  

InventoryMove checks for illegal inventory interactions (e.g.: while sneaking, swimming, etc...)

| Option | Description |
| :----- | :---------  | 
| disable_creative | Set to true if you want InventoryMove to skip players in creative mode.|
| hdist_leniency | The maximum difference between the last registered horizontal move and the current horizontal distance for the "moving" subcheck.|
| hdist_diff| The minimum horizontal distance required for the moving sub-check to activate.|

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
