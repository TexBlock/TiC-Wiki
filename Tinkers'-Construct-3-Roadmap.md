## Next Alpha

### Materials

#### Added

The following materials are new binding exclusive materials. This means they provide no stats, but do provide some unique traits

* Added leather, string, and vines as tier 1 materials. All have traits related to durability
* Added chain and skyslime vine as tier 2 materials. Chain is a durability related trait, while skyslime vines are harvest
* Added enderslime vines as a "tier 4" material, with a harvest/melee trait

The following materials require another mod to provide certain ores for them to show.

* Added osmium as a tier 2 general material
* Added tungsten and platinum as tier 2 harvest materials
* Added whitestone as a tier 2 special composite using aluminum, tin, or zinc
* Added invar as a tier 3 weapon material
* Added necronium as a tier 3 weapon composite using uranium and necrotic bones
* Added plated slimewood as a tier 3 special material using brass and slimewood

#### Changes

* Adjusted sort orders of many materials to leave more room for addon materials
* Made bloodbone deal slightly more damage to better align with tier 2 materials
* Made cobalt and steel a bit more distinct by giving steel more attack to cobalts mining speed
* Constantan now has stats closer to tier 3 harvest materials
* Seared stone buffed to have more durability
* Material redirects now save to tool NBT, which should both be slightly more efficient and give the option to remove redirects for cleanup later

### Tools

* Blood and pig iron now restore hunger when used as a spilling effect, for the sake of future shenanigans
* Broad axes now use a binding instead of the large plate in the recipe

### Smeltery

* Gold now always gives a byproduct of copper, instead of giving silver if present. This provides a source of copper in the nether
* Smeltery debug block border now shows from smeltery building blocks instead of manuals, should make the reason more clear

#### Compatibility

* Immersive Engineering: Added wire cast and wire casting
* Mekanism: Added melting, casting, and composite recipes for for refined obsidian and refined glowstone, along with alloying for refined obsidian
* Thermal: Added melting, casting, and alloying for lumium, enderium, and signalum

### Textures

* All materials now have unique textures with proper palettes due to texture generators, instead of using the tint fallback. Means much better contrast on textures (thanks RCXcrafter for palettes and the original bases)
* New nahuatl texture to match the new part palette
* New queens slime textures (thanks LethalChicken)

### Misc

* JEI: improved rendering of custom ingredient types, now show IDs on F3+H and all ingredients render properly in bookmarks
* Fix a duplication bug in part builders related to changing stack sizes of the input
* Fix cleared glass not being accepted by many vanilla recipes.
    * As a note for modpack makers, this fix was implemented by registering a second copy of those recipes.
    * A config option is provided to disable this fix in case you change the recipes (or you can use a datapack to remove our copies of the recipes)
* Fix many small book errors
* Fix JEI not showing stack sizes for part builder recipe inputs
* Fix materials with no relevant stats showing in the book lists

### Data

* Added new command to list all modifiers and whether they are used in recipes or traits
* Tool definitions are now defined in datapacks
* Tinker Station slot layouts are now defined in datapacks instead of resource packs, and have a bit more functionality. In addition, they are now separated from tools, so custom layouts can be more easily added
* The book no longer shows tools with invalid material combinations
* Added texture generators, specifically generators for material variants of part textures
    * Currently just implement repaletting a base texture, but the system has enough flexibility that the other methods can be brought back

### API

* Added material render info data generator
* Added tool defintion and tinker station slot layout data generators
* Added new `IModifierRecipe` interface for compatibility with the new command in dynamic recipes, it is the parent interface of `IDisplayModifierRecipe`
* Material based recipes that fail to find the material now hide in JEI and always fail
* All relevant teleports now fire a subclass of the forge `EntityTeleportedEvent` so other mods can cancel or modify teleports
* Modifier tool damage hook now has an entity parameter. It is nullable, but in most cases it should be non-null

#### Breaking changes

* Tool defintion build is now done through datapacks, so the old builders no longer exist. There was no clean way to keep the old builds and migrate to datapacks
    * Code calling methods on tool defintions should still work, though many old methods are deprecated
* The old Tinker Station Slot layout logic was removed, so JSON added for slots will no longer work
    * There are no breaking changes in code as all the related classes were not in the API

## Before beta

This section contains features that we want done before the final 1.16 update, and before the mod is marked as beta. It will ensure the mod is mostly stable moving on. After the first beta release, the API should remain stable, so making addons will be a lot easier.

### Documentation

**Datapacks**

* Document material creation
* Verify which recipe formats are documented so far

### Resources

**Worldgen**

* Update ender slime island foliage to a chorus like plant
* Added purple end slimewood variant. No logs, just planks will be available

### Tools

**Tool types**

* Armor

**Possible tool types**

Tools that I would like to include, but may not make it before the first beta

* Bows/crossbows
* Shield
* Battle Sign

**Materials**

* Tier 1: Chorus
* Tier 2: End Stone

**Modifiers**

* Armor modifiers
* Mending
    * New general ability
    * Requires something from the end to craft, or maybe soul forge
    * Tool repairs on XP pickup
* Blocking
    * Battle sign ability as a modifier
    * If used on a battle sign, upgrades to full blocking like shields

### Smeltery

* Ability to pour non-forge fluid containers into tanks and drains
    * Implement using a datapack registry (possibly recipes) to produce a mapping from itemstack to fluid + container.
    * Possibly allow the inverse, or leave that to datapacks.

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