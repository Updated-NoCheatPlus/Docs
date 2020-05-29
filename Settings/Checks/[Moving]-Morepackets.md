Config path: `checks.moving.morepackets`  
Permission (bypass): `nocheatplus.checks.moving.morepackets`  
Exemption: `MOVING_MOREPACKETS`  
Better with: `[Moving] Survivalfly`

The Morepackets check is complementary to the Survivalfly and Creativefly checks. While the other check(s) limit the actual distance a player can move with one server-side event, this check limits the number of steps/events a player may perform within certain time-frames.

| Option                  | Description |
| :---------------------- | :---------- |
| seconds                 | How long the check should last. Higher values compensate for higher latency but it will take longer to setback cheaters. |
| epsideal                | The ideal amount of packets that NCP will expect a player to send. |
| epsmax                  | The maximum number of events per second tolerated (in average). |
| burst                   | The burst mechanics allow MorePackets to keep track of packet rates in a longer run|
| burst _packets_           | The number of move-packets arriving within 500ms to trigger a burst-event (*not* a VL). All packets above this count arriving within the same time window will increase the burst counting. |
| burst _directviolation_ | Amount of burst packets to trigger a violation directly, without even considering to calculate any mid-term average. With burst packets set to 40 and directviolation set to 60, more than 100 packets within the first time window will trigger the direct violation. This may seem much, but 5 seconds worth of lag happen more often than expected with the client side. |
| burst _epmviolation_     | Amount of burst events per minute to trigger a violation. Note that only bursts (...) get counted in here, as configured with burst.packets. |
| setbackage              | After how many PlayerMoveEvents should the setback be executed/expire? The higher this value is, the longer the execution of the setback will be; if not careful, players may start noticing getting setbacked over really long/big distances.

**Notes**
* A normal value is 20 steps per second.

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
