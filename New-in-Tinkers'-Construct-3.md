This page is a summary of all the changes in Tinkers' Construct 3 for 1.16, compared to Tinkers' Construct 2 for 1.12. 1.16 is still an ongoing process, so this page will be updated periodically.

Note that not everything on this page is fully implemented. For information about implemented features, see [the roadmap](https://github.com/SlimeKnights/TinkersConstruct/wiki/Tinkers%27-Construct-3-Roadmap).

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

**[World](#world)**
* [Ore Gen](#ore-gen)
* [Slime Islands](#slime-islands)

**[Tools](#tools)**
* [Tool Tables](#tool-tables)
* [Materials](#materials)
* [Modifiers](#modifiers)
* [Tools](#tools-1)
  + [Small](#small)
  + [Broad](#broad)
  + [Armor](#armor)
  + [Ranged](#ranged)
  + [Tinkers' Complement Tools](#tinkers--complement-tools)
  + [Removed Tools](#removed-tools)

**[Multiblocks](#multiblocks)**
* [New features](#new-features)
* [Recipe changes](#recipe-changes)
* [Mechanics](#mechanics)
* [Soul Forge](#soul-forge)

**[Other](#other)**
* [Additions](#additions)
* [Recipes](#recipes)
* [Removals](#removals)
  </td>
</table>

# World

This section discusses changes to the world module

## Ore Gen

* Tinkers once again provides copper ore
    * Copper is the only overworld ore we add
* Cobalt ore returns
    * Instead of just alloying into manyullyn, cobalt has a few more alloys now
    * Cobalt is also used in crafting some special smeltery components
* Ardite ore has been removed
    * Potentially moved to Natura, but not used in Tinkers in either case
    * Manyullyn specifically is now alloyed from cobalt and molten debris (ancient debris)

## Slime Islands

* All slime types have unique names
    * Green slime is often called earth slime, or just generically slime (vanilla)
    * Blue slime is called sky slime
    * Orange slime is called ichor
    * Purple slime is called ender slime
    * Magma cream is often considered a fifth slime type, so is blood
* New earth slime islands
    * Spawn in the overworld ocean
    * Loaded with earth slimes (vanilla slimes) and the new greenheart slimy trees
    * Spawn in blue or green dirt variants, all types with green foliage
* Sky slime islands
    * Spawn in the sky as before, though probably a bit less commonly
    * Congealed slime trees replaced with new skyroot slimy wood tree
    * Spawn in blue or green dirt variants, all types with blue foliage
    * Sky slimes have overcome their weakness of falling off the island by bouncing
* Nether slime islands renamed to blood islands
    * Spawn with orange dirt and red foliage
    * "Trees" are called bloodshrooms, a huge fungus variant obtained from red slimy nylium
    * Bloodshrooms grow ichor instead of shroomlights
    * Remain a good source of magma cubes, now including a lake of liquid magma cream
* New ichor slime islands
    * Planned to appear as part of the nether ceiling, not yet implemented
    * Ichor slimes will live in reverse gravity with their upside down trees and stuff
* Purple slimes islands got tired of the dumb blue slimes, so they migrated to the end to start their own society
    * They actually prefer the name enderslime now
    * Enderslime mobs can be found now, who teleport for attacking and defense
    * Enderslimes are the most advanced of the slimes, some may even wear armor in the future
* Slimy Saplings
    * As mentioned earlier, saplings now have slimy wood instead of congealed slime for the stems
    * Slimy wood has a hard outer bark layer and a squishy inner slimy wood layer, meaning the effective tool changes when stripping
    * Slimeballs are still dropped from the leaves, except on bloodshrooms, where slime generates in place of shroomlights
    * Slimy saplings can now be melted in a smeltery for liquid slime of the proper type
* Clay Islands
    * Slime island variant spawning with normal grass
    * Lake filled with clay and sand


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
    * Recipe requires 3 metal alloy blocks and 4 seared bricks
* Renaming tools moved to the vanilla anvil. We are considering a different block that works with tool visuals later

**Improved Crafting Station**

* Can be crafted from a pattern and either a crafting station or any wooden table
* Alternatively, can be crafted from a pattern and a log to use the log texture on the legs

**Improved station tabs**

* Any two station blocks together will now form tabs, instead of requiring a crafting station
* Multiple of the same block can be tabs, for example placing 2 crafting stations together gives tabs to switch between them
* At most 6 tabs can exist in the UI

**Reworked repair kits**

* Replaces the sharpening kits
* No more mining level change, that is left to modifiers such as diamond and netherite
* Still repair on the go

## Materials

**Material tiers**

* Materials now come in more clearly defined tiers, and all are divided into general, weapon, harvest, or special materials
* Tier 1:
    * Starting tool tier
    * Includes wood, stone, flint, and bone
    * In the nether, this tier uses nether woods, basalt, blackstone, and necrotic bones
    * In the end, this tier consists of chorus
* Tier 2
    * Requires ores or the melter to obtain materials
    * Includes iron, copper, slimewood, seared stone, and bloodbone
    * In the nether, this tier includes scorched stone
    * In the end, this tier includes end stone
    * The emerald modifier will also upgrade a tool to tier 2
* Tier 3:
    * Requires alloying to obtain materials
    * Includes nahuatl, slimesteel, tinker's bronze, pig iron, and rose gold
    * In the nether, this tier includes cobalt and hollow
    * In the end, this tier includes dragonstone
    * The diamond modifier will also upgrade a tool to tier 3
* Tier 4:
    * Requires nether access to obtain materials
    * Includes manyullyn, hepatizon, queen's slime, soulsteel, and blazing bone
    * The netherite modifier will also upgrade a tool to tier 4, requires either the diamond or emerald modifier
* Tier 5:
    * Requires end access to obtain materials
    * Includes KnightSlime, Ebonite, and Alexandrite
    * The Gardite modifier will also upgrade a tool to tier 5, requires either netherite or worldbound

**Stat updates**

* Handles reworked:
    * No longer have a flat durability boost
    * Have 4 multipliers: durability, attack speed, attack damage, and mining speed
    * Most materials only have 2 multipliers set, though later game materials will set at most 3
* Bindings reworked:
    * Bindings no longer have any stats
    * Instead, the purpose of bindings are to let you choose the trait you wish without concern for material tiers

**Part Cleanup**

* Many parts that only got used once were removed in favor of reusing parts
* Currently, there are two types of handles: small (tool) and tough
* For bindings, tools use just tool bindings and large plates, no more tough bindings
* Sword guards are replaced with tool handles
* Tool heads ideally will be used in at least two tools. For example, the axe head is used on the axe and the mattock

## Modifiers
For a full list of modifiers and traits, see [this spreadsheet](https://docs.google.com/spreadsheets/d/17qwV8UOR0DBsUqbxyernG4e4LtjAZ55DMAqnJWc2kLw/edit#gid=0)

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
* Some traits from 1.12 got moved to modifiers, and some new traits got added

**Notable modifier changes**

* Reinforced V no longer grants unbreakable
    * Bonus is now based on the vanilla formula, which makes the first levels stronger
    * Unbreakable has been moved to an ability, with Reinforced V as a prerequisite
* Emerald now grants bonus damage to illagers
* Haste is a bit stronger to be more in line with the efficiency enchantment
* Autosmelt and luck currently do not have special interactions
    * Likely we will leave out the interactions, as the main use (multiplying ingots) is coming to vanilla in 1.17
* Embossments were removed, but a similar mechanic will return with the soul forge
* Modifier recipes changed. Look for recipes in JEI, do not make issues about modifiers being missing because the recipe changed
* Removing modifiers from existing tools is planned, but currently not implemented

## Tools

### Small

These tools are available from tier 1 and onwards.

* *Pickaxe*:
    * Adding expanders now increases the tool's area to 1x1x3, then to 1x3x3
    * Starts with Piercing I, in exchange for a lower damage stat
* *Mattock*:
    * Makes paths instead of hoeing, effective on all blocks the shovel could break
    * Replaces the shovel
    * Adding expanders grants the tool vein mining, first at a range of 1 then a range of 2
    * Does bonus knockback
* *Hand Axe*:
    * Rebalanced to be closer to the vanilla axe, making it a strong weapon
    * Adding expanders first increases it to a cross shape, then a 3x3 rectangle
* *Kama*:
    * Gained the ability to hoe blocks, making it a fully effective farming tool
    * Adding expanders first increases it to a half sphere cross shape, then a 3x3x2 half sphere
    * Faster than a sword, but lower attack damage
* *Sword*
    * Renamed from broadsword since its the only remaining sword
    * Best damage per second of all weapons, due to average attack speed and damage
* *Dagger*:
    * Fast weapon with low damage, but can attack on right click for use in the offhand.
    * Replaces the rapier
* *Flint and Bronze*:
    * Tinkers' Construct version of flint and steel
    * Can receive durability based and melee modifiers, along with interaction based abilities
    * Expanders increase area of effect, along with the unique fire primer modifier

### Broad

These tools require the Tinker's Anvil to craft, a tier 3 component. Tool parts will possibly use of the Part Forge in the future. All broad tools are two handed, meaning the offhand is unavailable while using unless the offhanded modifier is applied.

* *Sledgehammer*:
    * Area starts at 3x3, expanders increase to 3x5 then 5x5
    * Effective against undead, starting with Smite II
* *Veining Hammer*:
    * Breaks a vein of ores within 2 blocks, expands up to 4 blocks with expanders
    * One of the fastest broad weapons
    * Effective against armor, starting with Piercing II
* *Excavator*:
    * Area starts at 3x3, expanders increase to 3x5 then 5x5
    * Starts with Knockback II
* *Broad Axe*:
    * Replaces the lumber axe.
    * Tree logic works in a column, meaning a large tree takes 4 hits to break
    * Expanders increase max tree base size
    * When targeting non-logs, has a 1x1x6 area of effect, expandable up to 3x6x2
    * High damage, but really slow
* *Cleaver*:
    * Now has sweep attack
    * If forge ever fixes their attribute, will grant bonus attack reach
* *Scythe*:
    * Retains area attack
    * Can now hoe the ground

### Armor

Armor has some different rules for how modifiers apply. With the exception of the battle sign, all armor is a crafting station recipe with only one "part".

* *Battle Sign*: Getting some reworking to be less effective to allow for proper shields
* *Shield*: Added as a single type modifiable item, similar to armor.
* *Armor*: Available in three sets: travelers, plate, and slime suit. One recipe instead of variable materials, to allow more focus on modifiers.

### Ranged

These weapons make use of drawspeed and projectile behavior

* *Crossbow*:
    * Launches vanilla mod added arrows, along with fireworks (possibly requiring a modifier to do so)
    * Rebalanced to be closer to the vanilla crossbow
    * Will be crafted as a small tool, first form of bow available
    * Likely will be able to dual wield using the dual wielding modifier
* *Longbow*:
    * Two handed variant of the crossbow
    * Allows much greater accuracy and more damage at the cost of slower drawspeed
* *Slingshot*:
    * Weapon variant of slimeslings
    * Can fire projectile items such as snowballs, shurikens, fire charges, and splash potions
* *Boomerang*:
    * New throwable weapon
    * Deals damage then returns to hand
    * Behavior will be similar to a trident with loyalty
* *Spear*:
    * Cross between a boomerang and a cleaver
    * Works in melee as a high reach weapon
    * Can be thrown for a ranged attack
    * Takes the role of the vanilla trident

### Undecided

The following tools are not removed as we liked them too much to abandon them. However, they do not precisely fit in our tool tiers. They may end up in the addon Tinkers' Complement to serve as examples of an addon adding new tools.

* *Battle Sign*:
    * Cross between a shield and a melee weapon
    * Lots of overlap with cleaves if they get blocking

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
    * Leap returned as a slime sling variant
* *Longbows*
    * Were basically a reskin of the short bow with more expensive parts and slightly different stats
    * Cross bow is being declared the large version of the bow
    * Bow will have modifiers that make its stats closer to the longbows original stats
* *Rapiers*
    * Ended up being too similar to the dagger
    * The armor pierce ability was too weak against monsters, and too strong against players, the piercing modifier should be a good compromise

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
* One example is blazing bone, from pouring blazing blood on necrotic bones
* Composite recipes existed in 1.12 and before, though the name is new

**New peripherals**
 
* Seared Ladder
    * Climbable seared block to prevent molten player
* Seared Chute
    * Smeltery item input and output
* Seared Duct
    * Filtered version of the seared drain

**Smeltery variants**

* Foundry
    * Nether smeltery variant
    * Aids in nether survival, crafted from basalt/gravel, magma cream, and soul sand
    * Requires the frame and floor corners to build, but has increased capacity
    * Cannot alloy and lower ore multiplier, but ores give byproducts
* New end smeltery planned
    * Built upside down, because why not?
    * Only can hold gasses, no liquids
* "Smeltery Sandwich"
    * Code name for a new smeltery variant combining the other three variants
    * Alloys liquids and gasses together

## Recipe changes

**Smeltery recipe changed**

* The smeltery controller now requires casting molten copper
* Seared drains include copper as part of their recipe
* These changes are to encourage use of the melter before jumping to a smeltery

**Changed seared stone recipe**

* Seared stone can no longer be obtained by melting down cobblestone
* Instead, seared stone can be casted from pouring molten clay on stone
* While this change does make giant smelteries more expensive, the foundry should be cheaper to produce (basalt and magma cream)

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
        * If placing mobs in the smeltery is not the challenge for you, there is also a melting modifier available
        
**Alloy improvements**

* Alloying now has a temperature property, so some recipes can require a hotter fuel

**Smeltery structure**

* Smeltery can now be up to 16x16x65, or 14x14x64 internal
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
    * Casting recipes come in many variants
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
* Note that Natura may not release on all the versions that Tinkers will. However, these features were removed from Tinkers' in the first place as they did not fit the design.
    
**Pink slime**

* Was the fallback for mixing slimes towards the end of 1.12.
* Decided it was a bit too awkward of a mechanic
* In 1.16, there is no more mixing slime, so items must use fully one color to be crafted in general

**Tinker Tank**

* Removed due to content overlap
* The commonly used purpose of the tank, preventing accidental alloys, is now handled by a smeltery or foundry with no fuel.
* The closest multiblock to the original seared tank is a foundry with no fuel tank, as it considers all blocks for fluid capacity