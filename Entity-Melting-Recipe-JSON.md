Recipe to melt an entity into fluid in the smeltery. Any entities that do not have a corresponding will default to producing 50 mb of blood for 2 hearts of damage.

### Keys
* `type`: Must be `"tconstruct:entity_melting"`.  
* `entity` ([[EntityIngredient|Common-JSON-Value-Types#entityingredient]]): The entity to be melted.  
`result` ([[FluidStack|Common-JSON-Value-Types#fluidstack]]): The liquid added to the smeltery.  
`damage` (integer): Damage dealt to the entity when it is melted in half hearts (meaning 2 is 1 heart). Defaults to 2. If the entity has less health than this number, the fluid result is scaled down.

### Example

Melts any of endermen, endermites, or the enderdragon into 10 mb of molten ender. Damages the entity 2 per 10 mb produced.

```json
{
  "type": "tconstruct:entity_melting",
  "entity": {
    "types": [
      "minecraft:enderman",
      "minecraft:endermite",
      "minecraft:ender_dragon"
    ]
  },
  "result": {
    "fluid": "tconstruct:molten_ender",
    "amount": 10
  },
  "damage": 2
}
```

More examples in `.jar/data/tconstruct/recipes/smeltery/entity_melting/`