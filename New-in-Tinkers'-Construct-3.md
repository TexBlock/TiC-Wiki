This page is a summary of all the changes in Tinkers' Construct 3 for 1.16, compared to Tinkers' Construct 2 for 1.12. 1.16 is still an ongoing process, so this page will be updated periodically.

# World

This section discusses changes to the world module

## Ore Gen

* Tinkers once again provides copper ore.
    * Copper is the only overworld ore we add.
* Ardite ore has been removed
    * Potentially moved to Natura, otherwise just removed entirely
    * Manyullyn specifically is now alloyed from cobalt and molten debris (ancient debris)

## Slime Islands

* Orange slimes are annoyed by all the noise caused by piglins
    * They are planning to relocate to the nether ceiling
    * Orange slimes will live in reverse gravity islands
* Purple slimes islands got tired of the dumb blue slimes, so they migrated to the end
    * A new purple slime mob is likely to be found
    * Purple slimes are the most advanced of the slimes, some may even wear armor
* All slime types have unique names
    * Green slime is often called earth slime, or just generically slime
    * Blue slime is called sky slime
    * Orange slime is called ichor
    * Purple slime is called ender slime
    * Magma cream is often considered a fifth slime type

# Tools

This page describes some of the new content related to tools mechanics, including parts, materials, and modifiers. later in the section it has a full list of tools planned for Tinkers' Construct 3.

## Tool Tables

**Improved part builder**

* Stencil table and part builder were merged into one block
* Instead of crafting patterns and using those, the part builder has a UI similar to the stone cutter to craft parts
* Crafted from 2 patterns and 2 wooden planks

**Improved tinkering**

* Tinker Station
    * New name for the tool station
    * Has only 3 slots (no crafting large tools), and a similar UI to the classic 1.7 UI
    * Tool station is crafted using 4 planks and 3 patterns
* Reworked Tool Forge into Tinker's Anvil
    * Simply sounds cooler
    * Contains 5 slots, like the 1.12 UI
    * Recipe requires 3 metal blocks and 4 seared bricks

**Improved Crafting Station**

* Can be crafted from a pattern and either a crafting station or any wooden table
* Alternatively, can be crafted from a pattern and a log to use the log texture on the legs

**Improved station tabs**

* Any two station blocks together will now form tabs, instead of requiring a crafting station
* Multiple of the same block can be tabs, for example placing 2 crafting stations together gives tabs to switch between them

## Materials

**Material tiers**

* Materials now come in more clearly defined tiers, and all are divided into general, weapon, harvest, or special materials
* Tier 1:
    * Starting tool tier
    * Includes wood, stone, flint, and bone
    * In the end, this tier consists of chorus
* Tier 2
    * Requires ores or the melter to obtain materials
    * Includes iron, copper, slimewood, and seared stone
    * In the nether, this tier includes scorched stone
    * In the end, this tier includes end stone
    * The emerald modifier will also upgrade a tool to tier 2
* Tier 3:
    * Requires alloying to obtain materials
    * Includes nahuatl, slimesteel, tinker's bronze, pig iron, and rose gold
    * In the nether, this tier includes cobalt
    * In the end, this tier includes dragonstone
    * The diamond modifier will also upgrade a tool to tier 3
* Tier 4:
    * Requires nether access to obtain materials
    * Includes manyullyn, hepatizon, queen's slime, and soul steel
    * In the end, this tier includes slimebronze
    * The netherite modifier will also upgrade a tool to tier 4, requires either the diamond or emerald modifier
* Tier 5:
    * Requires end access to obtain materials
    * Includes KnightSlime, Ebonite, and Alexandrite
    * The Gardite modifier will also upgrade a tool to tier 5, requires either netherite or worldbound

**Stat updates**

* Handles reworked:
    * No longer have a flat durability boost
    * Have 4 multipliers: durability, attack speed, attack damage, and mining speed
    * Most materials only 2 multipliers set, though later game materials will set at most 3
* Bindings reworked:
    * Bindings no longer have any stats
    * Instead, the purpose of bindings are to let you choose the trait you wish without concern for material tiers

**Part Cleanup**

* Many parts that only got used once were removed in favor of reusing parts
* Currently, there are two types of tool rods: small and tough, and two bindings: small and tough
* Sword guards are replaced with other parts, including tool rods, small plates, and bindings based on the sword
* Tool heads ideally will be used in at least two tools. For example, the axe head is used on the axe and the mattock

## Modifiers

**Modifier types**

* Modifiers are now divided into 5 categories:
    * *Upgrades*: Classic modifiers common to TiC 1 and TiC 2. Requires upgrade slots
    * *Abilities*: Stronger and more unique modifiers, such as silk touch or luck. Requires ability slots
    * *Armor*: Special modifier type available on armor or shields
    * *Free*: Modifiers that can be applied without any slot restriction
    * *Traits*: Additional modifiers applied based on the materials

**Trait rebalancing**

* Tool traits are getting rebalanced
* All parts share the same trait, instead of heads often having unique traits
* Traits on average will be a bit weaker than 1.12 to prevent discouraging use of a material due to trait
* Some traits from 1.12 will get moved to modifiers, and some new traits will be added
* More information to follow

## Tools

### Small

These tools are available from tier 1 and onwards.

* *Pickaxe*
* *Mattock*:
    * Makes paths instead of hoeing, effective on all blocks the shovel could break.
    * Replaces the shovel in TiC 3.
* *Hand Axe*: Rebalanced to be closer to the vanilla axe, making it a viable weapon
* *Kama*: Gained the ability to hoe blocks, making it a fully effective farming tool
* *Broadsword*
* *Dagger*: Fast weapon with low damage, but can attack on right click for use in the offhand.

### Broad

These tools require the Tinker's Anvil to craft, a tier 3 component. Tool part will make use of the Part Forge.

* *Sledgehammer*
* *Veining Hammer*: Breaks a vein of ores, name pending.
* *Excavator*
* *Broad Axe*: New version of the lumber axe. Fallback for non-trees is now 1x6, also acts as a battle axe
* *Cleaver*
* *Scythe*

### Armor

Armor has some different rules for how modifiers apply. With the exception of the battle sign, all armor is a crafting station recipe with only one "part".

* *Battle Sign*: Getting some reworking to be less effective to allow for proper shields
* *Shield*: Added as a single type modifiable item, similar to armor.
* *Armor*: Available in three sets: travelers, plate, and slime suit. One recipe instead of variable materials, to allow more focus on modifiers.

### Ranged

These weapons make use of drawspeed and projectile behavior

* *Bows*
* *Crossbows*: Rebalancing to be closer to the vanilla crossbow
* *Boomerang*: New throwable weapon that returns after throwing
* *Spear*: High reach melee/ranged hybrid (takes role of vanilla trident)

### Tinkers' Complement Tools

These tools are planned to be in the addon Tinkers' Complement, as they do not precisely fit in our tool tiers, but we liked them too much to abandon them. They will serve as examples of an addon adding new tools.

* *Frypan*: High knockback, low damage weapon
* *Rapier*: Fast weapon with armor pierce

### Removed Tools

These tools are not returning in Tinkers Construct 3.

* *Arrows*:
    * We cannot get the design for Tinkers arrows to work, and vanilla arrows are a lot more interesting now.
    * The way modifiers function (large material costs) conflicts with the idea of disposable ammo
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
    * Leap returning as a slime sling variant
* *Longbows*
    * Were basically a reskin of the short bow with more expensive parts and slightly different stats
    * Cross bow is being declared the large version of the bow
    * Bow will have modifiers that make its stats closer to the longbows original stats

# Multiblocks

This section is about new features related to the smeltery or smeltery mechanics, and also other multiblocks

## New features

**Added the melter**

* Mini 2 block smeltery. Can run off solid or liquid fuel
* You may remember this from Tinkers' Complement
    
**Added sand casts**:

* Replace clay casts as the single use cast
* Blank cast can be crafted from sand
* Placing a blank cast in a casting table, then pressing a tool part in the top shapes the cast

**Added composite casting recipes**

* Composite materials are made by pouring a liquid on a solid tool part of a different material
* One example is slimewood, from pouring liquid slime on wood

**New peripherals**
 
* Seared Ladder
    * Climbable seared block to prevent molten player
* Seared Chute
    * Smeltery item input and output
* Seared Duct
    * Filtered version of the seared drain
* Gravity Peripheral (name pending)
    * End tier peripheral
    * Allows the smeltery to hold gasses, or the end smeltery to hold liquids
    * Placed in the smeltery floor

**Smeltery variants**

* New nether smeltery planned
    * Aids in nether survival, crafted from basalt/gravel, magma cream, and soul sand
    * Has some small differences from the overworld smeltery
* New end smeltery planned
    * Built upside down, because why not?
    * Only can hold gasses, no liquids
    * See gravity peripheral to give liquid support

## Recipe changes

**Smeltery recipe changed**

* The smeltery controller now requires casting molten copper
* Seared drains include copper as part of their recipe
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

* All multiblock checking code for the smeltery got reviewed to improve the efficiency
* Smeltery structures should overall cause less lag from structure checks

## Soul Forge

* New multiblock
* Forges souls
* More info to follow

# Other

This page discusses some of the new features that do not fit in any other section

## Additions

**Copper Cans**

* Fluid container that holds exactly 1 ingot of fluid
* Stackable up to 16

**Soul Glass**

* Nether clear glass variant
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

* All recipes have been moved to JSON, allowing them to easily be added using data packs
* Some new recipe types exist
    * Castin recipes come in many variants
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
* In 1.16, green slime is the fallback for mixing

**Tinker Tank**

* Moving to Tinkers' Complement
* The original design was based on the deep tank from Tinkers' Steelworks. The other steelworks multiblock was added to Tinkers' Complement, so it makes sense to have them together
* The commonly used purpose of the tank, preventing accidental alloys, is now handled by a smeltery with no fuel.