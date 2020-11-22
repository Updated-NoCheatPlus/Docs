Config path: `checks.fight.selfhit`  
Permission (bypass): `nocheatplus.checks.fight.selfhit`  
Exemption: `FIGHT_SELFHIT`  

This check was originally designed to prevent cheaters from hitting themselves, in order to fly around. This was later on fixed by Mojang.

| Option | Description |
| :----- | :--------- |
| excludeprojectiles| Should SelfHit exclude checking players hitting themselves with projectiles (e.g.: with a bow)?|
| message| Should NCP log a message to players who try to hit themselves with a projectile? |

**Notes**
* Leaving SelfHit enabled wont conflict with Mojangs or Spigots fix on this exploit
* In 1.8 it is possible to fly with a bow (bowfly) so you should still leave this enabled if your server runs in 1.8.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
