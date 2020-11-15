Config path: `checks.moving.nofall`  
Permission (bypass): `nocheatplus.checks.moving.nofall`  
Exemption: `MOVING_NOFALL`  

The NoFall check prevents players from manipulating fall damage and fall distance . 

| Option              | Description |
| :------------------ | :---------- |
| dealdamage          | If this is option is set to false, fall damage will be disabled altogether. NCP will *override* Minecraft's onGround logic and use its own to apply fall damage to players, in order to prevent further exploits from clients. Thus, this will also apply to legit players. It's pretty much unbypassable. |
| skipallowflight     | Should NoFall not deal fall damage to players who are set to be allowed to fly when they land on ground?|
| resetonviolation    | Clean Nofall data on attempts to take fall damage while not actually having hit the ground. |
| resetonteleport     | Compatibility fall-back option to clean nofall data after a teleport. |
| resetonvehicle      | Clean the NoFall data after entering a vehicle. Fixes a bug where a player could get killed due to the amount of fall damage inflicted. Used to be the case on older versions. |
| anticriticals       | If this is set to true, NoFall will set the player's falldistance to 0 if NCP detects the player to be on ground. Prevents most Critical cheats from working correctly (Cheaters will see critical particles client-side, but no real additional damage will be inflicted to the player). See `checks.fight.critical` for more information about this kind of cheat. |

**Tags**
* `fakefall`: The player attempted to fake fall distance in order to get fall damage while still being on the ground.
* `fakeground`: The player tried to get fall damage while still being airborne. Usually done by faking the onGround flag to true while in air.

**Notes**
* The NoFall check does not directly detect NoFall cheats, instead, we calculate fall distances on our own and apply fall damage to players accordingly.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [SurvivalFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Survivalfly.md)
* [Critical](https://github.com/Updated-NoCheatPlus/Docs/edit/master/Settings/Checks/%5BFight%5D-Criticals.md)
