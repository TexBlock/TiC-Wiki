## Shared Keys  
All casting recipes have these keys:  
`type`: Must be either `"tconstruct:casting_basin"` or `"tconstruct:casting_table"`.  

Item casting and material casting share these keys:  
`switch_slots`: Boolean. Defaults to `false`. Set to `true` to force the recipe to put the recipe output into the cast slot.  
`cast`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Optional. Item required to be in the cast slot for the recipe.  
`cast_consumed`: Boolean. Defaults to `false`. Whether the recipe consumes the item in the cast slot.  

## Item Casting
### Keys
`fluid`: [[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]. The fluid required to cast the item.  
`result`: [[ItemOutput|Common-JSON-Value-Types#itemoutput]]. Casting result.  
`cooling_time`: Integer. Time to finish the recipe. In [[ticks|Common-JSON-Value-Types#tick]].  
### Example
    {
      "type": "tconstruct:casting_basin",
      "fluid": {
        "name": "tconstruct:molten_cobalt",
        "amount": 1296
      },
      "result": "tconstruct:cobalt_block",
      "cooling_time": 225
    }

