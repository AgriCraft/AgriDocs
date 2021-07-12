AgriCraft Soil JSON
==================================================

## Structure

```{json}
{
  "path": "vanilla/soils/farmland_soil.json", // An internal field used for the transmission of JSON definitions.
  "version": "1.16.4", // The version of the AgriCraft Soil JSON.
  "json_documentation": "https://agridocs.readthedocs.io/en/master/agri_soil/", // Documentation of the AgriCraft Soil JSON.
  "enabled": true, // Determines if the soil should be loaded or not.
  "mods": [
    "agricraft",
    "minecraft"
  ],
  "id": "farmland_soil", // The unique string id for the soil.
  "lang_key": "agricraft.soil.farmland.name", // The user-readable name of the soil. This does not need to be unique. Can be a lang key.
  "varients": [ // An array of AgriStacks representing all the blocks that this soil represents.
    {           // This specific soil considers farmland and gravel to be the same soil.
      "type": "block",
      "object": "minecraft:farmland",
      "useTag": false,
      "data": "",
      "ignoredData": [
        "*"
      ]
    }
  ],
  "humidity": "wet",
  "acidity": "slightly_acidic",
  "nutrients": "high",
  "growth_modifier": 1.0
}
```

## Soil condition values

### Humidity

|Value|Name|Synonyms|
|:---:|:---:|:---:|
|0|`arid`||
|1|`dry`||
|2|`damp`|`moist`|
|3|`wet`|`standard` `default`|
|4|`watery`||
|5|`flooded`||

### Acidity

|Value|Name|Synonyms|
|:---:|:---:|:---:|
|0|`highly_acidic`|`0` `1` `2` `highly-acidic` `highly acidic` `very_acidic` `very-acidic` `very acidic`|
|1|`acidic`|`3` `4` `5`|
|2|`slightly_acidic`|`6` `slightly-acidic` `slightly acidic` `standard` `default`|
|3|`neutral`|`7`|
|4|`slightly_alkaline`|`8` `slightly-alkaline` `slightly alkaline`|
|5|`alkaline`|`9` `10` `11`|
|6|`highly_alkaline`|`12` `13` `14` `highly-alkaline` `highly alkaline` `very_alkaline` `very-alkaline` `very alkaline`|

### Nutrients

|Value|Name|Synonyms|
|:---:|:---:|:---:|
|0|`none`|`zero` `empty`|
|1|`very_low`|`scare` `poor`|
|2|`low`||
|3|`medium`|`normal` `average`|
|4|`high`|`standard` `default`|
|5|`very_high`|`rich`|

## How the soil conditions are used :

The condition is met if the soil value is in the range :
`conditionValue ± (tolerance_factor * plant_strength)`

### Exemple for humidity

Assuming the plant has a strength of 10 and has this condition in the json :
```{json}
{
  "soil_humidity": {
    "condition": "damp",
    "type": "equal",
    "tolerance_factor": 0.2
  }
}
```

`damp` has a value of 2. So : 2 ± (0.2 * 10) = [0, 4].
That means the soil's humidity has to be in the range [0, 4].

Note : If the type was `equal_or_higher` the range would be [0, +inf]

## How to calculate the tolerance factor :

First we have to set the soil the plant need, and at which strength the plant can be placed in farmland.
Let's say we want our plant to pe placed on podzol, and the strength for farmland 7.

The calcul is : `f = abs(ceil((soil_humidity - farmland_humidity) / strength)))`. More literally f equals the absolute value of the rounded up value of (soil_humidity - farmland_humidity) / strength.

In our exemple, `f = abs(ceil((2 - 3) / 7))) = abs(ceil(-0.1428))) = abs(-0.15)) = 0.15`
The tolerance factor is thus 0.15.
