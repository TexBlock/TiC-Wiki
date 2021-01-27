## Shared Keys
Item casting and material casting share these keys:  
`switch_slots`: Boolean. Defaults to `false`. Set to `true` to force the recipe to put the recipe output into the cast slot.  
`cast`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Optional. Item required to be in the cast slot for the recipe.  
`cast_consumed`: Boolean. Defaults to `false`. Whether the recipe consumes the item in the cast slot.  

## Item Casting
Location: `.jar/data/tconstruct/recipes/casting/`
### Keys
`type`: Must be either `"tconstruct:casting_basin"` or `"tconstruct:casting_table"`.  
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

## Material Casting
Location: `.jar/data/tconstruct/recipes/casting/parts/`
### Keys
`type`: Must be either `"tconstruct:basin_casting_material"` or `"tconstruct:table_casting_material"`.  
`fluid_amount`: Integer. The amount of fluid required. In millibuckets.  
`result`: [[IMaterialItem|Common-JSON-Value-Types#imaterialitem]]. Output part type.  
### Example
    {
      "type": "tconstruct:table_casting_material",
      "cast": {
        "item": "tconstruct:pickaxe_head_cast"
      },
      "fluid_amount": 288,
      "result": "tconstruct:pickaxe_head"
    }

## Composite Casting
### Keys
`type`: Unknown at the time. Presumably `"tconstruct:basin_composite"` or `"tconstruct:table_composite"`.  
`input`: [[MaterialId|Common-JSON-Value-Types#materialid]]. The material of the input tool part.  
`fluid`: [[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]. The fluid required to cast the item.  
`result`: [[MaterialId|Common-JSON-Value-Types#materialid]]. The material of the output tool part.  
`temperature`: Integer. Used to calculate casting time based on part size.  
### Example
    {
      "type": "tconstruct:table_composite",
      "input": "tconstruct:bone",
      "fluid": {
        "name": "tconstruct:fruit_juice",
        "amount": 65536
      },
      "result": "tconstruct:bone_hurting_material",
      "temperature": 1666
    }

## Container Filling
Location: `.jar/data/tconstruct/recipes/casting/filling/`
### Keys
`type`: Must be either `"tconstruct:basin_filling"` or `"tconstruct:table_filling"`.  
`fluid_amount`: Integer. The amount of fluid required. In millibuckets.  
`container`: [[IFluidHandlerItem|Common-JSON-Value-Types#ifluidhandleritem]]. The container to be filled.  
### Example
    {
      "type": "tconstruct:table_filling",
      "fluid_amount": 1000,
      "container": "minecraft:bucket"
    }

