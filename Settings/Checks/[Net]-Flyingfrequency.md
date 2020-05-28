Config path: `checks.net.flyingfrequency`  
Permission (bypass): `nocheatplus.checks.net.flyingfrequency`  
Exemption: `NET_FLYINGFREQUENCY`  
Depends on: `ProtocolLib (plugin)`  

Check aimed at catching packet manipulation/spam. It prevents extremely fast ticking by just sending packets that don't do anything new and also don't trigger moving events in CraftBukkit     

| Option              | Description |
| :------------------ | :---------- |
| seconds             | Seconds used within the internals of the check: a violation will be triggered if (Total packet score / _seconds_ > _packetsperseconds_)|
| packetspersecond    | Amount of packets per seconds tolerated. |
| cancelredundant     | TODO: |
| reduceredundant _seconds_| TODO:  |

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
