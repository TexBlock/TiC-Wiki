These recipes define fundamental tool building related recipes.

## Tool Building

Recipe for creating a tool. Currently just defines the tool as craftable from tool parts, though in the future will allow specifying other items required to create the tool. If a tool is defined with more than 3 parts, it must be created in the anvil.

### Keys
* `type` (string): Must be `tconstruct:tool_building`.  
* `result` ([[IModifiable|Common-JSON-Value-Types#resourcelocation]]): Item being crafted.

### Example

Defines the axe as buildable in the tinker station.

```json
{
  "type": "tconstruct:tool_building",
  "result": "tconstruct:axe"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/tools/building/`

## Part Swapping

This recipe allows part swapping for any tool with swappable parts. It cannot be configured, but can be disabled to disable part swapping.

It simply has one key: `type`, which is set to `tconstruct:tinker_station_part_swapping`