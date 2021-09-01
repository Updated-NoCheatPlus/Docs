Config path: `checks.inventory.fastconsume`  
Permission (bypass): `nocheatplus.checks.inventory.fastconsume`  
Exemption: `INVENTORY_FASTCONSUME`  

Fastconsume replaces the former Instanteat check and extends it by forcing vanilla consume durations on potions, water bottles and more.

| Option              | Description |
| :------------------ | :---------- |
| duration            | How long should it take to consume an item? (seconds) (Legit speed: 1.5s for most items, except dried kelp). |
| whitelest           | True means that Fastconsume will only check the items you have  added in your list. False means that Fastconsume ignores all items you added in your list (option below). |
| items               | You can add items here that you want to whitelist/blacklist from the Fastconsume check. |

**Notes**
* NoCheatPlus will automatically fallback to "Instanteat" if your server does not support the consume event which fastconsume needs to work.
* Setting duration higher will require players more time to consume the item while setting it lower allows them to consume it quicker.
* This check will auto-disable itself in newer versions (1.9+) since it's not possible to use this kind of cheat anymore.

**Related**
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [Instanteat](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BInventory%5D-Instanteat.md)
