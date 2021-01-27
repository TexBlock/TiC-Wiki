## Item Melting
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