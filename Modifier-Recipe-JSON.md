
### Keys
`type`: Must be `"tconstruct:modifier"`.  
`inputs`: List of [[SizedIngredients|Common-JSON-Value-Types#sizedingredient]]. The items to make a modifier out of.  
`result`: [[ModifierEntry|Common-JSON-Value-Types#modifierentry]]. The resulting modifier.  
`tools`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Optional. The tool that the modifier requires.  
`requirements`: [[ModifierMatch|Common-JSON-Value-Types#modifiermatch]]. Optional. Modifiers required on the tool to apply the recipe.  
`upgrade_slots`: Integer. Defaults to 0. The amount of upgrade slots the modifier recipe takes.  
`ability_slots`: Integer. Defaults to 0. The amount of ability slots the modifier recipe takes. A modifier recipe cannot use both upgrade and ability slots.  
`max_level`: Integer. Defaults to 0. The amount of levels the modifier has.  

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