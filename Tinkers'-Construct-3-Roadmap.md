## In Latest Alpha
The following subsections contain major features that are included in the current alpha on CurseForge.

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
* Alloyer and alloying
* Foundry components
    * Controller
    * Drain, chute, duct
    * Tanks
    * Melting, byproducts, entity melting

**Foundry**

* Casting 

### Tools

**Tool types**

* Small: broadsword
    * Harvest: pickaxe, mattock, axe, kama
* Large: cleaver
    * Harvest: sledge hammer, vein hammer, broad axe, excavator, cleaver, scythe

**Materials**

* Tier 1: Wood, stone, flint, bone, necrotic bone
* Tier 2: Iron, copper, seared stone, scorched stone, slimewood
* Tier 2 compat: Lead, silver, electrum
* Tier 3: tinkers' bronze, nahuatl, slimesteel, rose gold, pig iron, cobalt
* Tier 3 compat: Steel, bronze, constantan
* Tier 4: Queen's slime, hepatizon, manyullyn

**Modifiers**

* Free: Worldbound, Overslime, Creative
    * Bonus upgrade slots: book and quill, music disc, mob head, end crystal
* Upgrades: Reinforced, Experienced, Magnetic, Soulbound, Tank, Overforced
    * Harvest: Haste, Blasting, Lightspeed, Hydraulic 
    * Weapon: Beheading, Necrotic, Knockback, Fiery, Sweeping Edge
    * Damage boost: Sharpness, Smite, Bane of Arthropods, Antiaquatic, Cooling
    * Tier modifiers: Emerald, Diamond, Netherite
* Abilities: Gilded, Bucketing, Glowing, Unbreakable
    * Range: Expanded, Reach
    * Loot: Silk Touch, Luck, Autosmelt, Melting
    * Block transform: tilling, pathing, stripping

**Special recipes**

* Repair kits
* Wet sponge to remove modifiers
* Potion of Harming to damage tools

### Resources

**Worldgen**

* Ores
    * Copper ore in the overworld
    * Cobalt ore in the nether
* Overworld sky slime islands
    * Spawn in green and blue variants
    * Contain blue foliage and skyroot wood
* Blood slime islands
    * Spawn in the nether
    * Contain ichor and blood
    * Contains bloodshrooms
* Necrotic bones
    * Drop from wither skeletons
* End slime islands
    * Contain ender slime
    * Currently no mobs
    * Temporary home of greenheart wood

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

This section discusses the next features being worked on, which will be added in later alphas (but not necessarily the next)

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
* Fantastic Foundry
    * Alloyer
    * Foundry
    * Tier 1-3 nether materials?
    * Tier 4 nether materials

### Smeltery

* Smeltery interface (possibly)
    * Allows accessing the UI fluid tank
    * Comparator signal for tank level
    * On pulse, switches fluid order (bottom to top? Top to bottom?)
* Sand casts: allow placing sand second?
* Fix smeltery transparent fluids

### Tools

**Data packs**

* Support tagged fluids in materials, possibly via recipes

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
* Blocking
    * Battle sign ability as a modifier
    * If used on a battle sign, upgrades to full blocking like shields
* Duel Wielding
    * Similar to the daggers ability, but for any tool

**Tool Model**

* Modifier models
    * Supports direct texture scan
    * Supports custom models registered for modifier types

### Resources

**Worldgen**

* Update ender slime island foliage to a chorus like plant

### Misc

* Texture generators
* Find a good way to handle duplicate materials between mods. We just going to resort to conditions?
    * Might need to make recipes directly referencing materials automatically disable if the material is not found
* Content transfer:
    * Wooden rails move to Tinkers' Mechworks
    * Jerky, stone ladders and torches, punji sticks, and dried clay move to Natura
* CraftTweaker support
    * Jared made a pull request with support, will hopefully be reviewed before the next alpha

## Before beta release

Once the content in the above section is finished, content in this section is the next target. Once the API is stable during this section, the mod will be released as a beta instead of an alpha, and will be much more ready for addons. 

Before this beta, any addons need to be prepared to update as we make new alphas as our API needs a lot of cleanup from 1.12. Once the first beta is released, the API should remain stable.

### Crafting
**Multiblock**

* Soul Forge
    * Include new book or add to nether book
* End Smeltery (upside down/gasses)
* "Smeltery sandwich"

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

* Charge attack modifier
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