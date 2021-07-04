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
* Potion of Harming to damage tools

### Resources

**Worldgen**

* Ores
    * Copper ore in the overworld
    * Cobalt ore in the nether
* Overworld skyslime islands
    * Spawn in green and blue variants
    * Contain blue foliage and skyroot wood
* Overworld earthslime islands
    * Spawn in green and blue variants
    * Contain green foliage and greenheart wood
* Clay islands
    * Weird idea, want to develop a bit more later
* Blood slime islands
    * Spawn in the nether
    * Contain ichor and blood
    * Contains bloodshrooms
* Necrotic bones
    * Drop from wither skeletons
* Enderslime islands
    * Contain ender slime
    * Currently no mobs
    * Temporary second home of greenheart wood

### Book

* Materials and You
    * Mostly complete, apart from new info in later editions
    * Has full list of tier 1 materials and traits
    * Has a modifier listing, though a few modifiers will be moved to puny smelting later
* Puny Smelting
    * Has full list of tier 2 materials and traits
* Mighty Smelting
    * Has full list of tier 3 materials and traits
* Fantastic Foundry
    * Has full list of tier 4 materials and traits
    * Has information on how to obtain molten blaze
* Encyclopedia of Materials
    * Has a full list of tier 1 through 4 materials
* Tinkers Gadgetry
    * Placeholder book for future documentation

## Next Alpha

### Tools

**Data packs**

* Support tagged fluids in materials, possibly via recipes

**Tools**

* Dagger

**Modifiers**

* Padded
    * Reduces tool knockback
* Duel Wielding
    * Similar to the daggers ability, but for any tool
* Draconic
    * Can now be crafted using dragon scales as an alternative to dragon heads

### Misc

* Library cleanup (remove unused code, repackaging, a couple class renames)

## Before beta

This section contains features that we want done before the first beta release, as it will ensure the mod is mostly stable moving on. After the first beta release, the API should remain stable, so making addons will be a lot easier.

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

### Resources

**Worldgen**

* Update ender slime island foliage to a chorus like plant

### Tools

**Tool types**

* Shield
* Battle Sign
* Armor

**Materials**

* Tier 1: Chorus
* Tier 2: End Stone
* Tier 3: Dragonstone, Hollow
* Tier 4: Soulsteel
* Tier 5: KnightSlime, Ebonite, Alexandrite

**Modifiers**

* Mending
    * New general ability
    * Requires something from the end to craft
    * Tool repairs on XP pickup
* Blocking
    * Battle sign ability as a modifier
    * If used on a battle sign, upgrades to full blocking like shields
* Armor modifiers

### Data

* Find a good way to handle duplicate materials between mods. We just going to resort to conditions?
    * Might need to make recipes directly referencing materials automatically disable if the material is not found
* Texture generators

## Long term content

This section just describes some content that will be in the mod eventually, but is further off being done most likely.

### Smeltery

* Smeltery interface (possibly)
    * Allows accessing the UI fluid tank
    * Comparator signal for tank level
    * On pulse, switches fluid order (bottom to top? Top to bottom?)
* Sand casts: allow placing sand second?

### Crafting
**Multiblock**

* Soul Forge
    * Include new book or add to nether book
* End Smeltery (upside down/gasses)
* "Smeltery sandwich"

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
* Charge attack modifier

**Part Builder**

* Add part forge? the tier 3 version for crafting large parts
* Better sorting in UI

### Resources

**Worldgen**

* Ichor slimes and slime islands