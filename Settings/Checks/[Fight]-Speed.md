Config path: `checks.fight.speed`  
Permission (bypass): `nocheatplus.checks.fight.speed`  
Exemption: `FIGHT_SPEED`  

The Fight.Speed check prevents payers from hitting entities too quickly.

| Option              | Description |
| :------------------ | :---------- |
| limit               | How many clicks per second should players be allowed to perform? |
| shortterm _ticks_   | Ticks to track for the short-term checking. |
| shortterm _limit_   | How many clicks can a player perform in the specified ticks? |
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|


**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [Long-term and Short-term](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Others/Backgrounds.md#long-term-and-short-term)
