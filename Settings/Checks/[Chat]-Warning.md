Config path: `checks.chat.warning`  
Depends on: `[Chat] Text` or `[Chat] Commands`

Allows you to warn the player of the chat.text and chat.commands weight levels, possibly before a violation is triggered.

| Option         | Description |
| :------------- | :---------- |
| level          | Chance(%) to warn a player.. |
| message        | This message will be sent to all of the players that fail a chat check. |
| timeout        | Time in seconds before warning again (cooldown) (seconds). |

**Notes**
* Currently warning does not necessarily happen before violations are being triggered.
* Color codes are supported in message config
* If for example your CHAT_TEXT_SHORTTERM check has level set to 160 you calculate: (160 / 100) * level you set here in warning. Result= The level at which warning will trigger for CHAT_TEXT_SHORTTERM

**Related**
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Text](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BChat%5D-Text.md)
* [Chat Commands](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BChat%5D-Commands.md)
