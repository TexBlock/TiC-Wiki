This page is a summary of all the changes in Tinkers' Construct 3 for 1.16, compared to Tinkers' Construct 2 for 1.12. 1.16 is still an ongoing process, so this page will be updated periodically.

# World

This section discusses changes to the world module

## Ore Gen

* Tinkers one again provides copper ore.
    * Copper is the only overworld ore we add
* Ardite ore has been removed
    * Ardite will be available from a different crafting process
    * Manyullyn specificially is now alloyed from cobalt and molten debris (ancient debris)

## Slime Islands

* Magma slimes are annoyed by all the noise caused by piglins
    * They are planning to relocate to the nether ceiling
    * Magma slimes will live in reverse gravity islands
* Purple slimes islands got tired of the dumb blue slimes, so they migrated to the end
    * A new purple slime mob is likely to be found
    * Purple slimes are the most advanced of the slimes, some may even wear armor

# Tools

This page describes some of the new content related to tools mechanics, including parts, materials, and modifiers. later in the section it has a full list of tools planned for TiC 3.

## Tool Tables

**Improved part builder**

* Stencil table and part builder were merged into one block
* Instead of crafting patterns and using those, the part builder has a UI similar to the stone cutter to craft parts

## Materials

**Material tiers**

* Materials now come in more clearly defined tiers, and all are divided into general, weapon, tool, or special materials
* Tier 1:
    * Includes wood, stone, flint, and bone
* Tier 2
    * Includes iron, copper, slimewood, and seared stone
    * The emerald modifier will also upgrade a tool to tier 2
* Tier 3:
    * Includes nahuatl, slimesteel, tinker's bronze, pig iron, rose gold, and cobalt
    * The diamond modifier will also upgrade a tool to tier 3
* Tier 4:
    * Includes manyullyn, hepatizon, queen's slime, and soul steel.
    * The netherite modifier will also update a tool to tier 4
* In addition, there is a tier 5 planned for materials requiring end access

**Trait rebalancing**

* Tool traits are getting rebalanced
* All parts share the same trait, instead of heads often having unique traits
* Traits on average will be a bit weaker than 1.12 to prevent discouraging use of a tool due to trait
* Some traits from 1.12 will get moved to modifiers, and some new traits will be added
* More information to follow

**Stat updates**

* Handles reworked:
    * No longer have a flat durability boost
    * Have four multipliers: durability, attack speed, attack damage, and mining speed
    * Most materials only 2 multipliers set, though later game materials will set at most 3
* Bindings reworked:
    * Bindings no longer have any stats
    * Instead, the purpose of bindings are to let you choose the trait you wish without concern for material tiers

**Part Cleanup**

* Many parts that only got used once were removed in favor of reusing parts
* Currently, there are two tyoes of tool rods: small and tough, and two bindings: small and tough
* Sword guards are replaced with other parts, including tool rods, small plates, and bindings based on the sword
* Tool heads ideally will be used in at least two tools. For example, the axe head is used on the axe and the mattock

## Tools

Tools will be implemented in a few phases to allow development to be focused on framework between content additions. The following sections list those phases.

### Phase 1

These tools will be in the first alpha

* *Pickaxe*
* *Shovel*
* *Hand Axe*: Rebalanced to be closer to the vanilla axe, making it a viable weapon
* *Kama*: Gained the ability to hoe blocks
* *Broadsword*
* *Hammer*
* *Excavator*

### Phase 2

These tools will be added after the first alpha after the original tools get some testing

* *Lumber Axe*
* *Cleaver*
* *Scythe*
* *Mattock*

### Phase 3

Ranged tools take a bit more work, so are being delayed

* *Bows*
* *Crossbows*: Rebalancing to be closer to the vanilla crossbow
* *Boomerang*: New throwable weapon that returns after throwing
* *Trident*: High reach melee/ranged hybrid

### Other likely tools

These tools need a bit more design work before I can reliably put them in a phase, so may be changed from what is described

* *Battle Sign*: Getting some reworking to be less effective to allow for proper shields
* *Shield*:
    * If we can make the battle sign unqiue enough on its own, a separate Tinkers Shield will be added
    * Possibility of limiting material selection to focus on shield modifiers, as many tool traits won't be helpful on shields
* *Rapier*
* *Battle Axe*

### Tinkers' Complement Tools

These tools are planned to be in the addon Tinkers' Complement, as they do not precisely fit in our tool tiers, but we liked them too much to abandon them. They will serve as examples of an addon adding new tools.

* *Frypan*: High knockback, low damage weapon
* *Knife*: Early game weapon with a light parry attack

### Removed Tools

These tools are not returning in Tinkers Construct 3.

* *Arrows*:
    * We cannot get the design for Tinkers arrows to work, and vanilla arrows are a lot more interesting now.
    * The way modifiers function (large material costs) conflicts with the idea of disposable ammmo
    * What you may see is the ability to craft custom arrows in the Tinker Station, otherwise some of the old trait effects will return as crafting table recipes
* *Bolts*:
    * Bolt crafting sucked, both in explaining to people and the mess of edge cases it caused in code
    * We don't see much need to keep separate ammo types when vanilla has arrows for both
    * Expect to be able to use fireworks on Tinkers' Construct crossbows as well.
* *Shurikens*
    * Shurikens had the same ammo problems as arrows and bolts
    * Being replaced with boomerangs (for a full Tinkers tool) or the new shuriken gadget (see the misc page)
* *Longswords*
    * Were basically a reskin of the sword with minor stat changes that most people just used for the leap ability
    * Leap returning as a slimesling variant
* *Longbows*
    * Were basically a reskin of the short bow with more expensive parts and slightly different stats
    * Cross bow is being declared the large version of the bow
    * Bow will have modifiers that make its stats closer to the longbows original stats

# Smeltery

This page is about new features related to the smeltery or smeltery mechanics

## New features

**Added the melter**

* Mini 2 block smeltery. Can run off solid or liquid fuel
* You may remember this from Tinkers' Complement
    
**Added sand casts**:

* Replace clay casts as the single use cast
* Blank cast can be crafted from sand
* Placing a blank cast in a casting table, then pressing a tool part in the top shapes the cast

**Added composite casting recipes**

* Composite materials are made by pouring a liquid on a solid toolpart of a different material
* One example is slimewood, from pouring liquid slime on wood

**New peripherals**
 
* Seared Ladder
    * Climbable seared block to prevent molten player
* Seared Chute
    * Smeltery item input and output
* Seared Duct
    * Filtered version of the seared drain

## Recipe changes

**Smeltery recipe changed**

* The smeltery controller now requires casting molten copper
* Seared drains inclue copper as part of their recipe
* These changes are to encourage use of the melter before jumping to a smeltery

**Changed seared stone recipe**

* Seared stone can no longer be obtained by melting down cobblestone
* Instead, seared stone can be casted from pouring molten clay on stone
* While this change does make giant smelteries more expensive, we have plans for a nether smeltery variant that will be easier to mass produce

## Mechanics

**Smeltery fuel consumption changed**

* Smeltery fuel consumption is now based on the number of blocks in the structure
    * This means building cube smelteries will be more fuel efficient than tall and thin structures
    * This also means smaller smelteries may be better if you don't need ton of fuel storage
* Smelteries now require fuel to melt entities and to alloy
    * This means a smeltery with no fuel can store liquids without accidently alloys
* Based on these changes, you might find it useful to make two smelteries:
    * One small one for melting and alloying
    * One large one for liquid storage

**Melting recipes improvements**

* Separated time from temperature
    * Temperature requirement remain consistent across a material, so if a fuel can melt nuggets it can melt ingots
    * Time varies based on fluid volume and a few other factors such as ores
* There are now three different fuel choices for melting
    * Solid fuels are only available in the melter, producing the lowest temperature of 800 C
    * Lava is back as the standard fuel of 1000 C
    * Molten Blaze is available from absorbing down blazes, granting up to 1500 C.
        * Note this is not blaze rods, its the actual blaze mob you must place in a smeltery
        
**Alloy improvements**

* Alloying now has a temperature property, so some recipes can require a hotter fuel

**Smeltery efficiency**

* All multiblock checking code for the smeltery got reviewed to improve the efficincny
* Smeltery structures should overall cause less lag from structure checks

# Other

This page discusses some of the new features that do not fit in any other section

## Additions

**Copper Cans**

* Fluid container that holds exactly 1 ingot of fluid
* Stackable up to 16

**Soul Glass**

* Nether clear glass varaiant
* Only available by casting

**Clear Glass Panes**

* Clear glass, stained clear glass, seared glass, and soul glass are all available as panes

**Better JEI support**

* Entity melting is now shown in JEI, along with the new recipe type for making sand casts

**Shurikens**

* Throwable item crafted from flint or quartz
* Single use, not a full Tinkers tool
* Intended to be disposable weapons to keep monsters at bay for an escape

## Recipes

* All recipes have beem moved to JSON, allowing them to easily be added using datapacks
* Some new recipe types exist
    * Castign recipes come in many variants
    * Molding recipes are the new recipe type for making sand casts

## Removals

**Wooden Hoppers**

* I (KnightMiner) does not really like wooden hoppers
* A lot of wooden hopper mods exist

**Content moved to Natura**

* The devs of Tinkers Construct and Natura discussed whether some content should be moved between mods
* It was decided that the following features would be moved to Natura:
    * Stone ladders and torches
    * Brownstone
    * Drying racks and jerky
    * Punji sticks
    
**Pink slime**

* Was the fallback for mixing slimes towards the end of 1.12.
* Decided it was a bit too awkward of a mechanic
* In 1.16, green slime is the fallback for mxing

**Tinker Tank**

* Moving to Tinkers' Complement
* The original design was based on the deep tank fron Tinkers' Steelworks. The other steelworks multiblock was added to Tinkers' Complement, so it makes sense to have them together
* The commonly used purpose of the tank, preventing accidental alloys, is now handled by a smeltery with no fuel.