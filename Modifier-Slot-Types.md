This page details the different types of modifier slots in Tinkers' Construct 3, along with how modders and modpack makers can use them in their packs. This page is modder focused, for a player you are better off consulting the in game guidebooks.

## Slot types

By default, Tinkers' Construct includes 4 slot types:

| Name | ID | Usage | Obtaining |
|:--|:--|:--|:--|
| Upgrade | `upgrades`  | Standard modifier slot, allows applying most modifiers. | Most tools start with 3 slots. Several modifier recipes plus rose golds trait grant additional slots. |
| Ability | `abilities` | Rare modifier slot, used for powerful modifiers that should be more limited. | Most tools start with 1 slot. An additional slot can be applied through a modifier recipe. |
| Soul    | `souls`    | Slot for use in the soul forge. Currently unused, but will be used in future updates. | In the future, hollow gems and hollow ingots will grant more soul slots. |
| Armor   | `armor`     | Slots for protection based modifiers. Basic modifiers are divided into armor and upgrade. Currently unused. | Most armor will start with 3 armor slots in addition to 3 upgrade slots. |

Slot IDs are intentionally not namespaced to encourage reuse among addons and datapacks. If you make an addon with a custom slot type, discuss it with us and we can mention it on this page.

## Adding slots

Both datapacks and addons can define slot types, though a couple of steps differ slightly as discussed in the following sections.

### Defining slots

For addons, slots can be defined using the methods in `SlotType`:
* `create(String name, int color)`: Defines a new slot type. Name should only consistent of lowercase letters, numbers, and underscores. If two slots are declared with the same name, the first instance is returned.
* `getOrCreate(String name)`: Same as above, but if the slot is undefined, uses white as the color.
* `getIfPresent(String name)`: Returns the slot if any mod declared it, or null if undeclared.

For datapacks, slots currently can only be defined in recipes, see [#Recipes](#Recipes).

### Recipes

Modifier and salvage recipes which support slots have a JSON object key named `slots` which can configure the cost for a recipe or the slots restored on removing the modifier. For datapacks, this is the only way to define slot types at this time. The format is as follows:

```json
{
  "other_recipe_contents": "...",
  "slots": {
    "<id>": <count>
  },
  "other_recipe_contents": "..."
}
```

Where `<id>` is the slot type ID, and `<count>` is the number of slots for the recipe.

### Language keys

Whichever method used, language keys are consistent. To make a custom slot properly show up in translations, three language file keys are needed. In all examples, `<id>` should be replaced with the actual ID of the trait.

* `item.tconstruct.creative_slot.<id>`: Name of the creative modifier to add an extra slot of this type.
* `stat.tconstruct.slot.prefix.<id>`: Slot name for remaining slots in tooltips. Should end in a colon and space for consistency.
* `stat.tconstruct.slot.display.<id>`: Slot name for formatting in tooltips. Inserted into several translation strings that describe slot types.

For example, for upgrades:
```json
{
  "item.tconstruct.creative_slot.upgrades": "Creative Upgrade Slot",
  "stat.tconstruct.slot.prefix.upgrades": "Upgrades: ",
  "stat.tconstruct.slot.display.upgrades": "upgrade"
}
```

### Textures

Slot types require a texture which is used both for the creative slot modifier, and in JEI integration to show slot cost. If a texture is not defined, it will fallback to the slotless book icon. Internally, JEI integration uses the textures from the item model to define.

For a datapack, its easiest to create a resource pack to override the default icons. These are defined in `assets/tconstruct/models/item/creative_slot.json`. The textures JSON object contains a mapping from slot ID to texture in the standard resource pack format. Copying this file and adding the additional textures will allow these slots.

For addons, more textures can be added via Mantle's `NBTKeyModel.registerExtraTexture(ResourceLocation key, String textureName, ResourceLocation texture)`. The following parameters are wanted:
* `key` should be passed as `tconstruct:creative_slot`
* `textureName` should be the ID of your modifier slot
* `texture` should be the texture path in standard resource pack format.