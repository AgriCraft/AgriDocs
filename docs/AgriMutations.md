## Structure
```{json}
{
  "enabled": true, # Determines if the mutation should be loaded or not.
  "path": "",      # An internal field used for the transmission of JSON definitions.
  "chance": 0.5,   # The chance of the mutation occurring on any given random tick, a p-value in the range 0.0 to 1.0.
  "child": "cactus_plant",      # The unique id of the child AgriPlant.
  "parent1": "sugarcane_plant", # The unique id of the first  parent AgriPlant.
  "parent2": "potato_plant"     # The unique id of the second parent AgriPlant.
}
```