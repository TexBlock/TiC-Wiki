## Next Alpha

### Materials

* Adjusted sort orders of many materials to leave more room for addon materials
* Made bloodbone deal slightly more damage to better align with tier 2 materials
* Made Cobalt and steel a bit more distinct by giving steel more attack to cobalts mining speed
* Constantan now has stats closer to tier 3 harvest materials
* Seared stone buffed to have more durability

### Material Compatibility

* Added osmium as a tier 2 general material
* Added tungsten and platinum as tier 2 harvest materials
* Added whitestone as a tier 2 special composite using aluminum, tin, or zinc
* Added invar as a tier 3 weapon material
* Added necronium as a tier 3 weapon composite using uranium and necrotic bones
* Added plated slimewood as a tier 3 special material using brass and slimewood

### Smeltery Compatibility

* Immersive Engineering: Added wire cast and wire casting
* Mekanism: Added melting, casting, and composite recipes for for refined obsidian and refined glowstone, along with alloying for refined obsidian
* Thermal: Added melting, casting, and alloying for lumium, enderium, and signalum

### Data

* Added new command to list all modifiers and whether they are used in recipes or traits

### API

* Added material render info data generator
* Added new `IModifierRecipe` interface for compatibility with the new command in dynamic recipes, it is the parent interface of `IDisplayModifierRecipe`
* Material based recipes that fail to find the material now hide in JEI and always fail

## Before beta

This section contains features that we want done before the final 1.16 update, and before the mod is marked as beta. It will ensure the mod is mostly stable moving on. After the first beta release, the API should remain stable, so making addons will be a lot easier.

### Documentation

**Datapacks**

* Document material creation



### Resources

**Worldgen**

* Update ender slime island foliage to a chorus like plant

### Tools

**Tool types**

* Armor

**Possible tool types**

Tools that I would like to include, but may not make it

* Bows/crossbows
* Shield
* Battle Sign

**Materials**

* Tier 1: Chorus
* Tier 2: End Stone
* Tier 2 compat: Whitestone (aluminum/tin/zinc + seared stone composite)
* Tier 2 compat: Necronium (uranium + necrotic bones)
* Tier 2 compat: Tungsten, Platinum, Osmium (need to consider a bit more on all 3)
* Tier 3 compat: Plated Slimewood (brass + slimewood)
* Tier 3 compat: Invar

**Modifiers**

* Armor modifiers
* Mending
    * New general ability
    * Requires something from the end to craft, or maybe soul forge
    * Tool repairs on XP pickup
* Blocking
    * Battle sign ability as a modifier
    * If used on a battle sign, upgrades to full blocking like shields

### Data

* Make material redirects save to NBT
* Texture generators

### Compat

* Immersive Engineering compat between spilling and chemical thrower

## Long term content

This section just describes some content that will be in the mod eventually, but is further off being done. Most of this content will not be included until 1.17+.

### Smeltery

* Smeltery interface (possibly)
    * Allows accessing the UI fluid tank
    * Comparator signal for tank level
    * On pulse, switches fluid order (bottom to top? Top to bottom?)

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