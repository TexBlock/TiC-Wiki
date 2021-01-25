### Keys
`type`: Must be `"tconstruct:entity_melting"`.  
`entity`: [[EntityIngredient|Common-JSON-Value-Types#entityingredient]]. The entity to be melted.  
`result`: [[FluidStack|Common-JSON-Value-Types#fluidstack]]. The liquid added to the smeltery.  
`damage`: Integer. Optional, 2 by default. How much damage the entity takes per melting attempt in half-hearts (2 is one heart of damage).  

### Example
    {
      "type": "tconstruct:entity_melting",
      "entity": {
        "types": [
          "minecraft:enderman",
          "minecraft:endermite",
          "minecraft:ender_dragon"
        ]
      },
      "result": {
        "fluid": "tconstruct:molten_ender",
        "amount": 10
      },
      "damage": 2
    }