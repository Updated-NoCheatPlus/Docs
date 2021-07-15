This section of the configuration file provides you with additional settings to improve overall compatibility stuff.
# Exemptions
|**Option**|**Meaning**|
| :--------|:----------|
| _wildcard default metadata_ active | TODO |
|_wildcard default metadata_  keys | TODO |
|_wildcard_ npc | TODO |
| _npc_ active | TODO |
| _npc_ bukkitnpc | TODO |
| _npc metadata_ active | TODO |
| _npc metadata_ keys | TODO |
| _remove_ join | TODO |
| _remove_ leave | TODO |

# Server
|**Option**|**Meaning**|
| :--------|:----------|
| cbdedicated| If true, NoCheatPlus will use its dedicated module for the detected server version, currently supports 1.5 to 1.12.|
| cbreflection | Resort to the BukkitAPI if no dedicated module is present. Applies from MC 1.13+ and on. |

# Blocks
|**Option**|**Meaning**|
| :--------|:----------|
|breakingtime| Enables you to override the breaking time of a block for specific side conditions. An entry in this section maps a condition definition to the breaking time in milliseconds. Definitions for side conditions can be: BLOCK_TYPE:TOOL_TYPE:TOOL_MATERIAL_BASE:EFFICIENCY_LEVEL. In-air/water/aqua-affinity/haste are not possible to add at this stage. Those will get automatically evaluated. Later specifying these will be possible.|
| allowinstabreak | Blocks entered here will not be verified by the FastBreak check, meaning the player will be able to mine them at whichever speed.|

Example of breakingtime:
<br> `SAND:AXE:DIAMOND:0: 10000`</br> 
(Changes the breaking time for sand with a diamond axe with no efficiency enchantment to 10 seconds, thus fastbreak will trigger).
 
Use of breakingtime parameters:
<br> ` BLOCK_TYPE`: Bukkit block names. Currently no extras are possible, such as data values/variants.</br>
<br> `TOOL_TYPE`: `NONE, SWORD, SHEARS, SPADE, AXE, PICKAXE, HOE`</br>
<br> `TOOL_MATERIAL_BASE`: `NONE, WOOD, STONE, IRON, DIAMOND, NETHERITE, GOLD`</br>
<br> `EFFICIENCY_LEVEL`: Level of the efficiency enchantment.</br>

|**Option**|**Meaning**|
| :--------|:----------|
| overrideflags | This section allows you to tell NCP how to interpret the shape of blocks (if you can walk on them, walk through them and the like) by using flags. Using the `default` flag will let NCP use the flags that have already been initialized, useful in the case you only want to add one specific flag for a block (Use where you know what it means, set `checks.blockbreak.debug` to true, in order to dump the flags that NCP is using internally to the log-file). |

Example to both pass through and stand on: <br>
`default+ign_passable+ground_height`</br>
(It's recommended to set dimensions too, if possible.)

Currently, NoCheatPlus supports the following flags:
|**Flag**|**Meaning**|
| :--------|:----------------------------|
| F_STAIRS | Indicator flag for stairs. |
| F_LIQUID | Indicator for all liquid types. |
| F_NEWLIQ | Indicator flag for 1.13 liquids proprieties.|
| F_WATER | Like water. |
| F_LAVA | Like lava. |
| F_CARPET | Inidicator flag for carpets. |
| F_COBWEB | Cobweb-like blocks, adhesive.|
| F_COBWEB2 | Inidicator flag for berry bushes which have similar movement to webs but allow for faster speed and jump at 3/4 of block height. |
| F_SOULSAND | Indicator flag for soul-sand. |
| F_BUBBLECOLUMN | Indicator flag for bubble column block. |
| F_STICKY | Indicator flag for the honey block which upon collision will slow down the player and half the fall damage. |
| F_RAILS | All rails types a minecart can move on. |
| F_ICE | Indicator flag for all ice types, which will allow the player to slide on them, increasing their horizontal speed. |
| F_LEAVES | Indicator flag for all leaves. |
| F_SLIME | Indicator flag for slime, just to distinguish it from other bouncy blocks, like beds. |
| F_ANVIL | Indicator flag for anvils. |
| F_THIN_FENCE | Indicator flag for panes and iron bars. |
| F_THICK_FENCE | Indicator flag for walls and fences (e.g.: cobblestone wall). |
| F_FAKEBOUNDS | Flag used to activate a workaround for the edges of thin fences (iron bars and glass panes) on 1.8 server (which are bugged and would trigger the Passable check when colliding on them XZ). |
| F_SOLID  | Result of Minecraft's isSolid. Used for setting the ground flag. |
| F_IGN_PASSABLE | Indicate that this block is fully passable (used for compatibility). |
| F_GROUND | The player can stand on this block sneaking or not. |
| F_HEIGHT_100 | This block is 1 block high. |
| F_HEIGHT_150 | This block is 1.5 blocks high, like fences.|
| F_CLIMBABLE | This block is a climbable one, which currently will allow to land without taking fall damage, like ladders and vines.|
| F_CLIMBUPABLE | This block is climbable upwards under special conditions like vines, which are climbable only if attached to a block.|
| F_ CLIMBLIQ | This block is climbable in water, used for 1.13 kelp plants.|
| F_VARIABLE | The block can change shape. |
| F_XZ100 | The block has full xz(horizontal)-bounds, like a normal block (eg.: stone).|
| F_GROUND_HEIGHT | This flag indicates that everything between the minimum ground height and the height of the block can also be stood on. In addition this flag directly triggers a passable workaround for otherwise colliding blocks. |
| F_HIGHT_8SIM_DEC | The height is assumed to decrease from 1.0 with increasing data value from 0 to 0x7, with 0x7 being the lowest. (repeating till 0x15)). 0x8 means falling/full block. This is meant to model flowing water/lava. However the hit-box for collision checks  will be set to 0.5 height or 1.0 height only.|
| F_HEIGHT_8SIM_INC | The height is assumed to increase with data value up to 0x7, repeating up to 0x15. However the hit-box for collision checks  will be set to 0.5 height or 1.0 height only, as with the 1.4.x snow levels.|
| F_HEIGHT_8_INC | The height increases with data value (8 heights). This is for MC 1.5 snow levels. |
| F_COLLIDE_EDGES | Meta-flag to indicate that the (max.-) edges should mean a collision. |
| F_PASSABLE_X4 | At its 0x04 status, this block is fully passable, like fence gates. |
| F_BOUNCE25 | Slime block-like blocks. Bounce back 25% of fall height without taking fall damage. |
| F_FACING_LOW3D2_NSWE | The facing direction is described by the lower 3 data bits in order of NSWE, starting at and defaulting to 2, which includes invalid states. Main purpose is ladders, no guarantees on defaults for other blocks yet.|
| F_ATTACHED_LOW2_SNEW |The direction the block is attached to is described by the lower 2 bits in order of SNEW.|
| F_ALLOW_LOWJUMP | Allow players to low jump on this block, possibly allowing them to cheat. |
| F_HEIGHT8_1 | One eighth block height (0.125).|
| F_FALLDIST_HALF | Fall distance is divided by 2, if a move goes through this medium (currently only supports liquid). |
| F_FALLDIST_ZERO | Fall distance is set to zero, if a move goes through this medium (currently only supports liquid). |
| F_MIN_HEIGHT16_15 | Minimum height 15/16 (0.9375 = 1 - 0.0625). Only applies with F_GROUND_HEIGHT set.|
| F_MIN_HEIGHT16_14 | Minimum height 14/16 (8750). Only applies with F_GROUND_HEIGHT set.|
| F_MIN_HEIGHT16_13 | Minimum height 13/16 (8125). Only applies with F_GROUND_HEIGHT set.| 
| F_MIN_HEIGHT16_11 | Minimum height 11/16 (0.6875). Only applies with F_GROUND_HEIGHT set.|
| F_MIN_HEIGHT16_9 | Minimum height 9/16 (0.5625). Only applies with F_GROUND_HEIGHT set.|
| F_MIN_HEIGHT16_7 | Minimum height 7/16 (0.4375). Only applies with F_GROUND_HEIGHT set.|
| F_MIN_HEIGHT16_5 | Minimum height 5/16 (0.3125). Only applies with F_GROUND_HEIGHT set. |
| F_MIN_HEIGHT4_1 | Minimum height 1/4 (0.25). Only applies with F_GROUND_HEIGHT set.|
| F_MIN_HEIGHT8_1 | Minimum height 1/8 (0.125). Only applies with F_GROUND_HEIGHT set.|
| F_MIN_HEIGHT16_1 | Minimum height 1/16 (0.0625). Only applies with F_GROUND_HEIGHT set.| 
| F_VARIABLE_USE | Block change tracking: ordinary right click interaction (use) can change the shape. |
| F_VARIABLE_REDSTONE | Block change tracking: block redstone events can change the shape.|
| F_HEIGHT16_15 | Height 15/16 (0.9375 = 1 - 0.0625).|

# Changetracker
This section allows you to alter some option concerning NoCheatPlus' block change tracker system, which allow the moving checks to account for moving blocks (eg.: with pistons).
|**Option**|**Meaning**|
| :--------|:----------|
| active   | Should the change tracker system be active at all? Without it, moving blocks will cause false positives. |
| pistons | Should pistons be covered by the tracker? |
| maxageticks | Maximum age in ticks for which entries will be purged by the tracker system. |
| *perworld* maxentries | Maximum entries per world allowed before being removed. |

**Related**
* [Passable](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Passable.md)
* [FastBreak](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BBlockbreak%5D-Fastbreak.md)
* [BukkitAPI](https://hub.spigotmc.org/javadocs/bukkit)
* [Block names/enum](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
