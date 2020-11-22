Config path: `checks.combined.yawrate`  
Permission (bypass): `nocheatplus.checks.combined.yawrate`  
Exemption: `COMBINED_YAWRATE`  

Yawrate monitors how quickly players turn around to perform certain actions (most important, to attack) by checking how quickly the yaw-change rate varies over time. 

| Option             | Description |
| :----------------- | :---------- |
| rate               | Yaw speed change rate allowed without triggering a fight penalty. Set to 360 if you want to steer clear from any possible false positive, although this will only prevent extremely fast-turning killauras |
| penalty _factor_   | How many times should the counted penalties be multiplied? 2.0 is already double. |
| penalty _minimum_  | Set minimal amount of attacking penalty in milliseconds for every violation of Yawrate. |
| penalty _minimum_  | Set maximum amount of attacking penalty in milliseconds for every violation of Yawrate. |
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data. NOTE: if you set this to true, YawRate will still work and *silently* give players penalties. See `checks.fight.yawrate.active` if you want to completely disable this check|
| Improbable _weight_ | The weight this check should have when feeding improbable. **NOTE**: the effect is inverted here: higher the value, less the weight this check will have when feeding Improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|

**Related**
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [Improbable](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BCombined%5D-Improbable.md)
