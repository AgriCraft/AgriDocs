## Structure
```{json}
{
  "enabled": true, # Determines if the soil should be loaded or not.
  "path": "", # An internal field used for the transmission of JSON definitions.
  "id": "", # The unique string id for the plant.
  "name": "", # The user-readable name of the soil. This does not need to be unique.
  "varients": [ # An array of AgriStacks representing all the blocks that this soil represents.
    {           # This specific soil considers farmland and gravel to be the same soil.
      "item": "minecraft:farmland",
      "meta": 0,
      "tags": "",
      "ignoreMeta": true,
      "ignoreTags": [
        "*"
      ],
      "useOreDict": true
    },
    {
      "item": "minecraft:gravel",
      "meta": 0,
      "tags": "",
      "ignoreMeta": true,
      "ignoreTags": [
        "*"
      ],
      "useOreDict": true
    }
  ]
}

```