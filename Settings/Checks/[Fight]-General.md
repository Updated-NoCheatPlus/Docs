This page lists miscellaneous config options regarding fighting.

| Option                  | Description |
| :---------------------- | :---------- |
| canceldead              | Prevent dead players from hitting other players/entities while being still dead. This cancels silently.|
| toolchangepenalty       | Amount of time in ms, that players have to wait to hit an entity after switching item in their hotbar. This is helpful only if you have problems with AutoSwitch/FastSwitch cheats, otherwise leave it disabled as it can impact gameplay/pvp a lot.|
| maxlooplatencyticks     | Maximum latency counted in ticks for the loop checks (direction/reach). Higher the value, higher the leniency for these checks|
| pvp _knockbackvelocity_ | Should NoCheatPlus calculate the knockback velocity resulting from pvp by itself? Since MC 1.8, no velocity is sent by the server for pvp anymore, thus we don't get told by an event that the player is getting pushed. You should not touch this since NCP will automatically enable/disabled it according to the detect version.. Force set with true/false if you have problems with Survivalfly setbacking players in pvp.|
| yawrate _active_        | Yawrate tracks how fast players turn sideways. Having yawrate enabled allows to prevent some types of actions such as turning instantly and hit another player or entity. Also feeds the improbable check.|

**Notes**
* pvp _knockbackvelocity_ has nothing to do with the already removed fight.knockback check.

**Related**
* [Violations](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Others/Backgrounds.md#violations)
* [Yawrate](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BCombined%5D-Yawrate.md)
