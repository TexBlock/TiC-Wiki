This recipe allows combining two items on top of a casting table to modify one of the items. It is primarily used for creating sand casts.

### Keys
* `type`: Must be either `tconstruct:molding_basin` for basin recipes or `tconstruct:molding_table` for table recipes
* `material` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Item placed into the casting implement first.
`pattern` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Item placed into the casting implement second. If undefined, this recipe instead defines behavior for picking up an item from the table. 
`pattern_consumed` (boolean): If true, the pattern is consumed during the molding operation. Defaults to false.
* `result` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]): Item produced from the molding recipe.

### Example

Defines a recipe where placing a repair kit on a blank sand cast produces a repair kit sand cast. The repair kit is preserved and can be picked up.

```json
{
  "type": "tconstruct:molding_table",
  "material": {
    "item": "tconstruct:blank_sand_cast"
  },
  "pattern": {
    "item": "tconstruct:repair_kit",
    "type": "tconstruct:material"
  },
  "result": "tconstruct:repair_kit_sand_cast"
}
```

Defines that picking up any sand cast results in a blank sand cast on pickup.

```json
{
  "type": "tconstruct:molding_table",
  "material": {
    "tag": "tconstruct:casts/sand"
  },
  "result": "tconstruct:blank_sand_cast"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/casts/sand_casts/`