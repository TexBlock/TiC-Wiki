## Shared Keys  
All casting recipes have these keys:  
`type`: Must be either `"casting_basin"` or `"casting_table"`.  

Item casting and material casting share these keys:  
`switch_slots`: Boolean. Defaults to `false`. Set to `true` to force the recipe to put the recipe output into the cast slot.  
`cast`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Optional. Item required to be in the cast slot for the recipe.  
`cast_consumed`: Boolean. Defaults to `false`. Whether the recipe consumes the item in the cast slot.  

