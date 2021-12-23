Salvage is the method for removing modifiers from tools and restoring their slots.

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [Modifier Removal](#modifier-removal)
- [Salvage Recipe](#salvage-recipe)
- [Incremental Salvage Recipe](#incremental-salvage-recipe)
</td>
</table>

## Modifier Removal

Base recipe enabling modifier removal in the tinker station. In the future this will likely be moved to another table.

### Keys

* `type` (string): Always `tconstruct:remove_modifier`
* `ingredient` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Ingredient required to remove a modifier
* `container` ([[ItemStack|Common-JSON-Value-Types#itemoutput]]): Result returned from the consumed item.

### Example

Allows removing a modifier using a wet sponge in the tinker station, leaving a sponge behind.

```json
{
  "type": "tconstruct:remove_modifier",
  "ingredient": {
    "item": "minecraft:wet_sponge"
  },
  "container": "minecraft:sponge"
}
```

The modifier removal recipe can be found at `TConstruct.jar/data/tconstruct/recipes/tools/modifiers/slotless/remove_modifier`

## Salvage Recipe

Defines returns from a modifier after removing it, including slots and items. If no salvage recipes apply to the given tool and modifier, no salvage is given.

### Keys

* `type` (string): Always `tconstruct:modifier_salvage`
* `tools` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Tools this salvage recipe is applicalbe to
* `modifier` ([[Modifier|Common-JSON-Value-Types#resourcelocation]]): Modifier being removed
* `min_level` (integer): Minimum level of the modifier for this salvage to apply
* `max_level` (integer): Maximum level of the modifier for this salvage to apply
* `slots` ([[SlotCount|Common-JSON-Value-Types#slotcount]]): Slots restored from this recipe
* `salvage` (array): List of [[RandomItems|Common-JSON-Value-Types#randomitem]] to return in this salvage. If unspecified, no items are returned.

### Examples

Defines removing the fireprimer modifier from a tool. The tool regains 1 upgrade slot, and between 1 and 4 flint are gained, along with a 35% chance of gaining 1 netherite scrap. The salvage is only applicable if the tool has between 2 and 4 levels of fireprimer.

```json
{
  "type": "tconstruct:modifier_salvage",
  "tools": { "item": "tconstruct:flint_and_bronze" },
  "slots": { "upgrades": 1 },
  "modifier": "tconstruct:fireprimer",
  "min_level": 2,
  "min_level": 4,
  "salvage": [
    { "item": "minecraft:flint", "min": 1, "max": 4 },
    { "item": "minecraft:netherite_scrap", "chance": 0.35 }
  ]
}
```

More examples can be found in `TConstruct.jar/data/tconstruct/recipes/tool/modifiers/salvage/`

## Incremental Salvage Recipe

For incremental modifiers, allows returning less salvage if there is not a full level of the modifier.

### Keys

* `type` (string): Always `tconstruct:incremental_modifier_salvage`
* `tools` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Tools this salvage recipe is applicalbe to
* `modifier` ([[Modifier|Common-JSON-Value-Types#resourcelocation]]): Modifier being removed
* `min_level` (integer): Minimum level of the modifier for this salvage to apply
* `max_level` (integer): Maximum level of the modifier for this salvage to apply
* `slots` ([[SlotCount|Common-JSON-Value-Types#slotcount]]): Slots restored from this recipe
* `salvage` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]): Item returned for salvage. In addition to normal ItemOutput keys, includes one extra key:
    * `full` (boolean): if true, returns 1 salvage item per item on the tool. If false, returns between 0 and the number applied.

### Examples

Recipe allows removing haste, restoring 1 upgrade slot to the tool and restoring between 0 and the redstone on the tool.

```json
{
  "type": "tconstruct:incremental_modifier_salvage",
  "tools": [{ "tag": "tconstruct:modifiable/melee_or_harvest" }],
  "slots": { "upgrades": 1 },
  "modifier": "tconstruct:haste",
  "min_level": 1,
  "salvage": { "item": "minecraft:redstone", "full": false }
}
```

More examples can be found in `TConstruct.jar/data/tconstruct/recipes/tool/modifiers/salvage/`