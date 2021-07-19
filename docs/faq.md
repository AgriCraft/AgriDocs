Frequently Asked Questions
==================================================

## How do I prevent a plant from spawning? How do I disable it?

In the corresponding JSON file, change the `spawn_chance` or `enabled` settings. Note that if you delete the JSON file for a bundled plant, it will be regenerated with its default settings.

## How do I disable weeds?

Quick answer: Same like any other plant.

Longer answer: In `config/agricraft/json/SELECTSERVERHERE/vanilla/plants/weed_plant.json` set `"enabled": false`, or set `"spawn_chance": 0.0`.

Longest answer: As part of the transition to using customizable JSON files for all of the plants, weeds are now no longer special or different than other plants. What gives them that annoying nature is that they have a non-zero chance to spontaneously spawn, and because they're aggressive they have the ability to technically replace neighboring plants. Except that, by default they're too weak to do that really.

## Why won't some plant products stack with others?

Probably because one of those stacks have the AgriCraft plant stats on them, and so the NBT data doesn't agree. AgriCraft can use existing items as seeds, but it has to record extra information on there. The tooltip should show some of it, plus there's a config option to show a more in-depth tooltip. There's also a bug currently that makes leaves off an NBT tag seeds, and so those form a separate stack too.

## How do I use Fertilizers from other mods?

Create the corresponding fertilizer json. With some luck it's already present.

## Why can't I put the seed into the Seed Analyzer?

My first guess is that there isn't support for that plant or mod yet. Check the JSON folder for the server (default is for all of single player), then if there's a folder for the mod, and then if there's a file for that plant.

## How can I use the seed Analyzer ?

You need to shift + right click with the journal or seed in your hand. If the journal is in the analyzer and you analyze a seed, the page for the seed will show up in the journal.

## How can I use the seed bag ?

Hold the bag in your off hand, then right click with a seed in your main hand to put the seed in the bag, or with a empty hand to retrieve one seed.
You can shake the bag (shift + right click) to change the order of the seeds.
You can plant seeds directly from the bag with a right click from the main hand.
