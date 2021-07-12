AgriCraft Fertilizer JSON
==================================================

## Structure

```{json}
{
  "path": "vanilla/fertilizers/bone_meal_fertilizer.json", // An internal field used for the transmission of JSON definitions.
  "version": "1.16.4", // The version of the AgriCraft Fertilizer JSON.
  "json_documentation": "https://agridocs.readthedocs.io/en/master/agri_fertilizer/", // Documentation of the AgriCraft Fertilizer JSON
  "enabled": true, // Determines if the fertilizer should be loaded or not.
  "mods": [ // An array of mod ids. The fertilizer will be loaded only if all mods using those ids are present.
    "agricraft",
    "minecraft"
  ],
  "id": "vanilla:bone_meal_fertilizer", // The unique string id for the fertilizer.
  "lang_key": "item.minecraft.bone_meal",// The name of the fertilizer. Can be a lang key.
  "variants": [ // An array of objects representing all the items that this fertilizer represents.
    {           // This specific soil considers farmland and gravel to be the same soil.
      "type": "item",
      "object": "minecraft:bone_meal",
      "useTag": false,
      "data": "",
      "ignoredData": [
        "*"
      ]
    }
  ],
  "trigger_mutation": true, // Determine if the fertilizer trigger mutation in the crop.
  "trigger_weeds": true,    // Determine if the fertilizer trigger weed growth in the crop.
  "potency": 1, // Determine the potency of the fertilizer. Bigger values equals faster growth.
  "effect": { // Effects of the fertilizer on the plants.
    "reduce_growth": true, // Determine if the fertilizer can reduce the growth of negatively affected plants.
    "kill_plant": true,    // Determine if the fertilizer can kill negatively affected plants.
    "negatively_affected": { // The list of negatively affected plants by the fertilizer
      "blacklist": false, // Determine if the list should be considered as a whitelist or a blacklist
      "plant_list": [] // List of AgriPlant ids
    },
    "positively_affected":  {// The list of positively affected plants by the fertilizer
      "blacklist": false, // Determine if the list should be considered as a whitelist or a blacklist
      "plant_list": [] // List of AgriPlant ids
    },
    "particles": [ // An array of particles that are spawned in the world when the fertilizer is used on a plant.
      {
        "id": "minecraft:smoke", // The id of the particle
        "delta_x": 0.3, // How far from the center of the block the particle can spawn (X axis).
        "delta_y": 0.4, // How high from the center of the block the particle can spawn (Y axis).
        "delta_z": 0.3, // How far from the center of the block the particle can spawn (Z axis).
        "amount": 2, // The amount of particles
        "when": [ // Determine on which plants the particle should spawn
          "positive",
          "neutral",
          "negative"
        ]
      }
    ]
  }
}
```