Config path: `checks.net.packetfrequency`  
Permission (bypass): `nocheatplus.checks.net.packetfrequency`  
Exemption: `NET_PACKETFREQUENCY`  
Depends on: `ProtocolLib (plugin)`  

This check limits the overall amount of packets a player can send in one time-frame. 

| Option              | Description |
| :------------------ | :---------- |
| limitpersecond      | Maximum amount of packets that NCP will accept in one second |
| seconds             | Seconds that the check will use in its internals to determine how long it should last.|

**Note**
* It shouldn't be possible to crash/harm servers by flodding them with packets since 1.9, but if you notice further packet-based exploits in newer versions, then force-enabling this check
might be useful.    

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
