This recipe defines melting an item in the smeltery, melter, or foundry to produce a fluid.

## Item Melting

Melts a specific item into a specific amount of fluid.

### Keys
* `type`: Three different variants of item melting exist:
    * `tconstruct:melting`: Normal melting recipe
    * `tconstruct:ore_melting`: Multiplies the size of `result` by the ore multiplier of the device melting the item. For example, smelteries have a ore multiplier of 2x, meaning the result will be doubled.
    * `tconstruct:damagable_melting`: Melting recipe that scales the result down based on the remaining durability of the input item.
* `ingredient` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Item to be melted.
* `result` ([[FluidStack|Common-JSON-Value-Types#fluidstack]]): Output fluid from the recipe.
* `byproducts` (array): List of [[FluidStacks|Common-JSON-Value-Types#fluidstack]] defining byproducts for this recipe in the foundry. If the device melting this item does not support byproducts, these fluids are ignored.
* `temperature` (integer): Minimum temperature of the fuel to melt the item. For comparison, solid fuel is 800 degrees, lava 1000 degrees, and blazing blood 1500 degrees.
* `time` (integer): Time to melt the item in ticks, that is 1/20th of a second.

### Example

Melts copper ingots into 1 ingot (144 mb) of molten copper.

```json
{
  "type": "tconstruct:melting",
  "ingredient": {
    "tag": "forge:ingots/copper"
  },
  "result": {
    "fluid": "tconstruct:molten_copper",
    "amount": 144
  },
  "temperature": 500,
  "time": 50
}
```

Melts an iron chestplate into 8 ingots (1152 mb) of molten iron. If the chestplate is damaged, less liquid is produced.

```json
{
  "type": "tconstruct:damagable_melting",
  "ingredient": {
    "item": "minecraft:iron_chestplate"
  },
  "result": {
    "fluid": "tconstruct:molten_iron",
    "amount": 1152
  },
  "temperature": 800,
  "time": 170
} 
```

Melts cobalt ore into 1 ingot (144 mb) of molten cobalt. The amount of cobalt is multiplied by the device's ore multiplier. The recipe has a byproduct of 3 nuggets (48 mb) of molten iron.

```json
{
  "type": "tconstruct:ore_melting",
  "ingredient": {
    "tag": "forge:ores/cobalt"
  },
  "result": {
    "fluid": "tconstruct:molten_cobalt",
    "amount": 144
  },
  "temperature": 950,
  "time": 97,
  "byproducts": [
    {
      "fluid": "tconstruct:molten_iron",
      "amount": 48
    }
  ]
}
```

More examples in `.jar/data/tconstruct/recipes/smeltery/melting/`

## Material Melting

Defines the fluid a material item melts into. The value of the parts and the parts that are meltable are determined by [[material casting recipes|Casting-Recipe-JSON#material-casting]].

### Keys
* `type` (string) Must be `"tconstruct:material_melting"`.  
* `input` [[MaterialId|Common-JSON-Value-Types#resourcelocation]]: Material to melt.
* `temperature` (integer): Minimum temperature of the fuel to melt the item, also used for time calculated.
* `result` [[FluidStack|Common-JSON-Value-Types#fluidstack]]: Value of a single "ingot" of this material. The amount is multiplied by the material's value from the [[material casting recipe|Casting-Recipe-JSON#material-casting]].

### Example

Determines that hepatizon melts into 144 mb of molten hepatizon at a temperature of 1400.

```json
{
  "type": "tconstruct:material_melting",
  "input": "tconstruct:hepatizon",
  "temperature": 1400,
  "result": {
    "fluid": "tconstruct:molten_hepatizon",
    "amount": 144
  }
}
```

More examples in `.jar/data/tconstruct/recipes/tools/materials/melting/`