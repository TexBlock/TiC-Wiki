This page details the NBT structure of tools. In general addons should use [our utilities](https://github.com/SlimeKnights/TinkersConstruct/tree/1.16/src/main/java/slimeknights/tconstruct/library/tools/nbt) for interacting with tool NBT, but this page can be useful for mods adding compatibility that do not depend on our library.

## Tool Stack

This section describes the NBT of a normal tool, starting from the stack's root NBT compound.

* `Damage` (integer): Vanilla key determining the current damage on the tool
* `tic_broken` (boolean): If true, the tool is broken and is currently unusable
* `tic_materials` (list):
* `tic_upgrades` (list): List of modifiers added to the tool via recipes. Entries in the list should be unique.
    * *Entry* ([Modifier Entry](#modifier-entry)): A single modifier in the list
* `tic_modifiers` (list): Final computed list of modifiers, rebuilt on tool update. Contains everything in `tic_upgrades` plus traits from the tool and materials. Entries are unique and sorted by priority
    * *Entry* ([Modifier Entry](#modifier-entry)): A single modifier in the list
* `tic_persistent_data` ([Mod Data](#mod-data)): Extra tool data passed into modifiers. May be modified by both modifiers during interactions and recipes
* `tic_volatile_data` ([Mod Data](#mod-data)): Extra tool data rebuilt on tool update. Used to set shared properties, such as overslime capacity or extra modifier slots.
* `tic_stats` (compound): Final computed tool stats from materials and modifiers, rebuilt on tool update.
    * `durability` (integer): The maximum damage the tool can take before breaking
    * `attack` (float): The extra damage dealt by this tool
    * `attack_speed` (float): The speed at which this tool attacks, corresponds to the value passed into `ToolItem`
    * `mining_speed` (float): The speed at which this tool mines blocks, corresponds to the value from vanilla tool materials
    * `harvest_level` (integer): The harvest level for effective blocks, corresponds to vanilla harvest levels.
    * `reach` (integer): The maximum distance which this tool can interact, corresponds to Forge's reach attribute

## Modifier Entry

Represents a modifier with level on the tool

* *A modifier entry* (compound)
    * `name` (String): registry name of the modifier
    * `level` (integer): current level of the modifier, starting from 1

## Mod Data

Represents extra data shared between different modifiers and modifier recipes.

Note any of the three slot keys may be negative, as long as the sum of slots from both instances of mod data is non-negative.

* *Mod Data* (compound)
    * `upgrades` (integer): Number of unused upgrade slots on the tool.
    * `abilities` (integer): Number of unused ability slots on the tool
    * `traits` (integer): Number of unused trait slots on the tool
    * *Additional keys* (any): Namespaced keys representing additional modifier data
        * Example: `tconstruct:overslime` (integer) represents the current overslime on a tool

