
### Keys
`type`: Must be `"tconstruct:modifier"`.  
`inputs`: List of [[SizedIngredients|Common-JSON-Value-Types#sizedingredient]]. The items to make a modifier out of.  
`result`: [[ModifierEntry|Common-JSON-Value-Types#modifierentry]]. The resulting modifier.  
`upgrade_slots`: Integer. Defaults to 0. The amount of upgrade slots the modifier recipe takes.  
`ability_slots`: Integer. Defaults to 0. The amount of ability slots the modifier recipe takes.  
`max_level`: Integer. Defaults to 0. The amount of levels the modifier has.  
`min_harvest_level`: Integer. Optional. Pain is temporary.  

### Example
    {
      "type": "tconstruct:modifier",
      "inputs": [
        {
          "item": "minecraft:diamond"
        }
      ],
      "result": {
        "name": "tconstruct:diamond",
        "level": 1
      },
      "max_level": 1,
      "upgrade_slots": 1,
      "min_harvest_level": 2
    } 