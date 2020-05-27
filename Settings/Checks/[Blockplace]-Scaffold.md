Config path: `checks.blockplace.scaffold`  
Permission (bypass): `nocheatplus.checks.blockplace.scaffold`  
Exemption: `BLOCKPLACE_SCAFFOLD`  

The Scaffold check is a multi-module check that attempts to enforce realistic speeds and movements when scaffolding (placing blocks below yourself)

| Option | Description |
| :----- | :--------- |
| angle  | The angle subcheck forces players to look at the block-face they want to place their block on.|
| sprint | Prevents players from sprinting while simultaneously placing blocks below them|
| time _average_| A FastPlace check but for scaffold-type block placements. If all other subchecks fail to detect the cheat this will at least ensure a realistc block placement. If the calculated average time is inferior to this value, Scaffold will trigger.|
| rotate _difference_| The rotate subecheck checks for large changes in rotation between block placements. If the calculated difference is bigger than the set difference, Scaffold will trigger|
| toolswitch| The toolswitch subcheck checks if the player is quickly switching inventory slots between block placements|

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
