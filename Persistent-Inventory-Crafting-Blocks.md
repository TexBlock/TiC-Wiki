One of the features Tinkers' Construct provides is persistent inventory crafting blocks. In other words, the items in the crafting station remain in the block when closing the UI. To do this effectively, all crafting logic was moved into the tile entity, with a couple of hooks in the container to actually take the result. This design overall has led to far simpler code and and reduced duplication bugs when multiple players are both accessing the table.

As a side-effect of this design, all players share the same crafting UI including the same items and the same result, rather than having a copy per player. This means a couple things that affect gameplay:

* Crafting recipes cannot be individually hidden
    * Tinkers' works around this by not allowing players to take the result if they lack access to the recipe
    * If the player attempts to take a recipe to which they lack access, a message is displayed
* Displayed crafting results are not individual to each player
    * The only way this was possible was by using access transformers anyways

## Creating a player sensitive recipe

One method of accessing the player in vanilla crafting table recipes was an access transformer to the private event handler container from `CraftingInventory`. This will not work with the crafting station as we do not use that event handler, thus it is null. Additionally, as mentioned before, the original crafting hooks are not player sensitive. Since we understand some mods may wish to make player sensitive recipes, we do provide player access when the recipe result is removed.

If you want to simply prevent crashes with the crafting station, just make your recipe `matches` return false if the player/container is missing. This will effectively group the crafting station with auto-crafters that lack player access.

To create player sensitive crafting recipes that work with the crafting station:
* `matches` should return true even if a player is missing
* `getCraftingResult` should return some fallback item when the player is missing
* When the player tries to take the item, we set the player to `ForgeHooks.setCraftingPlayer()`
    * After doing so, we call both `matches` and `getCraftingResult` a second time to get the final result for the recipe
    * Within your logic, you can retrieve the player using `ForgeHooks.getCraftingPlayer()` to add player information