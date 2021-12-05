## Next Alpha

### Armor

* Added two and a half sets of modifiable armor: travelers and plate, plus half of the slimesuit

**Travelers Armor**

* Overworld armor set, made from copper and leather
* Balanced number of upgrade and defense modifier slots

**Plate Armor**

* Nether armor set, made from manyullyn and chain
* Higher armor and high number of defense slots, but few upgrade slots

**Slime Suit**

* Slimeskull is a new helmet made from a mob head and enderslime. Different heads grant different abilities.
* Slimelytra is a modifiable elytra from an elytra and enderslime.
* Slimeshell is leggings made from a shulker shell and enderslime. Its ability is not yet implemented, so for now it just grants protection (since the shell is hard).
* Slimeboots are more expensive now, but also support modifiers and grant leaping I.

### Modifiers

**Armor**

Note that not all planned modifiers are fully implemented. Notably most of the planned leggings modifiers and some of the planned boots modifiers are not finished

* *Defense* - New group of modifiers that increases protection
    * *Melee Protection* - Protects against melee attacks such as zombies or hoglins
    * *Projectile Protection* - Protects against projectiles and decreases visibility to mobs
    * *Fire Protection* - Protects against fire damage and decreases fire tick time
    * *Blast Protection* - Protects against explosion damage and decreases knockback from explosions
    * *Magic Protection* - Protects against magic damage (such as potions) and decreases duration of negative potion effects
    * *Turtle Shell* - Protects against all types of damage while underwater and increases swim speed
    * *Dragonborn* - Protects against all types of damage while in air and increases critical damage
    * *Knockback Resistance* - Adds +1 knockback resistance
    * *Revitalizing* - Increases max health
    * *Golden* - Prevents piglins from being hostile
* *Upgrades*
    * *Diamond* - grants +1 armor in addition to durability boosts
    * *Emerald* - grants +0.5 knockback resistance in addition to durability boosts
    * *Magnetic* - works on armor providing a constant magnet
    * *Netherite* - grants +1 toughness and +0.5 knockback resistance in addition to durability boosts and dropped item protection
    * *Overforced* - increases overslime capacity
    * *Reinforced* - decreases damage taken by armor
    * *Ricochet* - increases knockback received
    * *Sticky* - causes attackers to sometimes receive slowness
    * *Springy* - causes attackers to sometimes bounce away
    * *Soulbound* - causes the armor to remain in the inventory on death
    * *Thorns* - causes attackers to sometimes take damage
    * *Respiration* - Helmet upgrade - Decreases rate of air consumption underwater
    * *The One Probe* - Helmet upgrade - Compatibility, grants access to the One Probe UI while wearing
    * *Haste* - Chestplate upgrade - Increases mining speed of held tool
    * *Power* - Chestplate upgrade - Increases attack damage of held tool
    * *Experienced* - Leggings upgrade - Increases experience gained
    * *Speedy* - Leggings upgrade - Increases movement speed
    * *Leaping* - Leggings upgrade - Increases jump height
    * *Feather Falling* - Boot upgrade - Increases protection against fall damage
* *Slotless*
    * *Draconic* - grants +1 ability slot
    * *Harmonious*, *Recapitated*, *Resurrected*, *Writable* - grants +1 upgrade slot
    * *Overslime* - gives armor a second durability bar repaired with slime
    * *Shiny* - makes the armor glow
    * *Worldbound* - makes the armor item immune to damage when dropped
* *Abilities*
    * *Gilded* - trades 1 ability slot for 2 upgrade slots
    * *Unbreakable* - makes the armor no longer lose durability
    * *Aqua affinity* - Helmet ability - allows mining underwater with no penalty
    * *Slurping* - Helmet ability - allows you to drink fluid contained in the helmet for effects
    * *Zoom* - Helmet ability - adds a toggleable zoom ability similar to 1.17's telescope
    * *Bucketing* - Chestplate ability - empty hand will fill or drain fluid from the chestplate
    * *Frestarter* - Chestplate ability - empty hand can create fire
    * *Glowing* - Chestplate ability - empty hand will place glows, a light source
    * *Pathing* - Chestplate ability - empty hand can create paths like a shovel
    * *Reach* - Chestplate ability - increases harvest block reach of held tool
    * *Spilling* - Chestplate ability - spills fluid on attackers, causing potion effects, bonus damage, and more
    * *Stripping* - Chestplate ability - empty hand can strip wood like an axe
    * *Tilling* - Chestplate ability - empty hand can till dirt like a hoe/kama
    * *Unarmed Attack* - Chestplate ability - allows you to punch with both the main and offhand, and allows modifying the chestplate with melee weapon modifiers to improve unarmed damage
    * *Luck* - Leggings ability - increases fortune and looting of the tool in hand
    * *Bouncy* - Boot ability - causes you to bounce instead of taking fall damage, replaces slime boots
    * *Double Jump* - Boot ability- allows you to jump a second time in air

**Tools**

* New modifiers
    * *Nohanded* - Slotless - Upgraded form of offhanded, entirely disables tool interaction ability. Indented to allow a tool in the main hand and using a chestplate interaction ability in the offhand
    * *Sticky* - Upgrade - Causes slowness on the attacked target
    * *The One Probe* - Upgrade - Compatibility, grants access to the One Probe UI while holding
* Changes
    * *Severing* - Fix wither skeleton being marked rare instead of wither
    * *Spilling* - Water spilling effect now extinguishes fire, perfect for a spilling helmet or a "healing" sword

### Commands

* Fix slots command `set` argument syntax being incorrect

### Books

* Many improvements to the book indexes
* Encyclopedia lists all armor modifiers and pieces

### API

**Armor**

* Modifiable Armor Item
* Armor Material builder
* Many armor related modifier hooks
* Several new armor related modifier tags, and the new `HELD` tag to make a modifier only work on tools held in either hand (non-armor)



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

* Slime Suit armor

**Possible tool types**

Tools that I would like to include, but may not make it before the first beta

* Bows/crossbows
* Shield
* Battle Sign

**Materials**

* Tier 1: Chorus
* Tier 2: End Stone

**Modifiers**

* Boot walk modifiers
* Legging inventory modifiers
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