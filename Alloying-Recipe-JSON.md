Recipe JSON to convert a list of fluids into a single fluid output. Examples can be found in `TConstruct.jar/data/tconstruct/recipes/smeltery/alloys/`.

### Keys
* `type` (string): Must be "tconstruct:alloy".
* `inputs` (array): List of [FluidIngredients](#fluidingredient): The fluids that are being alloyed together. Must have at least two entries, and a single fluid in the structure cannot be used to match multiple inputs.
* `temperature` (integer): Minimum temperature of the fuel to alloy. For comparison:
    * Solid fuel has a temperature of 800 degrees
    * Lava has a temperature of 1000 degrees
    * Blazing blood has a temperature of 1500 degrees
* `result` ([FluidStack](#fluidstack)). The recipe's output. Cannot be contained in any input.

### Example
Alloys 3 ingots of copper and 1 ingot of gold to produce 4 ingots of rose gold. Requires a fuel of at least 550 degrees to melt.

```json
{
  "type": "tconstruct:alloy",
  "inputs": [
    {
      "name": "tconstruct:molten_copper",
      "amount": 432
    },
    {
      "name": "tconstruct:molten_gold",
      "amount": 144
    }
  ],
  "result": {
    "fluid": "tconstruct:molten_rose_gold",
    "amount": 576
  },
  "temperature": 550
}
```