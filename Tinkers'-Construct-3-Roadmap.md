## Already Coded

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
    * Large: hammer
* Partially implemented:
    * Small: kama (missing harvest)
    * Large: excavator (missing knockback bonus)

**Materials**

* Fully implemented
    * Tier 1: Wood, stone, flint, bone
    * Tier 2: Iron, copper, seared stone, slimewood
    * Tier 2 compat: Lead, silver, electrum
    * Tier 3: tinkers' bronze, nahuatl, slimesteel, Rose Gold, Pig Iron, Cobalt
    * Tier 3 compat: Steel, Bronze
    * Tier 4: Queen's Slime
* Has stats and recipe, no traits
    * Tier 3 compat: constantan
    * Tier 4: Manyullyn, Hepatizon, Soulsteel

**Modifiers**

* Free: Worldbound
    * Bonus modifiers: book and quill, music disc, mob head
* Upgrades: Reinforced, Experienced, Magnetic
    * Tier modifiers: emerald, diamond, netherite
* Abilities: Silk Touch, Expanded

### Resources

**Worldgen**

* Fully implemented
    * Overworld slime islands
    * Copper ore
    * Cobalt ore
* Partially implemented
    * End slime islands (wrong flora, missing mobs)

## Phase 1 (first alpha)

**Materials**

* Finish missing traits: constantan, manyullyn, hetatizon

**Modifiers**

* JEI recipe support
* Upgrades: Necrotic
    * Incremental: Haste, Sharpness, Smite, Bane of Arthropods, Antiaquatic, Fiery
* Abilities:
    * Incremental: Luck

### Cleanup

**Required**

* Rework tool model
* Trivial:
    * Copper oregen rate too high
    * Validate recipe tags, any tags we should be using
        * Darkosto reported crafting station does not use workbench tag
    * Table TESR render box
* Remapping items:
    * Toolpart cleanup (ditch large binding, excavator head to plate)
    * Rename slime types for consistency, either colors or flavor names
    * Rename hammer to sledgehammer

**Possibly delayed to phase 2**

* Fix smeltery transparent fluids
* AOE tool improvement
* Large tool model
* Trait manager cleanup
* Datapack material removal

## Phase 2 (incremental content)

### Crafting

**Tool tables**

* Part builder leftover slot
* Tinkers' Anvil

**Smeltery**

* Heaters in smeltery?
* Nether smeltery
* Multioutput recipes

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

### Resources 
**Worldgen**

* Ender slimes and foliage
* Better sky slimes

### Misc

* Texture generators

## Phase 3 (beta release, endgame content)

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

## Phase 4 (complex content)

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