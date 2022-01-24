These recipes define adding modifiers to tools using the tinker station.

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [Simple Modifier Recipe](#simple-modifiers)
- [Incremental Modifier](#incremental-modifier)
- [Overslime](#overslime)
- [Creative Slot](#creative-slot)
</td>
</table>

## Simple Modifiers

Standard way to add a modifier to a tool.

### Keys
* `type` (string): Must be `tconstruct:modifier` 
* `inputs` (array): List of [[SizedIngredients|Common-JSON-Value-Types#sizedingredient]] required to craft this modifier. If more than 3 are provided, the modifier requires the tinkers' anvil.
* `result` ([[ModifierEntry|Common-JSON-Value-Types#modifierentry]]): Modifier applied by the recipe.  
* `tools` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Tools the modifier is applicable on. Most often a tag.
* `requirements` ([[ModifierMatch|Common-JSON-Value-Types#modifiermatch]]): Optional list of modifiers that must be on the tool for this modifier to apply.
* `slots` ([[SlotCount|Common-JSON-Value-Types#slotcount]]): Contains information about the slots required for a modifier. If undefined or empty, the modifier will be "slotless", meaning no modifier slots are required.
* `max_level` (integer): Maximum level of the modifier that can be applied through this recipe. If unset, the modifier has no limit.

### Examples

Defines a recipe for adding the draconic modifier using a dragon head. The modifier can be applied to any modifiable tool and at most 1 level can be applied.

```json
{
  "type": "tconstruct:modifier",
  "inputs": [{ "item": "minecraft:dragon_head" }],
  "tools": { "tag": "tconstruct:modifiable" },
  "result": {
    "name": "tconstruct:draconic",
    "level": 1
  },
  "max_level": 1
}
```

Defines a recipe for adding a second level of the expanded modifier. It only applies to items in the AOE tag, requires a single level to already be applied, and consumes 1 ability slot. At most 2 levels are allowed, effectively meaning this recipe can be applied once.

```json
{
  "type": "tconstruct:modifier",
  "inputs": [{ "item": "tconstruct:ender_expander" }],
  "tools": { "tag": "tconstruct:modifiable/aoe" },
  "requirements": {
    "name": "tconstruct:expanded",
    "level": 1,
    "error": "recipe.tconstruct.modifier.ender_expander_requirements"
  },
  "result": { "name": "tconstruct:expanded", "level": 1 },
  "max_level": 2,
  "slots": { "abilities": 1 }
}
```

More examples can be found in `TConstruct.jar/data/tconstruct/recipes/tools/modifiers/`

## Incremental Modifiers

Modifier recipe that can be applied incrementally, meaning a partial amount is applied granting a partial effect. For modifiers that do not implement incremental behavior, this will not function as expected.

### Keys

* `type` (string): Must be `tconstruct:incremental_modifier`.  
* `input` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): The item added to make the modifier. 
* `neededPerLevel` (integer): Number of `input` needed to craft this modifier. If less than this value is applied, the tool is given a partial modifier.
* `amountPerInput` (integer): "value" of each input towards the number needed per level.
* `leftover` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]). If the amount needed to top off the modifier is smaller than the amount given per input, the remainder is given back as a stack of this item.  
* `result` ([[ModifierEntry|Common-JSON-Value-Types#modifierentry]]): Modifier applied by the recipe.  
* `tools` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Tools the modifier is applicable on. Most often a tag.
* `requirements` ([[ModifierMatch|Common-JSON-Value-Types#modifiermatch]]): Optional list of modifiers that must be on the tool for this modifier to apply.
* `slots` ([[SlotCount|Common-JSON-Value-Types#slotcount]]): Contains information about the slots required for a modifier. If undefined or empty, the modifier will be "slotless", meaning no modifier slots are required.
* `max_level` (integer): Maximum level of the modifier that can be applied through this recipe. If unset, the modifier has no limit.

### Example

Allows applying haste using redstone dust. 45 redstone dust is needed for the full recipe, but a partial amount can be added.

```json
{
  "type": "tconstruct:incremental_modifier",
  "input": { "tag": "forge:dusts/redstone" },
  "amount_per_item": 1,
  "needed_per_level": 45,
  "tools": [{ "tag": "tconstruct:modifiable/melee_or_harvest" }],
  "slots": { "upgrades": 1 },
  "result": { "name": "tconstruct:haste", "level": 1 },
  "max_level": 5
}
```

Allows applying haste using redstone blocks. 5 redstone blocks are needed for the full recipe, but each block separately adds 9 towards the total. Note applying one block means now only 36 redstone dust from the previous recipe is needed.

```json
{
  "type": "tconstruct:incremental_modifier",
  "input": { "tag": "forge:storage_blocks/redstone" },
  "amount_per_item": 9,
  "needed_per_level": 45,
  "leftover": "minecraft:redstone",
  "tools": [{ "tag": "tconstruct:modifiable/melee_or_harvest" }],
  "slots": { "upgrades": 1 },
  "result": { "name": "tconstruct:haste", "level": 1 },
  "max_level": 5
}
```

More examples can be found in `TConstruct.jar/data/tconstruct/recipes/tools/modifiers/`

## Overslime

Recipe to apply overslime to a tool or refill the overslime amount.

### Keys

* `type` (string): Always `tconstruct:overslime_modifier`
* `ingredient` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Item consumed to restore overslime
* `restore_amount` (integer): Amount of overslime restored by this recipe.

### Examples

```json
{
  "type": "tconstruct:overslime_modifier",
  "ingredient": {
    "item": "tconstruct:ender_slime_crystal"
  },
  "restore_amount": 200
}
```

More examples can be found in `TConstruct.jar/data/tconstruct/recipes/tools/modifiers/slotless/overslime`

## Creative Slot

This recipe allows applying the creative slot modifiers to boost a tool's slot count.

It simply has one key: `type`, which is set to `tconstruct:creative_slot_modifier`. The recipe is defined in `TConstruct.jar/data/tconstruct/recipes/tools/modifiers/slotless/creative_slot`
