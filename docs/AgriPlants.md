AgriCraft 2.0.0 introduces an exciting new feature: **JSON Custom Plants**!

JSON Custom Plants (i.e. AgriPlants) allow for total control of your agricultural experience, and even work in multiplayer environments!

This page will serve as a guide to using this awesome new feature of AgriCraft!

## Note
The JSON file may be located in any folder under the `config\agricraft\json\default` directory. Furthermore, the file must end in with `_plant.json` so that for a plant like wheat, the file name would be `wheat_plant.json`. This requirement is made so that the JSON file loader can differentiate between the different JSON file types.

## Structure
````
{
  "enabled": true, # Determines if the plant should be loaded or not.
  "path": "", # An internal field used for the transmission of JSON definitions.
  "id": "", # The unique string id for the plant.
  "plant_name": "", # The name of the plant. This does not need to be unique.
  "seed_name": "", # The name of the auto-generated seed for the plant. This will not be used if a valid seed item is defined.
  "seed_items": [ # An array containing the seed items that map to this plant.
    {
      "item": "minecraft:wheat_seeds",
      "meta": 0,
      "tags": "",
      "ignoreMeta": false,
      "ignoreTags": [
        "*"
      ],
      "useOreDict": false
    }
  ],
  "description": {
    "translations": {}, # An array containing locale:translation entries.
    "default": "" # The default description of the plant.
  },
  "growth_chance": 1.0, # The chance the plant has of growing on a random tick [range: 0.0-1.0].
  "bonemeal": true, # Determines if the plant accepts fertilizer to accelerate its growth.
  "tier": 1, # The tier of the plant. A legacy value.
  "weedable": false, # Determines if the plant acts like a weed and cannot be harvested normally.
  "aggressive": false, # Determines if the plant should try to overtake neighboring crops.
  "spread_chance": 0.1, # Determines the chance the plant has of attempting to move to a neighboring crop [range: 0.0-1.0].
  "spawn_chance": 0.0, # Determines the chance the plant has of randomly spawning in an unoccupied crop [range: 0.0-1.0].
  "products": {
    "products": [ # A list containing the possible products of the plant.
      {
        "min": 1,
        "max": 3,
        "chance": 0.95,
        "required": true,
        "item": "minecraft:wheat",
        "meta": 0,
        "tags": "",
        "ignoreMeta": false,
        "ignoreTags": [],
        "useOreDict": false
      }
    ]
  },
  "requirement": {
    "min_light": 10, # The min integer light value that the plant can grow in [min: 0].
    "max_light": 16, # The max integer light value that the plant can grow in [max: 16].
    "soils": [], # Array containing string ids for AgriSoils that are considered valid for this plant.
    "conditions": [ # Array containing all the growth requirement conditions to be met.
      {
        "amount": 1,  # The amount required in the given range.
        "min_x": 0,   # The bounding box, relative to the crop at 0, 0, 0 in which the block(s) are to be placed.
        "min_y": -2,  # In this case we specify the box {(0, -2, 0), (0, -2, 0)}, which is the single block directly
        "min_z": 0,   # below the soil block. Notice that the upper bound is inclusive, so that to specify a
        "max_x": 0,   # single block we use the same point twice, not the upper left and lower right points.
        "max_y": -2,
        "max_z": 0, 
        "item": "minecraft:gold_ore", # This part specifies information about the block required.
        "meta": 0, # This is a *direct* extension of an AgriStack meaning that it has all the same fields as
        "tags": "", # would be found on say the seed_items field.
        "ignoreMeta": true,
        "ignoreTags": [],
        "useOreDict": true
      }
    ]
  },
  "texture": {
    "render_type": "", # Can be either "cross", "hash", or "stem". This determines the method used to render the plant.
    "seed_texture": "", # A string representing the seed texure. This is used for the autogenerated seed items.
    "plant_textures": [] # An array of strings representing the plant textures.
  }
}
````