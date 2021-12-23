Defines a recipe to turn an item into another item by selecting a pattern. Most recipes make use of the material corresponding to the input item, as defined by  [[Material Recipes|Material-Recipe-JSON]].

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [Item Part Recipe](#item-part-recipe)
- [Material Part Recipe](#material-part-recipe)
</td>
</table>

## Item Part Recipe

Converts a material into a specific item using the specified pattern.

### Keys
* `type`: Must be `tconstruct:item_part_builder`.  
* `pattern` ([[ResourceLocation|Common-JSON-Value-Types#resourcelocation]]): Name of the pattern. Corresponds to the language key `pattern.<domain>.<name>`
* `material` ([[MaterialId|Common-JSON-Value-Types#resourcelocation]]): Material required for this recipe.
* `cost` (integer): How many baseline "ingots" are needed to make one part.  
* `result` [[ItemOutput|Common-JSON-Value-Types#itemoutput]]: Output item.

### Example

Produces a stone ingot using the ingot pattern and 5 stone "units".

```json
{
  "type": "tconstruct:item_part_builder",
  "pattern": "tconstruct:ingot",
  "material": "tconstruct:stone",
  "cost": 5,
  "result": {
    "item": "tconstruct:stone_ingot"
  }
}
```

## Material Part Recipe

Converts material input into a material item with corresponding material.

### Keys
* `type`: Must be `"tconstruct:part_builder"`.  
* `pattern` ([[ResourceLocation|Common-JSON-Value-Types#resourcelocation]]): Name of the pattern. Corresponds to the language key `pattern.<domain>.<name>`
* `cost` (integer): How many baseline "ingots" are needed to make one part.  
* `result` (JsonObject): Output object.
    * `item` ([[IMaterialItem|Common-JSON-Value-Types#resourcelocation]]): Output material item. Will have the material applied.
    * `count` (integer): Number of the result item produced. Defaults to 1.

### Example

Produces an axe head using the axe head pattern and 2 material.

```json
{
  "type": "tconstruct:part_builder",
  "pattern": "tconstruct:axe_head",
  "cost": 2,
  "result": {
    "item": "tconstruct:axe_head"
  }
}
```

More examples in `.jar/data/tconstruct/recipes/tools/parts/`