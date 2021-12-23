Tools can be repaired in both the Tinker Station and the Crafting table. These recipes define input items used for both types of repair.

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [Tinker Station Repair](#tinker-station-repair)
- [Repair Kit](#repair-kit)
- [Specialized Repair](#specialized-repair)
- [Modifier Repair](#modifier-repair)
</td>
</table>

## Tinker Station Repair

This recipe allows repairing tools in the Tinker Station using the proper item defined in [[Material Recipes|Material-Recipe-JSON]] or repair kits. It cannot be configured, but can be disabled to disable tool repair.

It simply has one key: `type`, which is set to `tconstruct:tinker_station_repair`. The recipe is defined in `TConstruct.jar/data/tconstruct/recipes/tables/tinker_station_repair`

## Repair Kit

This recipe allows repairing tools in the crafting table using repair kits. It cannot be configured, but can be disabled to disable repair kit repair.

It simply has one key: `type`, which is set to `tconstruct:crafting_table_repair`

## Specialized Repair

Defines a repair material for repairing a tool. Used for tools that do not have tool parts, such as armor or flint and bronze.

### Keys
* `type` (string): Two options:
    * `tconstruct:specialized_station_repair`: defines repairing using material items or repair kits in the tinker station
    * `tconstruct:specialized_repair_kit`: defines repairing repair kits in the crafting table
* `tool` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Tool to repair
* `repair_material` ([[MateiralId|Common-JSON-Value-Types#material]]): Material used for repairing. Material items will be pulled from [[Material Recipes|Material Recipe JSON]] for tinker station repair.

### Example

Defines flint and bronze as being repairable using tinkers bronze in the tinker station.

```json
{
  "type": "tconstruct:specialized_station_repair",
  "tool": {
    "item": "tconstruct:flint_and_bronze"
  },
  "repair_material": "tconstruct:tinkers_bronze"
}
```

Defines repairing any plate armor using a manyullyn repair kit in the crafting table.

```json
{
  "type": "tconstruct:specialized_repair_kit",
  "tool": [
    {
      "item": "tconstruct:plate_boots"
    },
    {
      "item": "tconstruct:plate_leggings"
    },
    {
      "item": "tconstruct:plate_chestplate"
    },
    {
      "item": "tconstruct:plate_helmet"
    }
  ],
  "repair_material": "tconstruct:manyullyn"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/armor/repair/`

## Modifier Repair

### Keys
* `type` (string): Two options:
    * `tconstruct:modifier_repair`: defines repairing in the tinker station, consumes as many items as possible for repair
    * `tconstruct:crafting_modifier_repair`: defines repairing in the crafting table, uses at most 1 item at a time
* `modifier` ([[Modifier|Common-JSON-Value-Types#resourcelocation]]): Modifier required to repair the tool using this recipe.
* `ingredient` ([[Ingredient|Common-JSON-Value-Types#ingredient]]): Ingredient consumed for repair.
* `repair_amount` (integer): Amount repaired per item.

### Examples

Allows repairing any tool with the tasty modifier using bacon in the tinker station, restoring 25 durability.

```json
{
  "type": "tconstruct:modifier_repair",
  "modifier": "tconstruct:tasty",
  "ingredient": {
    "item": "tconstruct:bacon"
  },
  "repair_amount": 25
}
```

Allows repairing any tool with the stringy modifier using string in the crafting table.

```json
{
  "type": "tconstruct:crafting_modifier_repair",
  "modifier": "tconstruct:stringy",
  "ingredient": {
    "tag": "forge:string"
  },
  "repair_amount": 25
}
```