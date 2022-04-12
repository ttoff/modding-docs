This document documents all of the available options in [Toontown Offline's][ttoff] server.json file.

|option|description|default|
|--|--|--|
|server-password|When a password is specified, users will be required to enter this password to connect||
|whitelisted-usernames|A list of Whitelisted usernames. If this is not empty, the server will become whitelisted allowing only usernames within this list to connect|[]|
|default-access-level|New users will be given this access level upon joining the server for the first time|USER|
|minimum-access-level|Users will be required to have this access level to join the server - NO_ACCESS is the lowest possible access level meaning anyone can join|NO_ACCESS|
|chat-whitelist|Toggles whether to enable whitelisted chat. If this is set to false, chat will be unfiltered|false|
|custom-whitelist|A list of words to use for a custom whitelist.|
|chat-whitelist-mode|Determines which whitelists to use. 0 = Toontown Offline Whitelist Only, 1 = Custom Whitelist only, 2 = Both|0|
|ban-manager|Toggle which ban methods are enabled. Use 1 to enable, 0 to disable. The modes are as follows: [HWID, UUID, IP]|[1,1,0]|
|district-name|The name of the Mini-Server|Toon Valley|
|district-description|The description of the Mini-Server|A Toontown Offline Mini-Server|
|district-limit|Maximum players allowed on a Mini-Server at once. Maximum 16|16
|district-public|Determines whether your Mini-Server will appear on the [public Mini-Server list][mslist]|false|
|district-public-port|This is currently unused, redefining will have no effect|7198|
|district-icon-url|Specifies the URL where the Mini-Server icon can be found|https://toontownoffline.net/images/offline-icon.png|
|magic-word-logging|If enabled, all magic words ran will be logged to the logs folder|false|
|legit-mode|Toggles playing in Legit mode - this will disable many cheats and creative features|false|
|nerfs-mode|Nerfs many aspects of the gameplay to better suit a solo experience|false|
|exp-multiplier|Multiplies gag experience rewards|1.0|
|exp-cap|Determines the maximum amount of gag experience that can be gathered in a single battle or cog building|
|merit-multiplier|Multiplies merit rewards|1.0|
|doodle-multiplier|Multiplies Doodle training points|1.0
|default-max-toon|If enabled, all Toons will be set to end-game stats, such as 137 laff, all unlocks, and all gag tracks|false
|default-zone|Determines where newly created Toons will spawn|ttc|
|prop-generator|Toggles Prop Generator features|true|
|classic-fishing|Toggles whether the classic fishing docks should be spawned alongside normal fishing docks|true|
|easter-eggs|Toggles whether certain easter eggs should be enabled|true|
|disney-characters|Toggles whether Disney characters should walk around playgrounds|true|
|jukebox|Toggles whether a jukebox should be spawned in Toontown Central and the Toontown Outskirts|false|
|building-helpers|document this|true|
|outskirts-theme|Determines which neighborhood the Toontown Outskirts should be themed like|tt|
|race-game-easter-egg|Toggles an easter egg that can occur when playing the Race trolley game|true|
|racing-pro-racer|Toggles the unused "Pro Racer" mode for Goofy's Speedway racing.|false|
|send-extra-data|Enables sending of some unique but unnecessary data, such as the wheel rotation in racing, or the head rotation when in the a Kart in first-person. It may be optimal to disable on populated servers running on low end hardware, but currently this has a negligable effect.|true|
|server-timezone|Sets the timezone the server is set to. This will also set the in-game "Toontown Time".|US/Pacific|
|safezone-activities|Toggles certain activities that are unique to each playground, currently only includes the Toon statues in Toontown Central.|false|
|cog-count-multiplier|Multiplies the amount of cogs that will spawn in each area.|1.0|
|classic-animated-prop-faceoff|When this is enabled, the camera will spend more time looking at an animated street prop at the beginning of a battle, disabling this will shorten the time|false|
|playground-passive-healing-amount|Controls how much Laff is given through passive regeneration while in a playground|1|

[mslist]: https://toontownoffline.net/servers
[ttoff]: https://toontownoffline.net/
