Location: `.jar/data/tconstruct/recipes/tools/modifiers/upgrade/`
### Shared Keys
Simple and incremental modifiers share these keys:
`result`: [[ModifierEntry|Common-JSON-Value-Types#modifierentry]]. The resulting modifier.  
`tools`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. The tool that the modifier requires. Usually a tag.  
`requirements`: [[ModifierMatch|Common-JSON-Value-Types#modifiermatch]]. Optional. Modifiers required on the tool to apply the recipe.  
`upgrade_slots`: Integer. Defaults to 0. The amount of upgrade slots the modifier recipe takes.  
`ability_slots`: Integer. Defaults to 0. The amount of ability slots the modifier recipe takes. A modifier recipe cannot use both upgrade and ability slots.  
`max_level`: Integer. Defaults to 0. The amount of levels the modifier has.  

## Simple Modifier Recipe
### Keys
`type`: Must be `"tconstruct:modifier"`.  
`inputs`: List of [[SizedIngredients|Common-JSON-Value-Types#sizedingredient]]. The items to make a modifier out of.  

### Example
    {
      "type": "tconstruct:modifier",
      "inputs": [
        {
          "item": "tconstruct:ender_expander"
        }
      ],
      "tools": {
        "tag": "tconstruct:modifiable/aoe"
      },
      "requirements": {
        "name": "tconstruct:expanded",
        "level": 1,
        "error": "recipe.tconstruct.modifier.ender_expander_requirements"
      },
      "result": {
        "name": "tconstruct:expanded",
        "level": 1
      },
      "max_level": 2,
      "ability_slots": 1
    }

## Incremental Modifier Recipe
The resulting modifier *must* extend IncrementalModifier.
### Keys
`type`: Must be `"tconstruct:incremental_modifier"`.  
`input`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. The item added to make the modifier.  
`amountPerInput`: Integer. Defaults to 1. Must be positive. The amount the modifier is boosted by for one `input`.  
`neededPerLevel`: Integer. Must be bigger or equal to `amountPerInput`. The amount of boosts needed for a full modifier level.  
`leftover`: [[ItemStack|Common-JSON-Value-Types#itemstack]]. If the amount needed to top off the modifier is smaller than the amount given per input, the remainder is given back as a stack of this item.  

### Example
    {
      "type": "tconstruct:incremental_modifier",
      "input": {
        "tag": "forge:storage_blocks/quartz"
      },
      "amount_per_item": 4,
      "needed_per_level": 36,
      "leftover": "minecraft:quartz",
      "tools": {
        "tag": "tconstruct:modifiable/melee"
      },
      "result": {
        "name": "tconstruct:sharpness",
        "level": 1
      },
      "max_level": 5,
      "upgrade_slots": 1
    }