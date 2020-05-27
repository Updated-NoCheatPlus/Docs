Config path: `checks.chat.commands`  
Permission (bypass): `nocheatplus.checks.chat.commands`  
Exemption: `CHAT_COMMANDS`  

This check aims to prevent command spamming (player chat only).

| Setting           | Description |
| :---------------- | :---------- |
| exclusions        | A list of case sensitive commands to exclude from the commands check. Commands to match complete words, you cant add "/test" to allow "test123", whereas it is possible to use entries like "/region info" to exclude just that sub command. |
| handleaschat      | Commands entered in this section will get treated as normal chat activity, thus, getting checked by the Text check instead. If you don't enter every PM command here, a player will be able to spam other players in private much easier. |
| level             | Set the total score level at which the commands check will throw 1 violation. |
| shortterm _ticks_ | Number of server ticks to count commands for shortterm checking. |
| shortterm _level_ | Level for which to generate an exception. |

**Related**
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [Captcha](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BChat%5D-Captcha.md)
* [Text](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BChat%5D-Text.md)
* [Long-term and Short-term](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Others/Backgrounds.md#long-term-and-short-term)
