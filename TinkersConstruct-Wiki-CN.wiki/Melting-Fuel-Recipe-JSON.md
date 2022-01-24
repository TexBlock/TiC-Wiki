This recipe defines fuels usable by the smeltery, with their burn time, rate of consumption, and temperature.

### Keys
* `type` (string): Must be `tconstruct:melting_fuel`.
* `fluid` ([[FluidIngredient|Common-JSON-Value-Types#fluidingredient]]): Fluid consumed when fuel is requested.
* `temperature` (integer): Affects which recipes can be performed using this fuel, between alloy recipes and melting recipes. Also affects melting speed, with lava being 1.0x, 1500 being 1.5x, 800 0.8x and so on. For comparison, solid fuel has a temperature of 800 degrees.
* `duration` (integer): Amount of "fuel" produced. The smeltery consumes 1 fuel every 4 ticks (that is, 5 times every second).

### Example

Consumes 50 mb of lava to produce 100 fuel at a temperature of 1000 degrees. 100 fuel will last about 20 seconds.

```json
{
  "type": "tconstruct:melting_fuel",
  "fluid": {
    "name": "minecraft:lava",
    "amount": 50
  },
  "duration": 100,
  "temperature": 1000
}
```

More examples in `TConstruct.jar/data/tconstruct/recipes/smeltery/melting/fuel/`