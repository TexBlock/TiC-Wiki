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

* Small: broadsword, dagger
    * Harvest: pickaxe, mattock, axe, kama
* Large: cleaver
    * Harvest: sledge hammer, vein hammer, broad axe, excavator, scythe

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
* Upgrades: Reinforced, Experienced, Magnetic, Soulbound, Tank, Overforced, Offhanded
    * Harvest: Haste, Blasting, Lightspeed, Hydraulic 
    * Weapon: Beheading, Necrotic, Knockback, Padded, Fiery, Sweeping Edge
    * Damage boost: Sharpness, Smite, Bane of Arthropods, Antiaquatic, Cooling
    * Tier modifiers: Emerald, Diamond, Netherite
* Abilities: Gilded, Bucketing, Glowing, Unbreakable
    * Range: Expanded, Reach
    * Loot: Silk Touch, Luck, Autosmelt
    * Weapon: Dual Wielding, Melting
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
    * Contains bloodshrooms, a nether like slime tree
* Necrotic bones
    * Drop from wither skeletons
* Enderslime islands
    * Contain ender slime
    * Currently no mobs
    * Temporary second home of greenheart wood

### Book

* Materials and You
    * Has full list of tier 1 materials and traits
    * Describes how to start the mod through tables and tool crafting
* Puny Smelting
    * Has full list of tier 2 materials and traits
    * Has an upgrade and slotless modifier listing
    * Describes basic fluid transfer, melting, and casting
* Mighty Smelting
    * Has full list of tier 3 materials and traits
    * Has an ability modifier listing
    * Describes smeltery creation and alloying
    * Lists broad tools and discusses creation of the anvil
* Fantastic Foundry
    * Has full list of tier 4 materials and traits
    * Has information on how to obtain molten blaze
    * Discusses creating the foundry and the alloyer
* Encyclopedia of Materials
    * Has a full list of tier 1 through 4 materials
    * Has a list of all upgrades, abilities, and slotless modifiers with detailed information
    * Has a full list of tools, detailing stats and special abilities
* Tinkers Gadgetry
    * Placeholder book for future documentation


## Before beta

This section contains features that we want done before the first beta release, as it will ensure the mod is mostly stable moving on. After the first beta release, the API should remain stable, so making addons will be a lot easier.

### Documentation

**Datapacks**

* Document material creation

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
* Tier 4: Some composite using molten diamond

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
    * A way to redirect an old material ID to a new one would be good, textures support it
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

**Materials**

* Tier 3: Dragonstone, Hollow
* Tier 4: Soulsteel
* Tier 5: KnightSlime, Ebonite, Alexandrite

**Part Builder**

* Add part forge? the tier 3 version for crafting large parts
* Better sorting in UI

### Resources

**Worldgen**

* Ichor slimes and slime islands