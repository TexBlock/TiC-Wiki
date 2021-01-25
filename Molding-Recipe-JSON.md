### Keys
`type`: Must be either `"tconstruct:molding_basin"` or `"tconstruct:molding_table"`.  
`material`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Item placed into the casting implement first.  
`pattern`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Optional. Item placed into the casting implement second.  
`pattern_consumed`: Boolean. Defaults to `false`. Whether the pattern is consumed during the molding operation.  
`result`: [[ItemStack|Common-JSON-Value-Types#itemstack]]. The operation result.  

### Example
    {
      "type": "tconstruct:molding_table",
      "material": {
        "tag": "tconstruct:casts/sand"
      },
      "result": "tconstruct:blank_sand_cast"
    }