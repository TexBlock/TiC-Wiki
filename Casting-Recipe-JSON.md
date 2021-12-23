Casting recipes allow converting a fluid and an optional item into an item.

## Item Casting

Basic casting recipe type. Casts a fluid onto an optional cast to produce a result.

### Keys

* `type` (string): May be `tconstruct:casting_basin` for a basin recipe or `tconstruct:casting_table` for a table recipe.
* `cast` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): If specified, this is the item required in the cast slot to cast the item. If unspecified, the table or basin must be empty.
* `cast_consumed` (boolean): If true, the cast item is consumed in the recipe, typically used for composites like seared stone. Defaults to false.
* `fluid` ([[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]): The fluid required to cast the item.  
* `result` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]): Casting result.
* `switch_slots` (boolean): If true the recipe output is put in the cast slot, and the cast in the output slot if present and not consumed. Used primarily for cast creation recipes. Defaults to false.
* `cooling_time` (integer): Time in ticks for the recipe to finish cooling. 1 tick is 1/20 of a second.

### Example

Pours 9 ingots (1296 mb) of molten cobalt into an empty casting basin to produce a cobalt block:

```json
{
  "type": "tconstruct:casting_basin",
  "fluid": {
    "name": "tconstruct:molten_cobalt",
    "amount": 1296
  },
  "result": "tconstruct:cobalt_block",
  "cooling_time": 225
}
```

Pours 125 mb of molten clay onto a stone button on a casting table to produce a seared brick. The stone button is consumed in the process.

```json
{
  "type": "tconstruct:casting_table",
  "cast": {
    "item": "minecraft:stone_button"
  },
  "cast_consumed": true,
  "fluid": {
    "tag": "tconstruct:molten_clay",
    "amount": 125
  },
  "result": "tconstruct:seared_brick",
  "cooling_time": 45
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/smeltery/casting/`.

## Material Fluid

Defines the fluid cost for a material for use in material and composite casting recipes.

### Keys

* `type` (string): Always `tconstruct:material_fluid`.
* `output` ([[MaterialId|Common-JSON-Value-Types#resourcelocation]]): Material produced by this recipe.
* `fluid` ([[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]): Fluid required to cast this material.
* `input` ([[MaterialId|Common-JSON-Value-Types#resourcelocation]]): If defined, this material will be produced in a composite recipe pouring over a part of this type. If not defined, material will be produced by pouring the fluid into a cast.
* `temperature` (integer): Temperature of the fluid for cooling time calculations. Typically the same as the melting temperature.

## Material Casting

Recipe creating a tool part using a tool part cast. Fluid type and amount are pulled from [Material Fluid recipes](#material-fluid).

### Keys
* `type` (string): Must be either `tconstruct:basin_casting_material` for basin tool parts or `tconstruct:table_casting_material` for table tool parts.
* `item_cost` (integer). The amount of baseline "ingots" required to cast. The fluid amount from [Material Fluid](#material-fluid) is multiplied this value for the total fluid cost.
* `cast` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): If specified, this is the item required in the cast slot to cast the item. If unspecified, the table or basin must be empty. Typically a bad idea to have a material casting recipe with no cast.
* `cast_consumed` (boolean): If true, the cast item is consumed in the recipe, typically used for single use sand casts. Defaults to false.
* `result` ([[IMaterialItem|Common-JSON-Value-Types#resourcelocation]]). Output part item.
* `switch_slots` (boolean): If true the recipe output is put in the cast slot, and the cast in the output slot if present and not consumed. Used primarily for cast creation recipes. Defaults to false.

### Example

Produces a pickaxe head by pouring fluid into a pickaxe head cast on a casting table. The cast is not consumed.

```json
{
  "type": "tconstruct:table_casting_material",
  "cast": {
    "item": "tconstruct:pickaxe_head_cast"
  },
  "item_cost": 2,
  "result": "tconstruct:pickaxe_head"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/tools/parts/casting/`

## Composite Casting

Recipe creating a tool part by pouring on another tool part of the correct material. Fluid type, amount, and material of the other tool part are pulled from [Material Fluid recipes](#material-fluid).

### Keys 

* `type` (string): Must be either `tconstruct:basin_casting_composite` for basin tool parts or `tconstruct:table_casting_composite` for table tool parts.
* `item_cost` (integer). The amount of baseline "ingots" required to cast. The fluid amount from [Material Fluid](#material-fluid) is multiplied this value for the total fluid cost. Generally should be the same as the corresponding material casting recipe.
* `result` ([[IMaterialItem|Common-JSON-Value-Types#resourcelocation]]). Output part item.  

### Example

Creates a repair kit by pouring a fluid on another repair kit of the correct material.

```json
{
  "type": "tconstruct:table_casting_composite",
  "result": "tconstruct:repair_kit",
  "item_cost": 2
}
```

More examples in `.jar/data/tconstruct/recipes/tools/parts/casting/` 

## Container Filling



### Keys
* `type` (string): Must be either `tconstruct:basin_filling` for basin recipes or `tconstruct:table_filling` for table recipes
* `fluid_amount` (integer): Maximum amount of fluid to add in millibuckets. May use less if the container is paritally filled.  
* `container` ([[IFluidHandlerItem|Common-JSON-Value-Types#ifluidhandleritem]]): The container to be filled.

### Example

Fills a bucket using 1000 mb of fluid in a casting table.

```json
{
  "type": "tconstruct:table_filling",
  "fluid_amount": 1000,
  "container": "minecraft:bucket"
}
```

Fills a scorched ingot gauge with 144 mb of fluid in a casting basin. If the gauge mostly full, less than 144 mb may be added.

```json
{
  "type": "tconstruct:basin_filling",
  "fluid_amount": 144,
  "container": "tconstruct:scorched_ingot_gauge"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/smeltery/casting/filling/`