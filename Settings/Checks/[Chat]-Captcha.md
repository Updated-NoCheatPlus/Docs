Config path: `checks.chat.captcha`  
Permission (bypass): `nocheatplus.checks.chat.captcha`  
Exemption: `CHAT_CAPTCHA`  
Depends on: `[Chat] Commands` or `[Chat] Text`

The captcha feature can be used together with our text or commands spam check to ask players that fail one/both of those a randomly generated captcha, which needs to be answered in order to continue.

| Option           | Description |
| :--------------- | :---------- |
| characters       | Which chars (numbers, letters and symbols) should be used to generate a captcha? |
| length           | How many chars should the captcha have? |
| question         | The message that will be sent to players upon triggering a chat-related check (Text/Commands), the text [captcha] will be replaced with the actual captcha. |
| success          | Set the message which will be shown to the player if they answer correctly. |
| tries            | Max tries before a player will get kicked from the server. Be generous here, as players may not be fast enough to read the question the first few times or be otherwise distracted. |

**Related**  
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [Text](https://github.com/Lysandr0/Docs/blob/master/Settings/Checks/%5BChat%5D-Text.md)
* [Commands](https://github.com/Lysandr0/Docs/blob/master/Settings/Checks/%5BChat%5D-Commands.md)
* [Formatting codes](http://minecraft.gamepedia.com/Formatting_codes)
