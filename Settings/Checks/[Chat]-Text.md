Config path: `checks.chat.text`  
Permission (bypass): `nocheatplus.checks.chat.text`  
Exemption: `CHAT_TEXT`  

Advanced check designed to prevent chat spam and floodding.  

| Option           | Description |
| :--------------- | :---------- |
| allowvlreset     |  |

## Frequency
This check is split in two in order to cover both faster and slower types of chat spamming.  

### Normal
First module of the Text.frequency check: the "text.frequency.normal" check keeps track of the server chat activity for about 30 seconds.
Meant to prevent slower types (more annoying) of chat spam.

| Option           | Description |
| :--------------- | :---------- |
| minimum          | Each message sent by the player will at least count in with this weight. (0.0 means not every message will have a weight) |
| factor           | How strong old chat messages should count in, 1.0 would let the check count in fully.  |
| weight           | Multiplier to balance out things, the calculated score will just be multiplied with this. |
| level            | Accumulated score for which to generate a violation for. |

### Shortterm
Second module of the Text.frequency check: the "text.frequency.shortterm" check covers 5 seconds of chat activity, roughly.
Meant to protect the server from obvious spam-bots and/or players intentionally flodding the chat

| Option           | Description |
| :--------------- | :---------- |
| minimum          | Each message sent by the player will at least count in with this weight. (0.0 means not every message will have a weight) |
| factor           | How strong old chat messages should count in, 1.0 would let the check count in fully.  |
| weight           | Multiplier to balance out things, the calculated score will just be multiplied with this. |
| level            | Accumulated score for which to generate a violation for. |

## Message
This section allows you to alter the weights of specific messages

| Option            | Description |
| :---------------- | :---------- |
| lettercount       | Counting the letters versus the word length. Unbalanced counts would be more expensive. |
| partition         | TODO: |
| uppercase         | A message with many caps letter will cost more   |
| afterjoin         | Chatting immediately after join will cost more  |
| nomoving          | Chatting and not having moved _recently_ is also more expensive. |
| repeatviolation   | Repeating a message which has been previously deleted and/or flagged by the Text check will cost more |
| repeatglobal      | Repeating a message that is getting repeated a lot in chat by other players is expensive |
| repeatself        | A player repeating the same message they just sent will cost more. |
| words _lengthav_  | Word length vs. average word length weight, really long words will count in more |
| words _lengthmsg_ | Word length vs. message length weight |
| words _noletter_  | Weight for words that don't contain any letter, only special characters. Will make countdowns harder to get by. Set to 0.0 to disable. |

## Global
Text.Global: uses more extended and advanced methods that are fed by all players messages. 

| Option              | Description |
| :------------------ | :---------- |
| weight              | Multiplier to allow balancing the score result of this check. 1.0 = no change |
| words               | Keeps track of recently spoken words as a whole.|
| prefixes _active_   | Keeps track of recently spoken words, but arranges them to also count in if prefixes of a word are repeated/detected, such as "hello" and "helloccc". Words that just have been used are more "expensive" than old ones. |
| similarity _active_ | Checks words for similarities with the Levenshtein algorithm applied within a metric tree. (most heavy operation, performance-wise) |

## Player
Text.Player: uses more extended and advanced methods that keep track of each player individually.

| Option              | Description |
| :------------------ | :---------- |
| words  _active_     | Keeps track of recently spoken words as a whole.|
| prefixes _active_   | Keeps track of recently spoken words, but arranges them to also count in if prefixes of a word are repeated/detected, such as "hello" and "helloccc". Words that just have been used are more "expensive" than old ones. |
| similarity _active_ | Keeps track of recently spoken words and assigns a higher score with recently spoken words being repeated similarly. |


**Related**   
* [Active](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#active)
* [Actions](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/General.md#actions)
* [Captcha](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Settings/Checks/%5BChat%5D-Captcha.md)
* [Long-term and Short-term](https://github.com/Updated-NoCheatPlus/Docs/blob/master/Others/Backgrounds.md#long-term-and-short-term)
