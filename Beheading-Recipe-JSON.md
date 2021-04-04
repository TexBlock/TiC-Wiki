Location: `.jar/data/tconstruct/recipes/tools/beheading/`
## Simple Beheading Recipe
### Keys
`type`: Must be `"tconstruct:beheading"`.  
`entity`: [[EntityIngredient|Common-JSON-Value-Types#entityingredient]]. The entity being beheaded.  
`result`: [[ItemOutput|Common-JSON-Value-Types#itemoutput]]. The head to drop.  

### Example
    {
      "type": "tconstruct:beheading",
      "entity": {
        "type": "minecraft:skeleton"
      },
      "result": "minecraft:skeleton_skull"
    }


## Player Beheading Recipe
A dummy recipe that can be disabled to disable player beheading.
### Keys
`type`: `"tconstruct:player_beheading"`.  