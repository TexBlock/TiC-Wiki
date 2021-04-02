## Already Coded

The following subsections contain major features that are already coded, to give an idea of progress and what should be in the mod already

### Crafting
**Tool Tables**

* Part builder, tinker station, tinker's anvil
* Modifier chest, part chest, cast chest

**Smeltery**

* Melter
* Overworld smeltery
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
* Tier 3: tinkers' bronze, nahuatl, slimesteel, rose gold, pig iron, cobalt
* Tier 3 compat: Steel, bronze, constantan
* Tier 4: Queen's slime, hepatizon, manyullyn

**Modifiers**

* Free: Worldbound, Overslime, Creative
    * Bonus modifiers: book and quill, music disc, mob head, end crystal
* Upgrades: Reinforced, Experienced, Magnetic, Necrotic, Knockback, Haste, Fiery
    * Damage boost: Sharpness, Smite, Bane of Arthropods, Antiaquatic, Cooling
    * Tier modifiers: Emerald, Diamond, Netherite
* Abilities: Silk Touch, Expanded, Luck, Gilded

### Resources

**Worldgen**

* Fully implemented
    * Overworld slime islands
    * Blood slime islands
    * Copper ore
    * Cobalt ore
    * Wither bones
* Partially implemented
    * End slime islands (wrong flora, missing mobs)

## Phase 2

Phase 2 consists of content I did not consider essential to the first public alpha. Some of this may still get pulled into the first alpha, but in general expect this content after the first alpha.

### Documentation

**Datapacks**

* Document material creation

**Book**

* Materials and You content
    * Tool tables
    * Information on tier 1 materials
    * Modifier information (minus nether access)
* Mighty Smelting
    * Melter
    * Tier 2 materials
    * Smeltery
    * Tier 3 materials
* Mystic Melting (title pending)
    * Alloy tank
    * Nether smeltery
    * Tier 1-3 nether materials
    * Tier 4 nether materials

### Crafting

**Smeltery**

* Heaters in smeltery?
* Nether smeltery
* Multi-output recipes
* Smeltery peripheral to access the UI?
* Sand casts: allow placing sand second?
* Fix smeltery transparent fluids

### Tools

**Data packs**

* Tool art listing in JSON?
* Support tagged fluids in materials
* Trait manager cleanup

**Part Builder**

* Add leftovers slot
* Cleanup behavior to be more like the tinker station
* Add part forge, the tier 3 version for crafting large parts

**Tool types**

* Small:
    * Kama fixes:
        * Right click harvest
        * Pumpkin and bee hive shearing
        * Trip wire disfusing
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
* Content transfer:
    * Wooden rails move to Tinkers' Mechworks, piggybackpacks too?
    * Jerky, stone ladders and torches, punji sticks, and dried clay move to Natura

## Phase 3

Phase 3 is the point at which I consider the mod's API ready to use. Before this phase, any addons need to be prepared to update as we make new alphas as our API needs a lot of cleanup from 1.12. Once the first beta is released, the API should remain stable.

### Crafting
**Multiblock**

* Soul Forge
    * Include new book or add to nether book
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