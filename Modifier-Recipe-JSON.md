Location: `.jar/data/tconstruct/recipes/tools/modifiers/upgrade/`
### Shared Keys
Simple and incremental modifiers share these keys:
`result`: [[ModifierEntry|Common-JSON-Value-Types#modifierentry]]. The resulting modifier.  
`tools`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. The tool that the modifier requires. Usually a tag.  
`requirements`: [[ModifierMatch|Common-JSON-Value-Types#modifiermatch]]. Optional. Modifiers required on the tool to apply the recipe.  
`slots`: [[SlotCount|Common-JSON-Value-Types#slotcount]]. Contains information about the slots required for a modifier. If undefined or empty, the modifier will be "slotless", meaning no modifier slots are required.
`max_level`: Integer. Defaults to 0. The maximum levels of the modifier that can be applied through this recipe. 0 means no limit.

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
      "slots": { "abilities": 1 }
    }

## Incremental Modifier Recipe
The resulting modifier *must* extend IncrementalModifier for proper behavior.
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
      "slots": { "upgrades": 1 }
    }