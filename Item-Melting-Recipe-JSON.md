## Item Melting
Location: `.jar/data/tconstruct/recipes/smeltery/melting/`
### Keys
`type`: Must be `"tconstruct:melting"`.  
`ingredient`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Item to be melted.  
`result`: [[FluidStack|Common-JSON-Value-Types#fluidstack]]. Output fluid from the recipe.  
`byproducts`: List of [[FluidStacks|Common-JSON-Value-Types#fluidstack]]. Foundry byproducts for the recipe.  
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

## Damageable Item Melting
Location: `.jar/data/tconstruct/recipes/smeltery/melting/`  
Same as normal item melting, but liquid output scales with item durability damage.  

### Keys
`type`: Must be `"tconstruct:damagable_melting"`.  

### Example
    {
      "type": "tconstruct:damagable_melting",
      "ingredient": {
        "item": "minecraft:iron_chestplate"
      },
      "result": {
        "fluid": "tconstruct:molten_iron",
        "amount": 1152
      },
      "temperature": 800,
      "time": 170
    } 

## Ore Melting
Location: `.jar/data/tconstruct/recipes/smeltery/melting/`
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
Location: `.jar/data/tconstruct/recipes/tools/parts/melting/`
### Keys
`type`: Must be `"tconstruct:material_melting"`.  
`item`: [[IMaterialItem|Common-JSON-Value-Types#imaterialitem]]. Tool part to melt.  
`item_cost`: Integer. The amount of baseline "ingots" to output.

### Example
    {
      "type": "tconstruct:material_melting",
      "item": "tconstruct:kama_head",
      "item_cost": 2
    }