Location: `.jar/data/tconstruct/recipes/smeltery/alloys/`
### Keys
`type`: Must be "tconstruct:alloy".  
`inputs`: List of [[FluidIngredients|Common-JSON-Value-Types#fluidingredient]]. The fluids that are being alloyed together. Must have at least two entries.  
`temperature`: Integer. Minimum temperature of the fuel to alloy.  
`result`: [[FluidStack|Common-JSON-Value-Types#fluidstack]]. The recipe's output.  

### Example
    {
      "type": "tconstruct:alloy",
      "inputs": [
        {
          "name": "tconstruct:molten_copper",
          "amount": 432
        },
        {
          "name": "tconstruct:molten_gold",
          "amount": 144
        }
      ],
      "result": {
        "fluid": "tconstruct:molten_rose_gold",
        "amount": 576
      },
      "temperature": 550
    }