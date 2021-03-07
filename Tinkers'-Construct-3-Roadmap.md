## Already Coded

The following subsections contain major features that are already coded, to give an idea of progress and what should be in the mod already

### Crafting
**Tool Tables**

* Part builder, tinker station

**Smeltery**

* Overworld variant
* Melter
* Drain, chute, duct
* Tanks
* Faucets, channels
* Casting table and basin
* Melting, alloying, entity melting

### Tools

**Tool types**

* Fully implemented
    * Small: Pickaxe, mattock, axe, broadsword
    * Large: hammer, excavator
* Partially implemented:
    * Small: kama (missing harvest)

**Materials**

* Tier 1: Wood, stone, flint, bone
* Tier 2: Iron, copper, seared stone, slimewood
* Tier 2 compat: Lead, silver, electrum
* Tier 3: tinkers' bronze, nahuatl, slimesteel, Rose Gold, Pig Iron, Cobalt
* Tier 3 compat: Steel, Bronze, Constantan
* Tier 4: Queen's Slime, Hepatizon, Manyullyn

**Modifiers**

* Free: Worldbound, Overslime, Creative
    * Bonus modifiers: book and quill, music disc, mob head
* Upgrades: Reinforced, Experienced, Magnetic, Knockback
    * Tier modifiers: Emerald, Diamond, Netherite
* Abilities: Silk Touch, Expanded

### Resources

**Worldgen**

* Fully implemented
    * Overworld slime islands
    * Copper ore
    * Cobalt ore
* Partially implemented
    * End slime islands (wrong flora, missing mobs)

## Phase 1

Phase 1 consists of all the code from the time we started working in 1.15 until the first public alpha. The following subsections contain things I need to complete before that first public alpha. When released, it will conclude phase 1.

### Tools

**Modifiers**

* Upgrades: Necrotic
    * Incremental: Haste, Sharpness, Smite, Bane of Arthropods, Antiaquatic, Fiery
* Abilities: Luck

### Tables

These changes are not specifically required for the first alpha, but have a few other reasons for inclusion

**Part Builder**

* Add leftovers slot
* Cleanup behavior to be more like the tinker station, should fix a dupe bug
* Add part forge, the tier 3 version for crafting large parts

**Tinker Anvil**

* Trivial to implement block

**Modifier Chest**

* Broken model
* Clean up code, probably pull from modifier recipe inputs

### Cleanup

**Required**

* Trivial:
    * Cleanup config file
* Content transfer:
    * Piggybackpack move to Tinkers' Mechworks
    * Jerky, stone ladders and torches, punji sticks, and dried clay move to Natura
* Remapping items:
    * Toolpart cleanup (ditch large binding, excavator head to plate)
    * Rename slime types for consistency, either colors or flavor names
    * Rename hammer to sledgehammer
* Unused Content:
    * Remove graveyard and consecrated soil, modifier recipes changed

**Possibly delayed to phase 2**

* Fix smeltery transparent fluids
* AOE tool improvement
* Trait manager cleanup
* Way to obtain magma/ichor slime. Probably drop from magma cubes for now
* Support tagged fluids in materials
* Head swapping should repair the tool

## Phase 2

Phase 2 consists of content I did not consider essential to the first public alpha. Some of this may still get pulled into the first alpha, but in general expect this content after the first alpha.

### Crafting

**Smeltery**

* Heaters in smeltery?
* Nether smeltery
* Multioutput recipes
* Smeltery peripheral to access the UI?
* Sand casts, allow sand second?

### Tools

**Building**

* Tool part factor: allow some parts to be worth more in stats (hammer heads vs plates)
* Tool building in JSON

**Tool types**

* Small:
    * Kama right click harvest
    * Dagger
* Large: Broad Axe, Cleaver, Scythe, Veining Hammer

**Modifiers**

* Upgrades: Knockback, Necrotic, Glowing, Soulbound, Reach
* Abilities: Autosmelt, Beheading, Mending, Ability Boost
* Nether bonus modifiers

**Tool Model**

* Broken part support
* Large tool model
* Modifier models

### Resources

**Worldgen**

* Ender slimes and foliage
* Better sky slimes

### Misc

* Texture generators
* Find a good way to handle duplicate materials between mods. We just going to resort to conditions?
    * Might need to make recipes directly referencing materials automatically disable if the material is not found

## Phase 3

Phase 3 is the point at which I consider the mod's API ready to use. Before this phase, any addons need to be prepared to update as we make new alphas as our API needs a lot of cleanup from 1.12. Once the first beta is released, the API should remain stable.

### Crafting
**Multiblock**

* Soul Forge
* End Smeltery (upside down/gasses)
* Gravity smeltery peripheral

### Tools

**Tool types**

* Battle sign
* Shield
* Armor

**Materials**

* Tier 1: Chorus
* Tier 2: End Stone
* Tier 3: Dragonstone, Hollow
* Tier 4: Slimebronze, Soulsteel
* Tier 5: KnightSlime, Ebonite, Alexandrite

**Modifiers**

* Abilities: Unbreakable
* End bonus modifiers
* Armor modifiers

### Resources

**Worldgen**

* Bloodwood trees?
* Ichor slimes and slime islands

### Cleanup

* Library cleanup (remove unused code)
* StatsNBT builder to make stats more extendable

## Phase 4

Phase 4 is similar to phase 2, its simply content that is planned for the mod but not required for the first beta. After the requirements of this phase are satisfied the mod will be ready for full release status, however the mod should be mostly playable during phase 2 or 3.

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