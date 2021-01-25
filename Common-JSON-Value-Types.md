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

## EntityIngredient
An entity. Used for entity melting. The input can be an array of both types and tags.
### Keys
`type`: Full entity type.  
`tag`: Forge entity tag.  
`types`: An array of entity types.  
### Example

    "entity": {
      "type": "minecraft:creeper"
    }

    "entity": [
      {
        "tag": "minecraft:skeletons"
      },
      {
        "type": "minecraft:skeleton_horse"
      }
    ]

    "entity": {
      "types": [
        "minecraft:villager",
        "minecraft:wandering_trader"
      ]
    }

## ItemOutput
Same as [[Ingredient|Common-JSON-Value-Types#ingredient]]. Used for recipe outputs where the exact item output is irrelevant, like ingot casting.
### Example
    "result": {
      "tag": "forge:ingots/invar"
    }

## FluidStack
Similar to [[FluidIngredient|Common-JSON-Value-Types#fluidingredient]], but cannot take a tag (the fluid must be exact).
### Example
    "result": {
      "fluid": "tconstruct:molten_electrum",
      "amount": 288
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