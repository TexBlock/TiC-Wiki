
<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

* [Ingredient](#ingredient)
* [FluidIngredient](#fluidingredient)
* [EntityIngredient](#entityingredient)
* [SizedIngredient](#sizedingredient)
* [ItemOutput](#itemoutput)
* [FluidStack](#fluidstack)
* [ModifierEntry](#modifierentry)
* [ModifierMatch](#modifiermatch)
* [ResourceLocation](#resourcelocation)
* [IFluidHandlerItem](#ifluidhandleritem)
* [ToolCore](#toolcore)
* [IMaterialItem](#imaterialitem)
* [MaterialId](#materialid)
* [Tick](#tick)
* [Color](#color)
</td>
</table>

## Ingredient
Vanilla recipe input. Can be either an item stack or a tag.

## FluidIngredient
A fluid recipe input. The input can be an array of both types and tags.
### Keys
`name`: The fluid's full name.  
`tag`: Forge tag. Used when the recipe can have multiple possible inputs.  
`amount`: Integer. The fluid amount in millibuckets.  
### Examples
    "fluid": {
      "name": "tconstruct:molten_gold",
      "amount": 144
    }

    "fluid": [
      {
        "name": "minecraft:water",
        "amount": 1000
      },
      {
        "tag": "forge:fluids/steam",
        "amount": 1000
      }
    ]


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

## SizedIngredient
Similar to [[Ingredient|Common-JSON-Value-Types#ingredient]], but needs at least `amount_needed` of the ingredient to be present.
### Keys
`ingredient`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. Optional, if missing, the whole object is considered an ingredient. The item to be used.  
`amount_needed `: Integer. Defaults to 1. The amount of `ingredient` needed for the recipe.  
### Examples
    {
      "item": "tconstruct:reinforcement"
    }

    {
      "ingredient": {
        "item": "tconstruct:bone_hurting_nugget"
      },
      "amount_needed": 9
    }

## ItemOutput
Used for recipe outputs where the exact item output could be irrelevant, like ingot casting.  
### Keys
`tag`: Forge tag. Used when the recipe can have any possible tagged output.  
`count`: Integer. Defaults to 1. The item count.  
`nbt`: NBT for the item.
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

## ModifierEntry
Full name and level of a modifier to be added.  
### Keys
`name`: Full modifier name.  
`level`: Integer. Defaults to 1. The level of the modifier to be added.  
### Example
    {
      "name": "tconstruct:silky",
      "level": 1
    }

## ModifierMatch
A recursive list of ModifierMatch and [[ModifierEntry|Common-JSON-Value-Types#modifierentry]] objects. The top object can be a ModifierEntry.  
### Keys
`options`: List of ModifierMatch and ModifierEntry objects.  
`matches_needed`: Integer. The amount of matches from the list required.  
`error`: String. The translation key of the error to shown if the ModifierMatch fails. Only available on the top level.
### Examples
    {
      "name": "tconstruct:expanded",
      "level": 1,
      "error": "recipe.tconstruct.modifier.ender_expander_requirements"
    },
    {
      "options": [
        {
          "name": "tconstruct:diamond",
          "level": 1
        },
        {
          "name": "tconstruct:emerald",
          "level": 1
        }
      ],
      "matches_needed": 1,
      "error": "recipe.tconstruct.modifier.netherite_requirements"
    }

 

## ResourceLocation
https://mcforge.readthedocs.io/en/latest/concepts/resources/

## IFluidHandlerItem
Full item name of a fluid container item. Must implement the IFluidHandlerItem capability.
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

## Color
A hex RRGGBB color.
### Example
    "color": "3ce186"