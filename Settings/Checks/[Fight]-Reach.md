Config path: `checks.fight.reach`  
Permission (bypass): `nocheatplus.checks.fight.reach`  
Exemption: `FIGHT_REACH`  

The Fight.Reach check prevents players from _consistenly_ over-reaching.

| Option              | Description |
| :------------------ | :---------- |
| survivaldistance    | Maximum attack distance for survival and adventure gamemode. Statically about 3 or 3.5 applies, with latency and moving 4.0 makes sense. |
| penalty             | How long should a player have to wait to hit other entities after triggering the check. (ms) |
| reduce              | Do you want the dynamic reach distance feature enabled? This will adapt a player's reach according to their hit distance instead of hard-fixing their reach to a single value.|
| reducedistance      |  Maximum amount of distance by which the _survivaldistance_ can be reduced (Blocks). If NCP notices that the player is hitting too close to the survivaldistance limit too consistenly, their reach will be silently reduced by this amount without any violation level being added. |
| reducestep          | Takes effect when a player hits at a rather long distance (blocks) , (much longer than the allowed _survivaldistance_ value). This will effectively adapt the allowed hit reach between two values, depending on how far you are off your target when hitting. This is to prevent killauras getting too many hits in a row at too big distance. |
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable. **NOTE**: the effect is inverted here: higher the value = less the weight this check will have when feeding Improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|

**Notes**
* Because of lag the reach distance isn't a fixed value and may increase/decrease, reach is for that reason designed to be dynamic and adapt to server lag if needed.
* The max reach for attacking is set to 3.0/.5 blocks client-side, the server however allows players to hit up to 6 block maximum to compensate for latency, this can be easily exploited by cheaters to always attack at the maximum range the server will allow.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
