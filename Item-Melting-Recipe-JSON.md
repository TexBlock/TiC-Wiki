## Item Melting
Location: `.jar/data/tconstruct/recipes/smeltery/melting/`
### Keys
`type`: Must be `"tconstruct:melting"`.  
`ingredient`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Item to be melted.  
`result`: [[FluidStack|Common-JSON-Value-Types#fluidstack]]. Output fluid from the recipe.  
`temperature`: Integer. Minimum temperature of the fuel to melt the item.  
`time`: Time to melt the item. In [[ticks|Common-JSON-Value-Types#tick]].  

### Example
    {
      "type": "tconstruct:melting",
      "ingredient": {
        "tag": "forge:ingots/copper"
      },
      "result": {
        "fluid": "tconstruct:molten_copper",
        "amount": 144
      },
      "temperature": 500,
      "time": 50
    }

## Ore Melting
Location: `.jar/data/tconstruct/recipes/melting/`
An extension of item melting. Uses the same keys, but boosts the recipe's output based on the smeltery.

### Keys
`type`: Must be `"tconstruct:ore_melting"`.  

### Example
    {
      "type": "tconstruct:ore_melting",
      "ingredient": {
        "tag": "forge:ores/cobalt"
      },
      "result": {
        "fluid": "tconstruct:molten_cobalt",
        "amount": 144
      },
      "temperature": 1300,
      "time": 112
    }

## Material Melting
Location: `.jar/data/tconstruct/recipes/melting/parts/`
### Keys
`type`: Must be `"tconstruct:material_melting"`.  
`item`: [[IMaterialItem|Common-JSON-Value-Types#imaterialitem]]. Tool part to melt.  
`amount`: Integer. The amount of fluid to output.

### Example
    {
      "type": "tconstruct:material_melting",
      "item": "tconstruct:kama_head",
      "amount": 288
    }