This page documents any tags in Tinker's Construct 3 with special behavior. Specifically, tags with behavior outside of recipes. Tags only used as recipe inputs are not described on this page.

## Blocks

### Smeltery

| Name | Behavior |
| :--- | :------- |
| `tconstruct:melter_tanks` | Blocks in this tag are a valid fuel source for melters. In order to function, the tile entity must have either an `IItemHandler` or an `IFluidHandler` capability |
| `tconstruct:smeltery`  | Blocks in this tag are a valid smeltery block. In general do not use this tag directly, add to one or more of wall, floor, or tanks. |
| `tconstruct:smeltery/tanks`  | Blocks in this tag are a valid fuel source for the smeltery. In order to function, the tile entity must implement `IServantLogic` and they must have either an `IItemHandler` or an `IFluidHandler` capability. |
| `tconstruct:smeltery/floor` | Blocks in this tag are a valid floor blocks for the smeltery. In order to function, the tile entity must implement `IServantLogic`. |
| `tconstruct:smeltery/wall` | Blocks in this tag are a valid wall blocks for the smeltery. In order to function, the tile entity must implement `IServantLogic`. All blocks in the smeltery need to be included in this tag to properly update. |

### Tools

| Name | Behavior |
| :--- | :------- |
| `tconstruct:anvil_metal` | Blocks in this tag and the corresponding item tag are valid blocks to craft the Tinker's Anvil. Generally alloy metal blocks. |
| `tconstruct:harvestable` | Blocks in this tag can be harvested using a kama or scythe. Only add items to this tag directly if you plan to use the event, for most harvestables use one of the sub tags. |
| `tconstruct:harvestable/crops` | Blocks that are harvested by breaking the block at max age, which drops produce and seeds. Will replant the crop at age 0. |
| `tconstruct:harvestable/interact` | Blocks that are harvested by interacting with them (e.g. berry bushes). Expects interaction through the block method, not the item event. |
| `tconstruct:harvestable/stackable`| Blocks that are harvested by breaking blocks above the bottom (e.g. sugar cane). |

### World

| Name | Behavior |
| :--- | :------- |
| `tconstruct:slimy_logs`   | Blocks in this tag are a valid trunk for slimy leaves blocks |
| `tconstruct:slimy_leaves` | Blocks in this tag can be replaced by leaves from slimy blocks and can support slimy vines despite being non-solid |

## Items

### Smeltery

| Name | Behavior |
| :--- | :------- |
| `tconstruct:duct_containers` | Items in this tag can be placed inside the seared duct. Additionally, items whose container item is in this tag can be placed inside the seared duct, allowing all buckets to work simply by including the empty bucket. |

### Tools

| Name | Behavior |
| :--- | :------- |
| `tconstruct:autosmelt_blacklist` | Items in this tag will not be smelted by the autosmelt modifier. |
| `tconstruct:seeds` | Items in this tag are valid seeds for replanting crops using the scythe. |
| `tconstruct:modifiable` | Items in this tag can receive modifiers from recipes that do not specify an ingredient. Additionally, items in this tag will process relevant modifier events. Note that some modifier events are handled through `ToolCore`, so simply adding an item to this tag will not make it support modifiers. |
| `tconstruct:modifiable/multipart` | Items in this tag work as a multipart tool for relevant recipes. It is expected that they extend `ToolCore` |
| `tconstruct:modifiable/melee` | Any modifiable tool that can deal melee damage. Note that not all melee tools are weapons. |
| `tconstruct:modifiable/combat` | Items in this tag will not receive double damage when attacking an enemy. |
| `tconstruct:modifiable/harvest` | Items in this tag support mining based events. If the item extends `ToolCore`, it also will display mining speed in tooltips. |
| `tconstruct:modifiable/harvest/stone` | Items in this tag support mining stone, for some special modifiers. Items in this tag are automatically added to `tconstruct:modifiable/harvest`. |
| `tconstruct:modifiable/aoe` | Items in this tag support receiving expanders. It is up to the item to respond to the expander. |
| `tconstruct:modifiable/melee_or_harvest` | Internal tag used as many modifiers support both melee and harvest. Should not add to directly, use the relevant tag. |

## Entity Types

### Smeltery
| Name | Behavior |
| :--- | :------- |
| `tconstruct:melting/show_in_default` | Entities to show in the entity melting default list in JEI. By default anything with an entity classification of misc does not show. |
| `tconstruct:melting/hide_in_default` | Entities to not show in the entity melting default list in JEI. By default anything with an entity classification other than misc shows. |

### World

| Name | Behavior |
| :--- | :------- |
| `tconstruct:bouncy` | Entities in this tag bounce as if they are wearing slime boots. |

## Materials
 For a few notes on support:

* If a material supports usage as a tool, it is expect the ingot tag has a value for full compatibility.
* If a material support melting/casting, all of `ingots`, `nuggets`, `storage_blocks`, and `dusts` are supported if present. `ingots` must be present for the fluid to show in JEI.
* If a material support ore melting, `ores` is supported if present.
* If a material supports alloying, it requires `ingots` exist for the material and all components to add the alloy recipe.

### Native

This subsection lists materials provided by Tinkers Construct natively.

| Material | Support | Notes |
| :------- | :------- | :---- |
| `cobalt`          | Melting/Casting, Ore, Tool Material      | |
| `copper`          | Melting/Casting, Ore, Tool Material      | |
| `gold`            | Melting/Casting, Ore                     | |
| `hepatizon`       | Melting/Casting, Alloying, Tool Material | Alloys 2 from 2 copper, 1 cobalt and 1 obsidian. |
| `iron`            | Melting/Casting, Ore, Tool Material      | |
| `netherite`       | Melting/Casting, Alloying                | Alloys 1 from 4 gold and 4 netherite scrap. |
| `netherite_scrap` | Melting/Casting, Ore                     | Molten form is called debris. Ore is ancient debris. |
| `pig_iron`        | Melting/Casting, Alloying, Tool Material | Alloys 2 from 1 iron, 1 blood and 1 clay. |
| `queens_slime`    | Melting/Casting, Alloying, Tool Material | Alloys 2 from 1 cobalt, 1 gold and 1 magma cream. |
| `rose_gold`       | Melting/Casting, Alloying, Tool Material | Alloys 4 from 3 copper and 1 gold. |
| `silicon_bronze`  | Melting/Casting, Alloying, Tool Material | Alloys 4 from 3 copper and 1 sand. |
| `slimesteel`      | Melting/Casting, Alloying, Tool Material | Alloys 2 from 1 iron, 1 blueslime and 1 seared brick. |

### Compat

This subsection lists materials that have automatic compat for smeltery recipes or tool materials.

| Material | Support | Notes |
| :------- | :------- | :---- |
| `aluminum`   | Melting/Casting, Ore                     | |
| `brass`      | Melting/Casting, Alloying                | Alloys 4 from 3 copper and 1 zinc |
| `bronze`     | Melting/Casting, Alloying, Tool Material | Alloys 4 from 3 copper and 1 tin |
| `constantan` | Melting/Casting, Alloying, Tool Material | Alloys 2 from 1 copper and 1 nickel |
| `electrum`   | Melting/Casting, Alloying, Tool Material | Alloys 2 from 1 silver and 1 gold |
| `invar`      | Melting/Casting, Alloying                | Alloys 3 from 2 iron and 1 nickel |
| `lead`       | Melting/Casting, Ore, Tool Material      | |
| `nickel`     | Melting/Casting, Ore                     | |
| `osmium`     | Melting/Casting, Ore                     | |
| `pewter`     | Melting/Casting, Alloying                | Alloys 2 from 1 iron and 1 lead |
| `platinum`   | Melting/Casting, Ore                     | |
| `steel`      | Melting/Casting, Tool Material           | |
| `silver`     | Melting/Casting, Ore, Tool Material      | |
| `tin`        | Melting/Casting, Ore                     | |
| `tungsten`   | Melting/Casting, Ore                     | |
| `uranium`    | Melting/Casting, Ore                     | |
| `zinc`       | Melting/Casting, Ore                     | |