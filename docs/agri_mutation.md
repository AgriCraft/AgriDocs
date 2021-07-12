AgriCraft Mutation JSON
==================================================

## Structure
```{json}
{
  "path": "vanilla/mutations/cactus_mutation.json", // An internal field used for the transmission of JSON definitions.
  "version": "1.16.4", // The version of the AgriCraft Mutation JSON
  "json_documentation": "https://agridocs.readthedocs.io/en/master/agri_mutation/", // Documentation of the AgriCraft Mutation JSON
  "enabled": true, // Determines if the mutation should be loaded or not.
  "mods": [ // An array of mod ids. The plant will be loaded only if all mods using those ids are present.
    "agricraft",
    "minecraft"
  ],
  "chance": 0.5, // The chance of the mutation occurring on any given random tick, a p-value in the range 0.0 to 1.0.
  "child": "vanilla:cactus_plant",      // The unique id of the child AgriPlant.
  "parent1": "vanilla:sugarcane_plant", // The unique id of the first  parent AgriPlant.
  "parent2": "vanilla:potato_plant"     // The unique id of the second parent AgriPlant.
}
```
