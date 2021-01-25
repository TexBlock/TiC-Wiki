### Keys
`type`: Must be `"tconstruct:material"`.  
`ingredient`: [[Ingredient|Common-JSON-Value-Types#ingredient]]. The item to be associated with the material.  
`value`: Integer. Defaults to 1. How many baseline "ingots" one `ingredient` is worth.  
`needed`: Integer. Defaults to 1. How many `ingredient`s are needed to equal one baseline "ingot".  
`material`: [[MaterialId|Common-JSON-Value-Types#materialid]]. The material to be associated with the item.  

### Example
    {
      "type": "tconstruct:material",
      "ingredient": {
        "item": "minecraft:blaze_rod"
      },
      "value": 1,
      "needed": 1,
      "material": "tconstruct:blaze"
    }