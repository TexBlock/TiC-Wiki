## Ingredient
Vanilla recipe input. Can be either an item stack or a tag.

## FluidIngredient
A fluid recipe input.
### Keys
`name`: The fluid's full name.  
`tag`: Forge tag. Used when the recipe can have multiple possible inputs.  
`amount`: Integer. The fluid amount in millibuckets.  
### Examples
    "fluid": {
      "name": "tconstruct:molten_gold",
      "amount": 144
    }

    "fluid": {
      "tag": "forge:fluids/water_or_steam",
      "amount": 1000
    }

## ItemOutput
Same as [[Ingredient|Common-JSON-Value-Types#ingredient]]. Used for recipe outputs where the exact item output is irrelevant, like ingot casting.
### Example
    "result": {
      "tag": "forge:ingots/invar"
    }
 
## IFluidHandlerItem
Full item name of a fluid container item. Must extend the IFluidHandlerItem interface.
### Example
    "container": "minecraft:bucket"

## ToolCore
Full item name of a Tinkers tool. Must extend the ToolCore class.
### Example
    "result": "tconstruct:axe"

## IMaterialItem
Full item name of a material based item, usually a tool part. Must extend the IMaterialItem interface.
### Example
    "result": "tconstruct:pickaxe_head"

## MaterialId
Full name of a Tinkers material.
### Example
    "input": "tconstruct:bone"


## Tick
1/20th of a second.