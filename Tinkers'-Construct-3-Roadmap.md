## Already In the Alpha

The following subsections contain major features that are already coded. They are either in the currently released alphas or will be in an upcoming alpha.

### Crafting
**Tool Tables**

* Part builder, tinker station, tinker's anvil
* Modifier chest, part chest, cast chest

**Smeltery**

* Melter and melting
* Casting table and basins
* Faucets and channels
* Smeltery components
    * Controller
    * Drain, chute, duct
    * Tanks
    * Melting, alloying, entity melting

### Tools

**Tool types**

* Small: broadsword
    * Harvest: pickaxe, mattock, axe, kama
* Large: cleaver
    * Harvest: sledge hammer, vein hammer, broad axe, excavator, cleaver, scythe

**Materials**

* Tier 1: Wood, stone, flint, bone, necrotic bone
* Tier 2: Iron, copper, seared stone, slimewood
* Tier 2 compat: Lead, silver, electrum
* Tier 3: tinkers' bronze, nahuatl, slimesteel, rose gold, pig iron, cobalt
* Tier 3 compat: Steel, bronze, constantan
* Tier 4: Queen's slime, hepatizon, manyullyn

**Modifiers**

* Free: Worldbound, Overslime, Creative
    * Bonus upgrade slots: book and quill, music disc, mob head, end crystal
* Upgrades: Reinforced, Experienced, Magnetic, Soulbound, Tank
    * Harvest: Haste, Blasting, Lightspeed, Hydraulic 
    * Weapon: Beheading, Necrotic, Knockback, Fiery
    * Damage boost: Sharpness, Smite, Bane of Arthropods, Antiaquatic, Cooling
    * Tier modifiers: Emerald, Diamond, Netherite
* Abilities: Gilded, Bucketing, Glowing
    * Range: Expanded, Reach
    * Loot: Silk Touch, Luck, Autosmelt, Melting
    * Block transform: tilling, pathing, stripping

**Other**

* Repair kits

### Resources

**Worldgen**

* Ores
    * Copper ore in the overworld
    * Cobalt ore in the nether
* Overworld slime islands
    * Spawn in green and blue variants
* Blood slime islands
    * Spawn in the nether, contain ichor and blood saplings
* Necrotic bones
    * Drop from wither skeletons
* End slime islands
    * Contain ender slime
    * Currently wrong flora, no mobs

### Book

* Materials and You
    * Mostly complete, apart from new info in later editions
    * Has full list of tier 1 materials and traits
    * Has a modifier listing, though a few modifiers will be moved to another book later
* Puny Smelting
    * Has full list of tier 2 materials and traits
* Mighty Smelting
    * Has full list of tier 3 and 4 materials and traits
    * Has information on how to obtain molten blaze
* Tinkers Gadgetry
    * Placeholder book for future documentation

## Next features

This section discusses the next features being worked on, which will be added in later, regular alphas.

### Documentation

**Datapacks**

* Document material creation

**Book**

* Puny Smelting
    * Melter and melting
    * Casting
* Mighty Smelting
    * Smeltery
    * Tinkers' Anvil modifiers
* Fantastic Foundry (title pending)
    * Alloy tank
    * Foundry
    * Tier 1-3 nether materials?
    * Tier 4 nether materials

### Smeltery

* Smeltery interface
    * Allows accessing the UI fluid tank
    * Comparator signal for tank level
    * On pulse, switches fluid order (bottom to top? Top to bottom?)
* Sand casts: allow placing sand second?
* Fix smeltery transparent fluids

### Foundry

* Nether smeltery variant
* Does not alloy
* Lower ore rate, but produces byproducts
* Higher capacity

### Alloy Tank

* Alloys from neighboring blocks
* Augments the foundry to allow alloying

### Tools

**Data packs**

* Support tagged fluids in materials, possibly via recipes
* Trait manager cleanup

**Part Builder**

* Send leftovers to player inventory
* Cleanup behavior to be more like the tinker station
* Add part forge? the tier 3 version for crafting large parts
* Better sorting in UI

**Tools**

* Dagger
* Battle sign

**Modifiers**

* Mending
    * New general ability
    * Requires something from the end to craft
    * Tool repairs on XP pickup
* Sweeping edge
    * Boosts damage of mobs in sweep attacks for swords and cleavers
    * How is this different from scythes? Should it affect scythes?
* Blocking
    * Battle sign ability as a modifier
    * If used on a battle sign, upgrades to full blocking like shields
* Unbreakable
    * Requires reinforced V and one ability slot to apply
    * Need something in the end to craft, undecided at this point

**Tool Model**

* Modifier models
    * Supports direct texture scan
    * Supports custom models registered for modifier types

### Resources

**Worldgen**

* Ender slimes and foliage
* New earth, sky, and blood wood variants for slimy saplings, replaces congealed slime

### Misc

* Texture generators
* Find a good way to handle duplicate materials between mods. We just going to resort to conditions?
    * Might need to make recipes directly referencing materials automatically disable if the material is not found
* Content transfer:
    * Wooden rails move to Tinkers' Mechworks
    * Jerky, stone ladders and torches, punji sticks, and dried clay move to Natura

## Before beta release

Once the content in the above section is finished, content in this section is the next target. Once the API is stable during this section, the mod will be released as a beta instead of an alpha, and will be much more ready for addons. 

Before this beta, any addons need to be prepared to update as we make new alphas as our API needs a lot of cleanup from 1.12. Once the first beta is released, the API should remain stable.

### Crafting
**Multiblock**

* Soul Forge
    * Include new book or add to nether book
* End Smeltery (upside down/gasses)
* Gravity smeltery peripheral

### Tools

**Tool types**

* Shield
* Armor

**Materials**

* Tier 1: Chorus
* Tier 2: End Stone
* Tier 3: Dragonstone, Hollow
* Tier 4: Slimebronze, Soulsteel
* Tier 5: KnightSlime, Ebonite, Alexandrite

**Modifiers**

* Armor modifiers

### Resources

**Worldgen**

* Ichor slimes and slime islands

### Cleanup

* Library cleanup (remove unused code)

## Long term content

This section just describes some content that will be in the mod eventually, but is far off being done.

### Tools

**Tool types**

* Bows
* Crossbows
* Boomerang
* Spear
* Fishing Rod

**Modifiers**

* Bow modifiers
* Throwing