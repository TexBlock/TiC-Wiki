In 1.16 builds and later, Tinkers' Construct adds several commands under the root command `/tconstruct`.

## Modifiers

Command to change modifiers on a tool. See sub commands for more information. For modifier IDs, a full list can be printed using `[the Modifier Usage command](#modifier-usage), or IDs can be discovered in datapacks or JEI recipes.

### Add Modifier

Adds a modifier to the currently held tool. Does not require any slots to be applied, and will act as though it was applied through a modifier recipe (including being removable with a wet sponge). Bypasses max level restrictions, but not other modifier restrictions (such as netherite requiring diamond or emerald). Fails if the target's hand is empty or does not contain a modifiable item.

#### Syntax

```
/tconstruct modifiers <targets> add <modifier> [<level>]
```

#### Arguments

* `<targets>`: Vanilla target selector
* `<modifier>`: Registry name of the modifier to add
* `<level>`: Level to add. Must be 1 or greater, if unset defaults to 1

### Remove Modifier

Removes a modifier from the tool. Does not restore any slots or grant salvage, unlike the modifier removal recipe. Cannot remove tool or material traits, use datapacks to change those. Cannot remove a modifier if it would leave the tool in an invalid state.

#### Syntax

```
/tconstruct modifiers <targets> remove <modifier> [<level>]
```

#### Arguments

* `<targets>`: Vanilla target selector
* `<modifier>`: Registry name of the modifier to remove
* `<level>`: Number of levels to remove. Must be 1 or greater, if unset, removes all levels

## Tool Stats

This command allows directly modifying a tool's stats. Any changes made in this command will be shown in the tooltip of the "Stat Override" modifier. See sub commands for more information

### Bonus Stats

Adds stat bonuses to the tool. These bonuses will apply before the tool's multipliers, meaning the stat adjustment may not be exactly the same as result shown.

#### Syntax

```
/tconstruct tool_stats <targets> bonus <operation> <stat_type> <value>
```

#### Arguments

* `<targets>`: Vanilla target selector
* `<operation>`: Operation to perform. Can be either `add` to adjust the bonus, or `set` to directly set the current bonus. Note the two are equivalent if there is no bonus for the given stat.
* `<stat_type>`: ID of the stat to modify. See [#Stat Types](#stat-types) for a list of default options
* `<value>`: Amount to add, or new value for set. Can be negative.

### Stat Multipliers

Multiplies tool stats by the given value. Multiplies apply after bonuses.

#### Syntax

```
/tconstruct tool_stats <targets> multiplier <operation> <float_stat> <value>
```

#### Arguments

* `<targets>`: Vanilla target selector
* `<operation>`: Operation to perform. Can be either `multiply` to adjust the multiplier, or `set` to directly set the current multiplier. Note the two are equivalent if there is no bonus for the given stat.
* `<float_stat>`: ID of the stat to modify. See [#Stat Types](#stat-types) for a list of default options. Only supports stats with a numerical value.
* `<value>`: Multiplier amount

### Reset Stats

Resets bonuses and multipliers applied to the tool from this command. Running without the stat type command is equivalent to running `/tconstruct modifiers <target> remove tconstruct:stat_override`.

#### Syntax

```
/tconstruct tool_stats <targets> reset [<stat_type>]
```

#### Arguments

* `<targets>`: Vanilla target selector
* `<stat_type>`: ID of the stat to reset. See [#Stat Types](#stat-types) for a list of default options. If unset, resets all stats.
* `<value>`: Amount to add, or new value for set. Can be negative.

### Stat Types

The following stat types are provided by Tinkers' Construct:

* `tconstruct:durability`: Tool's max durability
* `tconstruct:attack_damage`: Damage dealt by the tool in melee
* `tconstruct:attack_speed`: Rate of the tool's full power attack
* `tconstruct:mining_speed`: Speed at which the tool breaks blocks
* `tconstruct:secondary_mining`: Multiplier to mining speed when the mattock mines non-dirt blocks

One stat type deserves special mention due to its behavior. `tconstruct:harvest_level` will allow adjusting the harvest level of the tool, but due to harvest level ability it is not possible to reduce the harvest level of a tool, only increase it. Values used by this command may also be slightly different from expected values due to stat internals. Harvest level multipliers are not supported.

## Slots

Allows modifying the number of modifiers slots on a tool.

### Syntax

```
/tconstruct slots <target> add <slot_type> [<count>]
/tconstruct slots <target> set <slot_type> <count>
```

### Arguments

* `<targets>`: Vanilla target selector
* `<slot_type>`: Slot type to add. See [[Modifier Slot Types]] for valid values.
* `<count>`: Number of slots to add, or new number of slots for set. Defaults to 1 if unset for add, required for set

## Modifier Usage

Prints a table to the mod log with with information on how each modifier is used. This command is designed for modpack and datapack makers to identify unused modifiers for usage as tool traits. All modifiers will print information on whether they are used in recipes, or as a material or tool trait.

### Syntax

```
/tconstruct modifier_usage [<filter>]
/tconstruct modifier_usage recipe [<slot_type>]
```

### Arguments

* `<filter>`: Filters the result to only show modifiers with a particular usage. Valid options:
    * `all`: Shows all modifiers
    * `recipe`: Shows only modifiers used in recipes
    * `material_trait`: Shows only modifiers used as a material trait, see also the material traits JSON
    * `tool_trait`: Shows only modifiers used as a tool trait, see also the tool definition JSON
    * `unused`: Shows only modifiers that are not used in any of the above usages
* `<slot_type>`: Filters recipes to show only recipes of a particular slot type.
    * See [[Modifier Slot Types]] for valid values
    * Supports the special type `slotless` to show usages in recipes with no slot type

## Generate Part Textures

Generates part textures for materials in the mod. For more information, see [[Texture Generators (Data Packs)]].

### Syntax

```
/tconstruct generate_part_textures <filter> [<mod_id>|<material>]
```