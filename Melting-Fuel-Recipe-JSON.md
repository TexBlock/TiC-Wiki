Location: `.jar/data/tconstruct/recipes/melting/fuel/`
### Keys
`type`: Must be `"tconstruct:melting_fuel"`.  
`fluid`: [[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]. The fuel fluid.  
`temperature`: Integer. Affects the items the fuel can melt, as well as the melting speed. A straight multiplier for melting speed, with vanilla 1000 being 1.0x, 1500 being 1.5x, 800 0.8x and so on.  
`duration`: Integer. For how long the fuel lasts in the smeltery. The smeltery consumes 1 `duration` every 4 [[ticks|Common-JSON-Value-Types#tick]] base. Every `duration` is converted from `fluid`'s `amount` from the smeltery's tank.  

### Example
    {
      "type": "tconstruct:melting_fuel",
      "fluid": {
        "name": "minecraft:lava",
        "amount": 50
      },
      "duration": 100,
      "temperature": 1000
    }