Config path: `checks.net.flyingfrequency`  
Permission (bypass): `nocheatplus.checks.net.flyingfrequency`  
Exemption: `NET_FLYINGFREQUENCY`  
Depends on: `ProtocolLib (plugin)`  

Check aimed at catching packet manipulation/spam. It prevents extremely fast ticking by just sending packets that don't do anything new and also don't trigger moving events in CraftBukkit.    

| Option              | Description |
| :------------------ | :---------- |
| seconds             | Seconds used within the internals of the check: a violation will be triggered if (Total packet score / _seconds_ > _packetsperseconds_)|
| packetspersecond    | Amount of packets per seconds tolerated. |

**Note**

* When a flying packet gets canceled, the position of the player _won't_ get updated to the server but they will still be able to move client-side; this will result in a _server-sided_ freeze. When the player thaws out of this state, all their movements will be sent as a batch, making them look like as if they were speeding, causing (high) violations in SurvivalFly. Hence why it's not recommended to immediately cancel packets here.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
