In addition to the many modifiers used as traits, upgrades, and abilities, Tinkers' Construct provides several unused modifiers which may be useful for modpack makers adding either custom materials or modifiers.

## Bonus Modifier Slots

Three modifiers are registered under the IDs `tconstruct:red_extra_upgrade`, `tconstruct:green_extra_upgrade`, and `tconstruct:blue_extra_upgrade` which all grant +1 upgrade slot in a similar vein to `tconstruct:writable` or `tconstruct:harmonious`. In addition, a modifier is registered as `tconstruct:extra_ability` which provides +1 ability slot like the `tconstruct:draconic` modifier. The intention with these modifiers is to allow a modpack to add additional modifier recipes for single use bonus modifier slots based on content in the pack (such as extra dimensions). Note that in addition to adding the recipes, it is encouraged to provide a resource pack to change the extra modifier names based on the recipe you provide.

If for some reason this is not enough modifier slots for your pack, it is also possible to increase the max level on existing modifiers such as `tconstruct:writable` to allow applying them multiple times, either by changing the `max_level` field or by adding a second recipe in the same way the luck modifier recipes work. either case, the result is the tool will end up with "Writable II" or a similarly named second level of a modifier.

For an example recipe for one of these modifiers, see the recipe for the [writable modifier](/SlimeKnights/TinkersConstruct/blob/1.16/src/generated/resources/data/tconstruct/recipes/tools/modifiers/slotless/writable.json). Note it is set up to allow at most 1 level of the modifier, meaning writable cannot be applied multiple times.

## Unused Modifiers

There are several modifiers that are registered in Tinkers' Construct that are not currently being used, which are ideal for using either as a material trait. In addition, if your pack lacks one of the materials Tinkers' Construct provides automatic compat for, you can reuse it's trait on another material without duplicating traits.

The following modifiers are unused by default:

* `tconstruct:fortune`: Provides +1 looting per level, increasing block drops like the vanilla enchantment. Stacks with the Luck ability.
* `tconstruct:looting`: Provides +1 looting per level, increasing mob drops like the vanilla enchantment. Stacks with the Luck ability

The following modifiers are used exclusively on a compatibility material:

* `tconstruct:heavy`: Increases attack damage by 10% and reduces movement speed by 10%. Used by lead by default.
* `tconstruct:ductile`: Increases attack damage, attack speed, durability, and mining speed by 4% each. Used by steel by default.
* `tconstruct:maintained_2`: Boosts the mining speed of a tool at high durability. Uses a different formula than the Tinkers' bronze trait. Used by bronze by default.
* `tconstruct:temperate`: Boosts mining speed of a tool in extreme temperatures. Used by constantan by default.