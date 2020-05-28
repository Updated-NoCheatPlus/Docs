Config path: `checks.fight.fastheal`  
Permission (bypass): `nocheatplus.checks.fight.fastheal`  
Exemption: `FIGHT_FASTHEAL`  

This check prevents players from generating healthy faster then possible.

| Option              | Description |
| :------------------ | :---------- |
| interval            | Interval in ms (milliseconds) between regaining health (from saturation). |
| buffer              | Buffer for which FastHeal will compensate faster health regeneration for (ms). |

**Notes**
* In Minecraft 1.6 and older a player could faster generate health by spamming movement packets, this was later on changed in MC 1.7.x and higher to generate health based on server ticks instead. However there seem to still be some cases left where players seem to still be able to generate health faster which is the reason why we didnt remove Fastheal from NC+.
* FastHeal has been patched by MC itself since 1.9, so it will autodisable itself from 1.9 and onwards versions.
* Fastheal has a buffer to prevent false positives by smoothing out lag spikes
* You want to only adjust the interval if your server heals your players faster/slower for some reason (mods?)

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
