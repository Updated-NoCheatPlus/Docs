Config path: `checks.fight.reach`  
Permission (bypass): `nocheatplus.checks.fight.reach`  
Exemption: `FIGHT_REACH`  

The Fight.Reach check prevents players from _consistenly_ over-reaching.

| Option              | Description |
| :------------------ | :---------- |
| survivaldistance    | Maximum attack distance for survival and adventure gamemode. |
| penalty             | How long should a player have to wait to hit other entities after triggering the check. (ms) |
| reduce              | Whether or not the dynamic _survivaldistance_ feature should be enabled. If players hit too close at the _survivaldistance_, the maximum reach is reduced, so it is harder to use killaura. A player that hits between the dynamic limit and the _survivaldistance_ limit gets a silent penalty without violation level added. |
| precision           | If true, the check will subtract from the calculated reach distance the player's own hitbox radious (0.3 blocks). |
| reducedistance      | Maximum amount of distance by which the _survivaldistance_ can be reduced (Blocks). |
| reducestep          | Takes effect when a player hits at a rather long distance (blocks). This is to prevent killauras getting too many hits in a row at too big distance. |
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable. **NOTE**: the effect is inverted here: higher the value = less the weight this check will have when feeding Improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|

**Notes**
* Because of lag the reach distance isn't a fixed value and may increase/decrease, reach is for that reason designed to be dynamic and adapt to server lag if needed.
* The maximum reach for attacking is set to 3.0 blocks client-side, the server however allows players to hit up to 6 blocks maximum to compensate for latency, this can be easily exploited by cheaters to always attack at the maximum range the server will allow.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
