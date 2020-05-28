Config path: `checks.moving.nofall`  
Permission (bypass): `nocheatplus.checks.moving.nofall`  
Exemption: `MOVING_NOFALL`  

The NoFall check prevents players from manipulating fall damage and fall distance . 

| Option              | Description |
| :------------------ | :---------- |
| dealdamage          | Deal fall damage to players? Note that NCP will use its own onGround logic to apply fall damage to prevent further exploits from clients. Thus, this will also apply to legit players. It's pretty much unbypassable. |
| skipallowflight     | Should NoFall not deal fall damage to players who are set to be allowed to fly when they land on ground?|
| resetonviolation    | Clean Nofall data on attempts to take fall damage while not actually having hit the ground. |
| resetonteleport     | Compatibility fall-back option to clean nofall data after a teleport. |
| resetonvehicle      | Clean the NoFall data after entering a vehicle. Fixes a bug where a player could get killed due to the amount of fall dmg inflicted. Used to be the case on older versions. |
| anticriticals       | If this is set to true, NoFall will set the player's falldistance to 0 if NCP detects the player to be on ground. Prevents most Critical cheats from working correctly (Cheaters will see critical particles client-side, but no real additional damage will be inflicted to the player). See `checks.fight.critical` for more information about this. |

**Notes**
* resetonvehicle was set to true because of a strange bug that killed players when they left a vehicle.
* In Minecraft its possible to fake small amounts of fall damage to get fake critical hits on entities. For that reason we highly recommend to let anticriticals to true unless you have no choice.


**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [SurvivalFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Survivalfly.md)
* [Criticals](https://github.com/Updated-NoCheatPlus/Docs/edit/master/Settings/Checks/%5BFight%5D-Criticals.md)
