This recipe defines head and other item drops for entities from the severing modifier.

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [Tinker Station Repair](#tinker-station-repair)
- [Repair Kit](#repair-kit)
- [Specialized Repair](#specialized-repair)
- [Modifier Repair](#modifier-repair)
- [Damaging Recipe](#damaging-recipe)
</td>
</table>

## Severing Recipe

Standard severing recipe for adding a drop to an entity. Multiple severing recipes can be added for the same entity and both will drop with separate chances.

### Keys
* `type` (string): Always `tconstruct:severing`
* `entity` ([[EntityIngredient|Common-JSON-Value-Types#entityingredient]]): Entity to sever
* `result` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]): Result of severing

### Examples

Recipe to make a blaze drop a blaze head when severed.

```json
{
  "type": "tconstruct:severing",
  "entity": {
    "type": "minecraft:blaze"
  },
  "result": "tconstruct:blaze_head"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/tools/severing/`

## Ageable Severing recipe

Severing recipe which drops different items for child and adults of the entity.

### Keys
* `type` (string): Always `tconstruct:ageable_severing`
* `entity` ([[EntityIngredient|Common-JSON-Value-Types#entityingredient]]): Entity to sever.
* `adult_result` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]): Result of severing for adult entities
* `child_result` ([[ItemOutput|Common-JSON-Value-Types#itemoutput]]): Result of severing for child entities. If missing, the entity drops nothing as a child.

### Examples

Recipe to make a chicken drop feathers when severed. It will drop nothing as a baby chicken.

```json
{
  "type": "tconstruct:ageable_severing",
  "entity": {
    "type": "minecraft:chicken"
  },
  "adult_result": {
    "item": "minecraft:feather",
    "count": 2
  }
}
```

Recipe to make turtles drop turtle shells if severed as an adult, and scutes as a child.

```json
{
  "type": "tconstruct:ageable_severing",
  "entity": {
    "type": "minecraft:turtle"
  },
  "adult_result": "minecraft:turtle_helmet",
  "child_result": "minecraft:scute"
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/tools/severing/`

## Special Severing Recipes

Some entity types register extra severing recipes to define special behaviors. They are discussed in the following sections.

### Mooshroom

Mooshrooms drop brown mushrooms if if brown and red mushrooms if red. The recipe has a `type` of `tconstruct:mooshroom_demushrooming`, and is located at `TConstruct.jar/data/tconstruct/recipes/tools/severing/mooshroom_shroom`.

### Player

Player heads when dropped store the username and skin of the killed player. The recipe has a `type` of `tconstruct:player_beheading`, and is located at `TConstruct.jar/data/tconstruct/recipes/tools/severing/player_head`.

### Sheep

Sheep drop wool of the color matching their fleece, and drop nothing if killed when shorn. The recipe has a `type` of `tconstruct:sheep_shearing`, and is located at `TConstruct.jar/data/tconstruct/recipes/tools/severing/sheep_wool`.

### Snow Golem

Snow golems drop a pumpkin if not shorn. When shorn they drop a snow block instead. The recipe has a `type` of `tconstruct:snow_golem_beheading`, and is located at `TConstruct.jar/data/tconstruct/recipes/tools/severing/snow_golem_head`.