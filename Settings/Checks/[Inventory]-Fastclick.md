Config path: `checks.inventory.fastclick`  
Permission (bypass): `nocheatplus.checks.inventory.fastclick`  
Exemption: `INVENTORY_FASTCLICK`  

FastClick limits the amount of clicks a player can perform inside an inventory.   

| Option              | Description |
| :------------------ | :---------- |
| sparecreative       | Set this to true if you don't want Fastclick to check players that are in creative mode. |
| tweaks1_5           | Set this to true if you want to support the new inventory tweaks that were introduce in Minecraft 1.5 (such as inventory painting). |
| limit _shortterm_   | How many clicks should a player be able to perform in one tick (50ms) ?|
| limit _normal_      | How many clicks should a player be able to perform in one second? |
| limit _chest_       | The time, in ms, that a player is not allowed to interact with a chest/container if it is below this time after opening. This will force more realistic interaction times, slowing all cheststealer-like cheats down.|
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|

**Notes**
* If you run Minecraft 1.4.x and older then set tweaks1_5 to false.
* This check will also prevent mods such as InvTweaks and similar ones from working right (because they give advantage compared to vanilla players), if you want your players to be able to use those mods then disable this check or give them the right exempt permission.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [Long-term and Short-term](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Others/Backgrounds.md#long-term-and-short-term)
