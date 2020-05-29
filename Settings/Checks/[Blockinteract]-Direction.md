Config path: `checks.blockinteract.direction`  
Permission (bypass): `nocheatplus.checks.blockinteract.direction`  
Exemption: `BLOCKINTERACT_DIRECTION`
Better with: `ProtocolLib (plugin)`  

The Direction check forces players to look (eye location) at the block they want to interact with.

**Notes**
* The BukkitAPI throws a interaction event before the place/break events come, so the BLOCKINTERACT_DIRECTION check will pretty much always catch the cheat attempt first before the other two do. If you wish to only check Direction on placing/breaking then disable the interaction one first.
* Do note that this check will need ProtocolLib in order to mitigate a vanilla bug (packet inversion: the interaction is processed before the looking direction) which causes the check to throw false positives almost everytime you switch block while interacting.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
