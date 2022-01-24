Spilling recipes define behavior when attacking entities with the spilling modifier, or when drinking fluid with the slurping modifier.

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [Spilling Effects](#spilling-effects)
  * [Cure Effects](#cure-effects)
  * [Damage](#damage)
  * [Effect](#effect)
  * [Extinguish](#extinguish)
  * [Restore Hunger](#restore-hunger)
  * [Set Fire](#set-fire)
  * [Teleport](#teleport)
  * [Calcified](#calcified)
- [Spilling](#spilling)
</td>
</table>

## Spilling Effects

Spilling recipes apply an array of spilling effects to a fluid. This section describes all available effects and their formats.

### Cure Effects

Cures potion effects on the entity.

**Keys**:

* `type` (string): Always `tconstruct:cure_effects`
* `item` ([[ResourceLocation|Common-JSON-Value-Types#resourcelocation]]): Item used to cure the potion effects. Typically milk
* `nbt` (string): NBT to apply to the stack, if unset the stack will have no NBT

**Example**:

Cure potion effects using milk.

```json
{
  "type": "tconstruct:cure_effects",
  "item": "minecraft:milk_bucket"
}
```

### Damage

Damages the entity the given amount

**Keys**:

* `type` (string): Always `tconstruct:damage`
* `entity` (mixed): One of the following options:
    * `any`: Matches any entity, default
    * `water_sensitive`: Damages entities that take damage from water, such as blazes and endermen
    * `undead`: Damages undead entites
    * `arthropod`: Damages spider-like mobs
    * `not_fire_immune`: Damages entities that are not immune to fire
    * [[EntityIngredient|Common-JSON-Value-Types#entityingredients]]: damages the entities matching the ingredient
* `damage_type` (string): Type of damage to apply. The following options are available:
    * `normal`: Normal melee damage
    * `fire`: Fire damage, less effective against fire protection
    * `magic`: Magic damage like potions, less effective against magic protection
    * `explosion`: Explosion damage, less effective against explosion protection
    * `piercing`: Damage that pierces armor
* `damage_amount` (float): Amount of damage to deal

**Example**:

Damages an entity that is not fire immune using 3.0 fire damage.

```json
{
  "type": "tconstruct:damage",
  "entity": "not_fire_immune",
  "damage_type": "fire",
  "damage_amount": 3.0
}
```

### Effect

Applies a potion effect to the entity.

**Keys**:

* `type` (string): Always `tconstruct:effect`
* `name` ([[ResourceLocation|Common-JSON-Value-Types#resourcelocation]]): Potion name
* `time` (integer): Time of the effect in seconds
* `level` (integer): Level of the effect to apply, starting at 1. Defaults to 1 if unset.

**Example**:

Applies 10 seconds of Poison I to the target.

```json
{
  "type": "tconstruct:effect",
  "name": "minecraft:poison",
  "time": 10,
  "level": 1
}
```

### Extinguish

Extinguishes fire on the entity. This effect has no extra keys, just the type `tconstruct:extinguish`.

### Restore Hunger

Fills the entity's hunger and saturation.

**Keys**:

* `type` (string): Always `tconstruct:cure_effects`
* `hunger` (integer): Hunger to restore
* `saturation` (saturation): Saturation to restore

**Example**:

Restores 1 hunger and 0.2 saturation

```json
{
  "type": "tconstruct:restore_hunger",
  "hunger": 1,
  "saturation": 0.2
}
```

### Set Fire

Sets the entity on fire for the given time

**Keys**:

* `type` (string): Always `tconstruct:set_fire`
* `time` (integer): Fire time in seconds

**Example**:

Sets the entity on fire for 5 seconds
```json
{
  "type": "tconstruct:set_fire",
  "time": 5
}
```

### Teleport

Teleports the entity randomly. This effect has no extra keys, just the type `tconstruct:teleport`.

### Calcified

Applies the calcified effect or resistance effect if the player has the proper slimeskull types. This effect has no extra keys, just the type `tconstruct:calcified`.

## Spilling

Spilling recipes assign the effects to a fluid to apply from the relevant modifiers.

### Keys

* `type` (string): Always `tconstruct:spilling`
* `fluid` ([[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]): Fluid consumed for the recipe. Amount determines the maximum amount consumed. If the tank contains less fluid, the effect will be scaled down.
* `effects` (array): List of effects to apply.

### Examples

Causes molten gold to deal 2 magic damage, and set the entity on fire for 3 seconds. this is done at a cost of 50 mb of molten gold.

```json
{
  "type": "tconstruct:spilling",
  "fluid": {
    "tag": "forge:molten_gold",
    "amount": 16
  },
  "effects": [
    {
      "type": "tconstruct:damage",
      "damage_type": "magic",
      "damage_amount": 2.0
    },
    {
      "type": "tconstruct:set_fire",
      "time": 3
    }
  ]
}
```

More examples are located in `TConstruct.jar/data/tconstruct/recipes/tools/spilling/`