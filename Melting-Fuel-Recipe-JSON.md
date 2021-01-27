Location: `.jar/data/tconstruct/recipes/melting/fuel/`
### Keys
`type`: Must be `"tconstruct:melting_fuel"`.  
`fluid`: [[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]. The fuel fluid.  
`temperature`: Integer. Affects the items the fuel can melt, as well as the melting speed.  
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