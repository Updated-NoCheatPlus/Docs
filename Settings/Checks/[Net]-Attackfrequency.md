Config path: `checks.net.attackfrequency`  
Permission (bypass): `nocheatplus.checks.net.attackfrequency`  
Exemption: `NET_ATTACKFREQUENCY`  
Depends on: `ProtocolLib (plugin)`  

The AttackFrequency check limits the amount attacks a player can perform in multiple time-frames.

| Option              | Description |
| :------------------ | :---------- |
| limitforseconds     | Set the click limit for each established time frame.|
| limitforseconds _half_| How many clicks should players be able to do in 500 milliseconds?|
| limitforseconds _one_| How many clicks should players be able to do in one second?|
| limitforseconds _two_| How many clicks should players be able to do in two seconds?|
| limitforseconds _four_| How many clicks should players be able to do in four seconds?|
| limitforseconds _eight_| How many clicks should players be able to do in eight seconds?|
| Improbable _weight_ | How much weight should this check have when feeding Combined.Improbable? Set to 0.0 to disable.|

**Note**
* It is *extremely* unlikely that a (casual) player can reach 20 CPS and keeping such value for long period of times, anything above 20-ish can be considered as cheating. 

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
