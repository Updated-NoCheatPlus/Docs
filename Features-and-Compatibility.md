# General compatibility
NoCheatPlus features a range of compatibility features.
* Compatibility with multiple versions of Minecraft. You can rely on the latest version of NoCheatPlus still running on a range of past versions of Minecraft.
* Configuration allows working around issues with specific blocks (custom mods, early adopter): [Config compatibility settings]
* A range of API features to allow developers to make their plugins compatible (exemption API, exemption by meta data, hooks for violation processing, other).
* Vanilla features. It may not seem worth mentioning, but we can't support all features to arbitrary depths. Still you will find that NoCheatPlus provides a balance between supporting vanilla features, extensions like higher level potion effects and attributes (vanilla too, but usually not encountered without command blocks or adventure maps), and finally protection from abusing those features vs. false positives. Our aim is to support all vanilla features, of course, it's a larger task than you might think.


# Plugin Compatibility
This is a small list of plugins that work together with NoCheatPlus

## Officially supported
Here we list all plugins that use cncp (CompatNoCheatPlus) to support other plugins and enhance compatibility.
* [mcMMO]
* [Citizens 2] (Out of the box)

## Plugins that support NoCheatPlus
Here are all plugins which either use the NC+ API or specially account for NC+ to create a smooth game experience.
* [BungeeNCPNotify] hooks into NoCheatPlus and reports violations (configurable) of certain checks to staff members on other servers.
* [DoubleJump4NCP] Lets you double jump.

[mcMMO]:https://dev.bukkit.org/bukkit-plugins/mcmmo/
[Citizens 2]:https://dev.bukkit.org/bukkit-plugins/citizens/

[DoubleJump4NCP]:https://www.spigotmc.org/resources/doublejump4ncp.1519/
[BungeeNCPNotify]:https://dev.bukkit.org/bukkit-plugins/bungeencpnotify/
[Config compatibility settings]:https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/%5BSettings%5D-Compatibility.creole

