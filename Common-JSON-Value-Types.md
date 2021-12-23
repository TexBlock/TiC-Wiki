<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [General](#general)
  * [ResourceLocation](#resourcelocation)
  * [Ingredient](#ingredient)
  * [FluidIngredient](#fluidingredient)
  * [EntityIngredient](#entityingredient)
  * [SizedIngredient](#sizedingredient)
  * [ItemOutput](#itemoutput)
  * [FluidStack](#fluidstack)
  * [Tick](#tick)
- [Unique](#unique)
  * [ModifierEntry](#modifierentry)
  * [ModifierMatch](#modifiermatch)
  * [SlotCount](#slotcount)
  * [RandomItem](#randomitem)
</td>
</table>

## General

These value types are defined either by vanilla Minecraft or by Mantle. Many of them are covered on [Mantle's wiki](/Mantle/wiki/Recipe-Components).


### ResourceLocation

String representing the registry name of an object in the game. Format is always `<domain>:<name>`, where `<domain>` typically represents a mod or datapack ID, and `<name>` is the specific name for this object. Valid characters are any lowercase letter, any number, `-`, `_`, and `/`. A single `:` is allowed between the domain and name.

Some JSON specifies resource locations belonging to particular registries:

* **Block**: Registry entry in block registry. For example `minecraft:stone` or `tconstruct:cobalt_ore`.
* **Item**: Registry entry in item registry. For example `minecraft:diamond` or `tconstruct:iron_reinforcement`.
    * **`IFluidHandlerItem`**: Item that contains a `IFluidHandlerItem` capability. For example `minecraft:bucket` or `tconstruct:copper_can`.
    * **`IModifiable`**: Item that implements the `IModifiable` interface giving it a tool definition. For example `tconstruct:axe`
    * **`IMaterialItem`**: Item that implements the `IMaterialItem` interface, typically a tool part. For example `tconstruct:pickaxe_head`.
* **Fluid**: Registry entry in fluid registry. For example `minecraft:water` or `tconstruct:molten_iron`.
* **Modifier**: Registry entry in modifier registry. For example `tconstruct:haste` or `tconstruct:revitalized`.
* **MaterialId**: Represents a specific material registered through a datapack. See `data/<domain>/materials/` for material definitions.

### Ingredient
Vanilla recipe input. See [Mantle's wiki](/SlimeKnights/Mantle/wiki/Recipe-Components#ingredient) for more info. In addition to ingredients defined by vanilla or Mantle, Tinkers' Construct defines several new types of ingredients.

####

### FluidIngredient

Mantle fluid ingredient for recipes taking fluids as input. See [Mantle's wiki](/SlimeKnights/Mantle/wiki/Recipe-Components#fluidingredient) for keys and more info.

### EntityIngredient

Mantle entity ingredient for recipes taking entities as input. See [Mantle's wiki](/SlimeKnights/Mantle/wiki/Recipe-Components#entityingredient) for keys and more info.

### SizedIngredient

Mantle ingredient for an ingredient with a minimum size. See [Mantle's wiki](/SlimeKnights/Mantle/wiki/Recipe-Components#sizedingredient) for keys and more info.

### ItemOutput

Mantle result for item outputs in recipes. Supports outputting items both from an item name and from a tag using Mantle's preference. See [Mantle's wiki](/SlimeKnights/Mantle/wiki/Recipe-Components#itemoutput) for keys and more info.

### FluidStack
Represents a fluid as a recipe output. See [Mantle's wiki](/SlimeKnights/Mantle/wiki/Recipe-Components#fluidstack) for keys and more info.

### Tick
1/20th of a second.

## Unique

These value types are defined as part of Tinkers' Construct.

### ModifierEntry

Full name and level of a modifier to be added.

#### Keys

* `name` ([Modifier](#resourcelocation)): Full modifier name.
* `level` (integer): Level of the modifier to be added, defaults to 1. 

#### Example

Represents 1 level of the silky modifier:
```json
{
  "name": "tconstruct:silky"
}
```

Represents 2 levels of the leaping modifier:

```json
{
  "name": "tconstruct:leaping",
  "level": 2
}
```

### ModifierMatch

Modifier match is a simple way for a recipe to specify the required modifiers. It supports two forms: entry and list

#### Entry

Same format as [ModifierEntry](#modifierentry). Represents a single modifier that must be present and the minimum level.

In addition to all the keys specified by the two types, the top level ModifierMatch supports one extra key:
* `error` (String): The translation key of the error to shown if the ModifierMatch fails. Only available on the top level.

#### List

Matches if the required number of items in the matches.

**Keys**:

* `options` (array): List of ModifierMatch objects.  Can be either an entry or another list.
* `matches_needed` (integer): The amount of matches from the list required.
    * Setting to 0 is effectively a Boolean true
    * Setting to 1 is effectively an OR condition
    * Setting to the size of the list is effectively an AND condition
    * Setting to a value larger than the list size is a Boolean false 

#### Examples

Matches 2 or more levels of the expanded modifier. Errors with the specified key.

```json
{
  "name": "tconstruct:expanded",
  "level": 2,
  "error": "recipe.tconstruct.modifier.ender_expander_requirements"
}
```

Matches any two of the diamond, emerald, and netherite modifiers:
```json
{
  "options": [
    {
      "name": "tconstruct:diamond",
      "level": 1
    },
    {
      "name": "tconstruct:emerald",
      "level": 1
    },
    {
      "name": "tconstruct:netherite",
      "level": 1
    }
  ],
  "matches_needed": 1,
  "error": "recipe.tconstruct.modifier.gardite_requirements"
}
```

### SlotCount

Contains information about the modifier slots in a recipe. The format for `SlotCount` is `{ "<type>": <slots> }` where `<type>` is the type of modifier slots required, and `<slots>` is the number of that type needed. At most one type can be specified, if no type is specified the modifier is considered "slotless".

For more information on modifier slots, see [[Modifier Slot Types]]

#### Example

Requires 2 modifier slots of type `upgrades`:

```json
"slots": {"upgrades": 2}
```

### RandomItem

Represents an item with a random chance and stack size. Can be constant (always returns the given item), range (returns between `min` and `max` items), or chance (has a `chance` percent chance of the result).

#### Keys

* *All keys from [ItemOutput](#itemoutput)*
* `chance` (float): Number between 0 and 1 for the percent chance of this item.
* `min` (integer): Minimum number of items to produce. Maximum will be the count of the item
* `max` (integer): Alias for `count` as `min` and `max` looks cleaner than `min` and `count`.