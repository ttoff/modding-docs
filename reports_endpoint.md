# Toontown Realms Reports Endpoint Documentation
Toontown Realms allows Realm (server) hosters to specify a custom api endpoint in which to submit player reports by adding it to their [server.json][serverjson] file in the `reports-endpoint` field (an authorization header is also highly recommended)

Your POST api endpoint must accept the following fields

|Field Name|Type|Description|
|--|--|--|
|reporterId|unsigned long|The ToonID of the user who sent the report|
|reporterName|string|The Toon name of the user who sent the report|
|timestamp|string|The time the report was sent|
|category|string|The [report category](#report-categories)|
|reportDescription|string|A description written by the reporter to add detail to the report|
|reportedId|unsigned long|The ToonID of the user who is being reported|
|reporterName|string|The Toon name of the user who is being reported

## Report Categories
|String|Description as appears in-game|
|-|-|
|MODERATION_FOUL_LANGUAGE|Foul Language
|MODERATION_PERSONAL_INFO|Sharing/Requesting Personal Info
|MODERATION_RUDE_BEHAVIOR|Rude or Mean Behavior|
|MODERATION_BAD_NAME|Bad or Offensive Name|
|MODERATION_HACKING|Hacking|

[serverjson]: https://github.com/ttoff/modding-docs/blob/master/server_conf.md
