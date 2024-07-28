This page lists all the config options that apply to the multiple existing features.  

# Active
This is a simple switch to enable or disable features throughout the configuration.  
**True**: Enables a feature  
**False**: Disables a feature 
<br>**Default**: This feature will be enabled or disabled by NoCheatPlus, based on a determined condition (eg.: if the server is > 1.9)</br>
 

# Set up a custom configuration
We will be using the following string as an example for our walkthrough.
<br>`actions: vl>2 log:fdirectionlowvl:5:6:i vl>10 cancel log:fdirection:2:4:if vl>50 cancel log:fdirection:0:7:icf cmdc:kicksuspiciouscombat:1:5`</br>

## Actions
![actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Resources/actions.png)
The `actions` entry can be considered as NoCheatPlus' task scheduler and can be found at the end of a given check's options. This is the only place where you can control what a check should do after reaching a determined violation level.
* **`vl>X`** To be interpreted literally, it means "violation greater than X". This is used to articulate actions into different intervals. After a player has reached the defined violation threshold, the subsequent interval will be executed. In other words, the `vl>X` is a limiter to how many actions can be performed in a given interval.<br>
Intervals can be ommitted altogether, meaning: you can tell NoCheatPlus to perform a single and specific action at any violation level (e.g.: `actions: log:fdirection:10:10:icf`), but the `actions` section cannot be left blank as a whole.<br>
The first interval may be left undefined at the start (e.g.: `vl>2 cancel (...)`).<br>
* **`cancel`** is the flag used to indicate that an action is to be cancelled, this can have several meanings: 
<br>-Cancel an event (prevent) (i.e.: prevent illegal moves by setting the player back, or cancel illegal hits in combat.);
<br>-Undo actions done by players in some other way (i.e.: restore altered fall damage or fall distance);
<br>-Do something that should've been done (enforce) (i.e.: enforcing damage if players ignore its source (GodMode));
<br>Note that the `cancel` flag currently supports cancellation with probability: instead of cancelling an action 100% of the time, you can tell NoCheatPlus that said action only has a probability of actually getting cancelled, by specifying the probability in percentage (`x%`) before the cancel flag (e.g.: `10%cancel`). Can be used in combat, for instance, to not immediately cancel a hit.

<br>_Taking the previously illustrated example:_</br>
* Interval 1: If players don't reach at least 2 VL, NoCheatPlus will do nothing, as we don't have anything specified before VL 2. 
* Interval 2: After the player has reached at least a violation level of 3 the `log` action will be executed.
* Interval 3: After a violation level of 10, we then start to cancel whatever has been detected by the check and execute the `log` action.
* Interval 4: In the final interval, after a player has reached VL 50, we cancel, then `log` and finally, we execute the `cmdc` action (which will kick the player in this case).

## Strings usage
Strings are defined at the file's bottom part; you can think of them as aliases.
A string can be used to either log something into NoCheatPlus' logging stream or execute a command. This enables server owners to do almost anything they wish to do upon detections.
* **`cmd`** and **`cmdc`** are used to tell NoCheatPlus to execute a command action. The latter will force NoCheatPlus to recognize color codes (`&`).
* **`log`** is used to tell NoCheatPlus to log a message into its logging stream (console, in-game or flat file).
<br>The template for strings is as it follows:</br> 
![StringsExplenation](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Resources/StringsExplenation.gif)
<br>Do note that normal messages need start and ending quotes. (eg.: 'your message here').<br>

<br>_Taking the previously illustrated example:_</br>
* The default message for the `fdirectionlowvl` string is as it follows:
<br>`fdirectionlowvl: '&c[player]&7 failed &c[check]&7: could be using an aimbot (hit not canceled) &7(&cVL[violations]&7)'`</br>
* While the command for `kicksuspiciouscombat` is like this:
<br>`kicksuspiciouscombat: ncp kick [player] &c&l(!)&7 Illegal combat modifications.`</br>

## Actions format
In order for actions to be recognized by NoCheatPlus, they need to respect a specific format. If an action is not formatted correctly, NoCheatPlus will fallback to the default actions for that check.
* The format used for **`log`** actions is: **`log:string:delay:cooldown:target`**.
* For **`cmdc`**/**`cmd`** actions, the `target` part _has_ to be omitted, while `delay` and `repeat` _can_ be removed or specified, at your discretion: (**`cmd(c):yourcommandhere[:delay:cooldown]`**).
* The `delay` part tells NoCheatPlus how many failed checks it has to wait before actually logging the action. This is used if you feel like a check is throwing too many false positives and you want to log your string only if a player fails the check multiple times within a minute. 
* The `cooldown` is used to indicate how many seconds have to pass before NoCheatPlus can log an action once again. This is needed to prevent the spam of multiple actions in a given interval. Usually a value of 5 seconds is acceptable. It is recommended to at least enforce a one second cooldown.
* The `target` part is used to indicate where NoCheatPlus should log a `log` action. `i` stands for in-game chat, `c` stands for console, `f` stands for file. The order is at your discretion (`icf`, `cfi`, `ifc` etc..) , however, at least _one_ log destination has to be specified.
* The `cancel` action does not need to respect a fixed order (e.g.: `log:yourstringhere:3:0:icf cancel` or `cancel log:yourstringhere:3:0:icf`).
<br>Colons are used to separate arguments from one another.</br>

_As always, we'll be taking the previously illustrated string as an example:_
* `log:fdirectionlowvl:5:6:i`: This will let NoCheatPlus know that it needs to log the `fdirectionlowvl` string only in the in-game chat (`i`), every `5` failed checks, with a cooldown of `6` seconds.
* `cmdc:kicksuspiciouscombat:1:5`: This will let NoCheatPlus know that it needs to execute the `kicksuspiciouscombat` command after failing the check `1` time, with a cooldown of `5` seconds. Since **`cmdc`** is used, color codes will be used.


# Placeholders
There are a few placeholders available which can be used to display more in-depth information in strings and to further customize actions.
| Placeholder    | Description  | Check |
| :------------- | :------------| :------------|
|`[player]` | Display the name of the player.| `All` |
|`[IP]` | Display a player's IP.| `Chat.Text`, `Chat.Commands`, `Chat.Login`, `Chat.Relog` |
|`[reachdistance]` | Display the reach distance in blocks.| `Block*.Reach`, `Fight.Reach`|
|`[tags]` | Generic tag used to display a specific check's information (Eg.: with SurvivalFly, this will display the triggered subchecks).| `Moving.*`, `Net.AttackFrequency`, `Fight.Angle`, `Fight.Critical`, `Combined.Improbable`, `BlockPlace.AutoSign`, `Inventory.InventoryMove`, `Inventory.FastConsume`, `BlockPlace.Scaffold` |
|`[packets]` | Generic tag used to display a certain packet (Eg.: with MorePackets, this will display the amount of move-packet received, with AttackFrequency, the attack-packets and so on).| `Net.AttackFrequency`, `Moving.MorePackets`, `Moving.Vehicle.MorePackets` | 
|`[limit]` | Display the limit of a specific check (Eg. with Fight.Speed, this will display the established limit in the config).| `Fight.Speed`, `Net.AttackFrequency`|
|`[violations]` | Returns the current violation level reached by the player.| `All` |
|`[food]` | Used by FastConsume and InstantEat, it will display the food type that the player attempted to fast-use.| `Inventory.InstantEat`, `Inventory.FastConsume` |
|`[check]` | Returns the check's name.| `All` |
|`[locationto]` | Returns the coordinates where the player moved to.| `Moving.SurvivalFly`, `Moving.CreativeFly`, `Moving.Passable`, `Moving.Vehicle.Envelope` |
|`[locationfrom]` | Returns the coordinates where the player moved from.| `Moving.SurvivalFly`, `Moving.CreativeFly`, `Moving.Passable` |
|`[distance]` | Returns the horizontal distance that the player has covered with one move.| `Moving.SurvivalFly`, `Moving.CreativeFly`, `Moving.Passable`, `Moving.Vehicle.Envelope` |
|`[health]` | Returns a player's health in hearts.| `Fight.GodMode`, `Fight.FastHeal` |
|`[blocktype]` | Display a block's name for which the player tried to interact or phase through.| `Moving.Passable`, `BlockBreak.FastBreak`, `BlockPlace.Against` |
|`[model]` | Display CreativeFly's current movement model. | `Moving.CreativeFly` |


**Notes**
* Remember that NoCheatPlus will still load up the check on start-up even if its set to false.  
* Do note that some checks and/or modules might depend on other features to be enabled in order to work (eg.: disabling NoFall will partially cripple the Critical check)
* For some checks immediate kicking of players is not recommended, because it can conflict with the set-back logic or further event-processing, such as with the flying checks - for those we recommend to use the command prefix "ncp delay", in order to run the actions outside of the event processing.
* Always make sure to cancel first before you kick player to avoid exploits with checks not canceling properly.

**Related**
* [Violations](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Others/Backgrounds.md#violations)
