This recipe defines an item input for a material. It is used both in the part builder for part crafting and in the tinker station for repairing tools.

### Keys
* `type` (string): Always `tconstruct:material`.
* `ingredient` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Item to associate with the material. In general, an item can only match one material.
* `value` (integer): How many baseline "ingots" this recipe produces of the material. Defaults to 1.
* `needed` (integer): How many `ingredient`s are needed to produce `value` of the material. Defaults to 1.
* `material ([[MaterialId|Common-JSON-Value-Types#resourcelocation]]): The material to be associated with the item.
* `leftover` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]): extra item produced if the recipe cost is not a multiple of `value`.

### Example

Associates iron nuggets with the iron material. 9 iron nuggets are needed to produce 1 iron material. Note that the iron material is not defined as being craftable, meaning this recipe only allows nuggets to be used for repairing iron tools.

```json
{
  "type": "tconstruct:material",
  "ingredient": {
    "tag": "forge:nuggets/iron"
  },
  "value": 1,
  "needed": 9,
  "material": "tconstruct:iron"
}
```

Associates blaze rods with the blaze material at a value of 3. If a recipe cost is not a multiple of 3, 1 blaze rod will be given per leftover `value`.

```json
{
  "type": "tconstruct:material",
  "ingredient": {
    "item": "minecraft:blaze_rod"
  },
  "value": 3,
  "needed": 1,
  "material": "tconstruct:blaze",
  "leftover": "minecraft:blaze_powder"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/tools/materials/`