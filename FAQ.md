**Table of Contents**
* [Why is aimbot/killaura not detected by NoCheatPlus?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#why-is-aimbotkillaura-not-detected-by-nocheatplus)
* [I want NoCheatPlus to only block fly cheats while still allowing speed hacks (or viceversa). How can I do it?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#i-want-NoCheatPlus-to-only-block-fly-cheats-while-still-allowing-speed-hacksor-viceversahow-can-i-do-it)
* [Why does NoCheatPlus not detect NoKnockback?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#why-does-nocheatplus-not-detect-noknockback)
* [How can I make NoCheatPlus so that it only notifies about potential cheaters instead of canceling actions?](https://github.com/Updated-NoCheatPlus/Docs/blob/e7dfa1215da46bdf70a024501be2f2af600c2976/FAQ.md#how-can-i-make-nocheatplus-so-that-it-only-notifies-about-potential-cheaters-instead-of-canceling-actions)
* [Why use NoCheatPlus instead of plugin X?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#nocheatplus-does-not-block-any-hacks-on-my-server-i-can-login-with-any-hack-client-and-grief-as-much-as-i-want-without-getting-blocked)
* [NoCheatPlus does not block any hacks on my server, I can login with any hack client and grief as much as I want without getting blocked?](FAQ#nocheatplus-does-not-block-any-hacks-on-my-server-i-can-login-with-any-hack-client-and-grief-as-much-as-i-want-without-getting-blocked)
* [I gave my friend permissions for a mod but he stills get blocked by NoCheatPlus?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#i-gave-my-friend-permissions-for-a-mod-but-he-stills-get-blocked-by-nocheatplus)
* [Will NoCheatPlus support plugins like mcMMO and Citizens out of the box?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#will-nocheatplus-support-plugins-like-mcmmo-and-citizens-out-of-the-box)
* [Why isn't cncp (CompatNoCheatPlus) already integrated in NoCheatPlus?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#why-isnt-cncp-compatnocheatplus-already-integrated-in-nocheatplus)
* [Can I use NoCheatPlus with another anti-hack plugin?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#can-i-use-nocheatplus-with-another-anti-hack-plugin)
* [Why do you have commands like /ncp ban, /ncp kick and other?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#why-are-commands-like-ncp-ban--or-ncp-kick--used-in-the-configuration-instead-of-the-default-commands)
* [Is banning based on check alerts encouraged?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#is-banning-based-on-check-alerts-encouraged)
* [Where is the "donate" button?](https://github.com/Updated-NoCheatPlus/Docs/blob/master/FAQ.md#where-is-the-donate-button)

### Why is aimbot/killaura not detected by NoCheatPlus?
The principle of NCP as an _anticheat_ and **not** a _cheat-detector_ is rather to find envelopes/models to fit around legit behaviour: instead of detecting a specific cheat implementation type --in this case, kilaura-- we track down what’s possible for a player to do and _enforce_ that.
NCP’s suit of combat checks serve this exact purpose; they attempt to create an even fight envelope by enforcing limits to players, blocking everything that’s clearly unlegit or potentially gamebreaking (E.g.: Instant turning, hitting 2+ entities at the same time, hitting at insane speeds etc…) so that legit players have a chance against cheaters as well.
Unfortunately, unlike in the movement area, combat cannot be modelled upon by us. Movement cheats are meant to leave vanilla envelopes which can be tracked down and then be enforced to players, whereas combat hacks simply try to simulate a legit, player-like behaviour so there’s nothing that we can realistically “enforce”.  

### I want NoCheatPlus to only block fly cheats while still allowing speed hacks (or viceversa). How can I do it?
The main check for player movement is [SurvivalFly](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Survivalfly.md), which currently does not discern horizontal from vertical speed. This may change in the future, for the time being however, if your only concern are vertical-oriented cheats (e.g.: fly, step) you can workaround this by editing the [speed limits](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Survivalfly.md) for Survivalfly.
Alternatively, if you want NoCheatPlus to only perform "sanity" checks on player (oten the case for anarchy servers, where you may still want to make sure that players can't crash/harm the server by performing insane moves) you can disable Survivalfly and edit [Creativefly's](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BMoving%5D-Creativefly.md) movement limits to some really high values. 

### Why does NoCheatPlus not detect NoKnockback?
Key issues is that the client is authoritative on how it responds to velocity, the latency between client and server makes it extra hard for us to detect such cheat as well. Something is already in the works, however. (Moving.UnusedVelocity).

### How can I make NoCheatPlus so that it only notifies about potential cheaters instead of canceling actions?
If you want NCP to work silently (for all or just some checks), remove the `cancel` flag under each check `actions`.
E.g.: `cancel vl>100 log:angle:6:5:i cancel vl>800 log:angle:0:20:if cancel` -> `vl>100 log:angle:6:5:i vl>800 log:angle:0:20:if`.
Please do note that it might be dangerous to indiscriminately remove all cancel flags, as cheaters could exploit this to crash and/or lag the server or other players. (E.g.: Removing all cancel flags from Survival/Creativefly will allow cheaters to perform very large movements, causing extra load to the server to process such moves. Not canceling illegal packets detected by FlyingFrequency and PacketFrequency is also not recommended, as cheaters could otherwise use magnet/paralyse-like cheats to freeze other players)

### Why use NoCheatPlus instead of plugin X?
It is up to you! NoCheatPlus puts emphasis on configurability allowing you to choose when to kick, ban, log, do anything at all, also allowing to adjust a lot of parameters to tweak checks for your needs. Other plugins may put emphasis on simplicity of configuration. All plugins strive to work fine "out of the box" without need to adapt much. Of course every plugin might have strengths and weaknesses on different fields, also consider that NoCheatPlus is both free and open source.

### NoCheatPlus does not block any hacks on my server, I can login with any hack client and grief as much as I want without getting blocked?
You probably have OP or permissions (administrator or owner rank) on your server which let you bypass all the NoCheatPlus checks. So if you want to test then deop yourself and set your rank to default. Also make sure your Minecraft version matches the version NoCheatPlus has been compiled for, it can be seen on the download pages of BukkitDev or simply using /version NoCheatPlus or /nocheatplus version

### I gave my friend permissions for a mod but he stills get blocked by NoCheatPlus?
After giving permissions to a player, he/she has to relog to activate their mods they got permissions for. Be warned: `nocheatplus.mods.zombe.fly` for example only gives the permission to enable zombes fly mod, you will also need the `nocheatplus.checks.moving.survivalfly` permission to make it work right.

### Will NoCheatPlus support plugins like mcMMO and Citizens out of the box?
NoCheatPlus does not have any special plugin dependencies built in, because they delay the update process of our plugin. Instead we provide you with a compatibility bridge called [CompatNoCheatPlus].  
CompatNoCheatPlus simply connects NoCheatPlus (reason why it needs to be installed alongside CNCP also) with other plugins such as [mcMMO], [Citizens] and others using the powerful [NoCheatPlus API](API) to make them compatible together.  
If you would like to suggest or implement another plugin compatibility in CompatNoCheatPlus then contact @xaw3ep or @CaptainObvious0 for additional support.

### Why isn't cncp (CompatNoCheatPlus) already integrated in NoCheatPlus?
Because it would slow down the development of NoCheatPlus, we would always have to keep up with the other plugins if those get changed, also changes to NoCheatPlus might break compatibility with other plugins, so we would have to fix those too or remove the broken hooks. Also the testing for those components takes a lot of time and can't really be done by us. We might at some point build in a couple of generic things that will help with _some_ compatibility issues without endangering us of getting stuck with compatibility issues.

### Can I use NoCheatPlus with another anti-hack plugin?
Two plugins usually are not better than one. Just activate the few checks of the other plugin that you assume to be useful, disable the rest. Don't have both plugins check for the same things. The typical problems are that checks or the the whole plugins... a) become less effective, because one plugin won't even register actions that a player did, due to the other plugin having cancelled the action already, which can happen to both plugins, due to differing limits... b) that the same kind of checks conflict in taking back players actions, leading to unpleasant emergent effects, such as allowing flying with multiple fly checks being activated (also thinkable with built-in the vanilla fly check, thus let a plugin check for flying, setting allow-flight to true).

### Why are commands like 'ncp ban ...', or 'ncp kick ...' used in the configuration instead of the default commands?
Those are auxiliary commands used for actions, at some point in history the default commands had been lacking some functionality or we wanted to both kick and ban at once.

### Is banning based on check alerts encouraged?
We don't encourage banning in general, because checks can have false positives and nowadays cheat clients adapt pretty well to the boundaries set by NoCheatPlus, so the "good ones" won't even create many violations. It does depend on the individual check, how it is affected by latency or lag or randomness, though. With the right choices, temp-banning could make sense for combinations of checks+alert-levels, if they are not too much influenced by random events or lag or latency.

### Where is the "donate" button?
It has been removed for the time being. We might re-add it once we are in need of donations.

**Related**  
* [Known Issues](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Known-Issues.md).

[CompatNoCheatPlus]:https://dev.bukkit.org/bukkit-plugins/compatnocheatplus-cncp/
[mcMMO]:https://dev.bukkit.org/bukkit-plugins/mcmmo/
[Citizens]:https://dev.bukkit.org/bukkit-plugins/citizens/
