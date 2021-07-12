AgriCraft Weed JSON
==================================================

## Structure

```{json}
{
  "path": "vanilla/weeds/weed_weed.json", // An internal field used for the transmission of JSON definitions.
  "version": "1.16.4", // The version of the AgriCraft Weed JSON.
  "enabled": true, // Determines if the weed should be loaded or not.
  "mods": [ // An array of mod ids. The weed will be loaded only if all mods using those ids are present.
    "agricraft",
    "minecraft"
  ],
  "id": "agricraft:weed_weed", // The unique string id for the weed.
  "weed_lang_key": "agricraft.weed.weed.name", // The name of the weed. Can be a lang key.
  "desc_lang_key": "agricraft.weed.weed.desc", // The description of the weed. Can be a lang key.
  "stages": [ // An array containing the height of the weed for each growth stage.
    2,
    4,
    6,
    8,
    10,
    12,
    14,
    16
  ],
  "spawn_chance": 0.25, // The chance the weed has of spawning on a random tick [range: 0.0-1.0].
  "growth_chance": 0.9, // The chance the weed has of growing on a random tick [range: 0.0-1.0].
  "aggressive": true, // Determine if the weed reduce the growth stage of the plant.
  "lethal": true,     // Determine if the weed can kill the plant.
  "rake_drops": {
    "products": [] // A list containing the possible raking products of the weed.
  },
  "requirement": { // Determines the growth requirements of the weed. More information in AgriPlants as it's the same format.
    "soil_humidity": {
      "condition": "damp",
      "type": "equal",
      "tolerance_factor": 0.15
    },
    "soil_acidity": {
      "condition": "neutral",
      "type": "equal",
      "tolerance_factor": 0.2
    },
    "soil_nutrients": {
      "condition": "medium",
      "type": "equal_or_higher",
      "tolerance_factor": 0.1
    },
    "min_light": 10,
    "max_light": 16,
    "light_tolerance_factor": 0.5,
    "seasons": [
      "spring",
      "summer",
      "autumn",
      "winter"
    ],
    "conditions": [],
    "fluid": {
      "type": "fluid",
      "object": "minecraft:empty",
      "useTag": false,
      "data": "",
      "ignoredData": []
    }
  },
  "texture": { // This determines the method used to render the weed. More information in AgriPlants as it's the same format.
    "render_type": "rhombus",
    "plant_models": [],
    "plant_textures": [
      [
        "agricraft:block/weed_stage_0"
      ],
      [
        "agricraft:block/weed_stage_0"
      ],
      [
        "agricraft:block/weed_stage_1"
      ],
      [
        "agricraft:block/weed_stage_1"
      ],
      [
        "agricraft:block/weed_stage_2"
      ],
      [
        "agricraft:block/weed_stage_2"
      ],
      [
        "agricraft:block/weed_stage_2"
      ],
      [
        "agricraft:block/weed_stage_3"
      ]
    ]
  }
}

```