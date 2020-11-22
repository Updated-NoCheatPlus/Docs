Config path: `checks.blockinteract.visible`  
Permission (bypass): `nocheatplus.checks.blockinteract.visible`  
Exemption: `BLOCKINTERACT_VISIBLE`  
Better with: `ProtocolLib (plugin)`  

Visible uses a simplified method of ray-tracing to prevent players from interacting with blocks that are not in sight at all (such as through walls).

**Notes**
* This check does not cover interactions thru entities such as item frames, paintings, mobs in general.
* Do note that this check will need ProtocolLib in order to mitigate a vanilla bug (packet inversion: the interaction is processed before the looking direction) which causes the check to throw false positives almost everytime you switch block while interacting.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
