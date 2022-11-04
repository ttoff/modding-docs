# NPC Toons - Toontown Offline Modding Documentation

Toontown Offline features the ability to add, or replace NPC toons.

## Important Information
* The default NPC toons file can be found in `phase_3/data/npctoons.json`, this should NEVER be overwritten by resource packs - any changes should be made to `config/npctoons.json`. This file does not exist by default, so you will need to create one if you want to make changes.
* Make sure you follow proper JSON formatting. An example file is provided here.
* It is not possible to add new NPC positions, therefore zones should never go above their proper NPC count, excess NPCs in a zone will just default to xyz (0, 0, 0).

## Modifying NPC Toons
1. Create a new file called `npctoons.json` in the config folder in your Toontown Offline installation directory
2. The json file should first be formatted as following:
```json
{

}
```
*Inside the brackets is where you wlil add each new entry, separated by commas. Note that JSON is a very strict format, a stray comma will break the file. Do NOT include a comma after the final entry.
3. Add entry. The format of each NPC Toon will be explained later in the document.

`npctoons.json` is a dictionary of `Toon` elements, identified by their NPC ID

## Toon data type

| Field | Type | Description | Example |
|---|---|---|---|
|name|string|The Toon's Name|"Flippy"|
|zone_id|int or null|The zone ID in which the Toon resides. A Toon can be set to not appear in a zone if you set to null|2007|
|protected|boolean|Protected buildings will not be taken over by Cogs|false (or 0)|
|body|[`Body`](#body-data-type)|Defines the Toon's head, body, legs, and gender|See Below|
|clothes|[`Clothes`](#clothing-data-type)|Defines the Toon's clothing textures|See Below|
|colors|[`Colors`](#color-data-type)|Defines the Toon's body and clothing colors|See Below|
|accessories|[`Accessories`](#accessories)|Define's the Toon's accessories|See Below|
|type|string (see below for valid options)|Define's the Toon's type - Control's its function in game|"NPC_HQ"|

### Example:
```json
"20002": {
        "name": "HQ Harry",
        "zone_id": null,
        "protected": 1,
        "body": {...},
        "clothes": {...},
        "colors": {...},
        "accessories": {...},
        "type": "NPC_HQ"
    }
```

## Body data type
| Field | Type | Description | Example |
|---|---|---|---|
|head|string|Toon's species, head, and muzzle sizes|"dls"|
|torso|string|Toon's torso (Also controls whether wearing a skirt or shorts)|"ms"|
|legs|string|Toon's legs|"l"|
|gender|string ("m" or "f")|Controls whether the toon is a male or female|"f"|

### Example
```json
"body": {
        "head": "dll",
        "torso": "sd",
        "legs": "l",
        "gender": "f"
},
```
## Clothing data type
| Field | Type | Description | Example |
|---|---|---|---|
|shirt|int|Shirt texture ID|5|
|sleeves|int|Sleeves texture ID|4|
|bottoms|int|Bottoms texture ID|9|

### Example
```json

"clothes": {
    "shirt": 0,
    "sleeves": 0,
    "bottoms": 8
},
```

## Colors data type
*Hint: For clothing, 27 is white, or the default color of the texture - No tint
For gloves, 0 is white*
| Field | Type | Description | Example |
|---|---|---|---|
|head|int|Head color ID|8|
|torso|int|Torso color ID|8|
|gloves|int|Glove color ID|0|
|legs|int|Leg color ID|12|
|shirt|int|Shirt color ID|27|
|sleeves|int|Sleeves color ID|27|
|bottoms|int|Bottoms color ID|19|

### Example
```json
"colors": {
    "head": 21,
    "torso": 21,
    "gloves": 0,
    "legs": 21,
    "shirt": 5,
    "sleeves": 5,
    "bottoms": 21
},
```

## Accessories
| Field | Type | Description | Example |
|---|---|---|---|
|hat|List of 3 integers|This list defines the Hat Model, Texture ID, and Color ID for the Hat accessory|\[5,0,0\]
|glasses|List of 3 integers|This list defines the Glasses Model, Texture ID, and Color ID for the Glasses accessory|\[5,0,0\]
|backpack|List of 3 integers|This list defines the Backpack Model, Texture ID, and Color ID for the Glasses accessory|\[5,0,0\]
|shoes|List of 3 integers|This list defines the Shoe Model, Texture ID, and Color ID for the Glasses accessory|\[1,4,0\]

### Example
```json
"accessories":{
            "hat": [34,0,0],
            "glasses": [3,0,0],
            "backpack": [38,0,0],
            "shoes": [1,6,0]
}
```

## Example
The following example shows an NPC Toon override of Tutorial Tom and HQ Harry
`npctoons.json`
```json
{
"20000": {
        "name": "Tutorial Tom",
        "zone_id": null,
        "protected": 1,
        "body": {
            "head": "dll",
            "torso": "ms",
            "legs": "m",
            "gender": "m"
        },
        "clothes": {
            "shirt": 2,
            "sleeves": 2,
            "bottoms": 2
        },
        "colors": {
            "head": 7,
            "torso": 7,
            "gloves": 0,
            "legs": 7,
            "shirt": 6,
            "sleeves": 6,
            "bottoms": 16
        },
        "accessories": {
            "hat": [0,0,0],
            "glasses": [0,0,0],
            "backpack": [0,0,0],
            "shoes": [0,0,0]
        },
        "type": "NPC_REGULAR"
    },
    "20002": {
        "name": "HQ Harry",
        "zone_id": null,
        "protected": 1,
        "body": {
            "head": "dls",
            "torso": "ms",
            "legs": "m",
            "gender": "m"
        },
        "clothes": {
            "shirt": 0,
            "sleeves": 0,
            "bottoms": 0
        },
        "colors": {
            "head": 6,
            "torso": 6,
            "gloves": 0,
            "legs": 6,
            "shirt": 10,
            "sleeves": 10,
            "bottoms": 9
        },
        "accessories": {
            "hat": [0,0,0],
            "glasses": [0,0,0],
            "backpack": [0,0,0],
            "shoes": [0,0,0]
        },
        "type": "NPC_HQ"
    }
}
```
