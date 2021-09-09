Config path: `checks.blockplace.scaffold`  
Permission (bypass): `nocheatplus.checks.blockplace.scaffold`  
Exemption: `BLOCKPLACE_SCAFFOLD`  

Scaffold is a multi-module check that attempts to enforce realistic speeds and movements when scaffolding (placing blocks below yourself)

| Option | Description |
| :----- | :--------- |
| angle  | The angle subcheck forces players to look at the block-face they want to place their block on.|
| sprint | Prevents players from sprinting while simultaneously placing blocks below them.|
| time _average_| A FastPlace check but for scaffold-type block placements. If all other subchecks fail to detect the cheat this will at least ensure a realistc block placement time. If the calculated average time is inferior to this value, Scaffold will trigger.|
| rotate _difference_| The rotate subecheck checks for large changes in rotation between block placements. If the calculated difference is bigger than the set difference, Scaffold will trigger.|
| toolswitch | The toolswitch subcheck checks if the player is quickly switching inventory slots between block placements.|
| Improbable _feedonly_ | Decide the influence this check should have when contributing to the Improbable check analysis. If false, this check can directly incur Improbable **violations** with its data. If true this check will only contribute in feeding Improbable with its data.|
| Improbable _weight_ |The weight this check should have when feeding improbable. Set to 0.0 if you don't want this check to feed Improbable at all.|

**Notes**
* Keep in mind that legit fast-scaffolding techniques do exist (e.g.: "godbridge") so you may want to tweak Scaffold's time subcheck to your likings, especially on gamemodes where bridging is a core/important mechanic, like Skywars.
* Some Scaffold implementations tend to also trigger MorePackets if turning around too fast.
* Yaw rate is also monitored here. Makes it even harder to do unlikely rotation changes. 

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
