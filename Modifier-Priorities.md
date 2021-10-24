
| Modifier | Priority | Relevant Hooks | Comments |
| :------- | :------- | :------------- | :------- |
| `TannedModifier` | 200 | `onDamageTool` | Wants to be processed before all other durability hooks |
| `StoneshieldModifier` | 175 | `onDamageTool` | Wants to be processed before overslime |
| `OverslimeModifier` | 150 | `onDamageTool` | Wants to be processed before normal durability |
| `UnbreakableModifier` | 125 | `onDamageTool` | Does not protect overslime, skips unneeded work in unbreakable. |
| `BlastingModifier`, `LightspeedModifier`, `HydralicModifier` | 125 | `onBreakSpeed` | Provides a flat boost to break speed, wants to apply it before percentage boosts. |
| `OvercastModifier` | 90 | `addVolatileData` | Adds a percentage boost to overslime capacity, wants to run after overslime and overforced, but not boost overlord. |
| `OffhandAttackModifier` | 90 | `getAttackDamage`, `onEntityUse` | Reduces attack damage by a percentage, most additive boosts are 100 priority. Entity use also uses this to just be one of the first. |
| `BucketingModifier` | 80 | `addVolatileData`, `afterBlockUse` | Rounds capacity to the nearest bucket. |
| Pathing, Stripping, Tilling | 75 | `afterBlockUse` | Needs to run before glowing. |
| `OverlordModifier` | 90 | `addVolatileData` | Runs last so its after overcast, as it would make overcast way to strong to boost this large amount by a percentage. |
| `MomentumModifier`, `Airborne` | 75 | `onBreakSpeed` | Wants to multiply all previous speed bonuses |
| `GlowingModifier` | 70 | `afterBlockUse` | Completely overrides block use behavior, so want to run after other block use modifiers. |
| Multi-level `ExtraModifier` | 65 | `afterBlockUse` | Done so it displays late last in the tinker station. |
| Multi-level `ExtraModifier` | 60 | - | Done so it displays late last in the tinker station. |
| Single level `ExtraModifier` | 50 | - | Done so it displays late last in the tinker station. |
| Shears, Silky Shears | `Short.MIN_VALUE` | `removeBlock`, `onEntityUse` | Tools native right click ability, intended to be overriden by any interaction modifier. |
| `ExchangingModifier` | `Short.MIN_VALUE - 20` | `removeBlock` | Needs to run after the shears modifier to ensure tripwire is properly diffused |
| Shovel Transform, Axe Transform, Hoe Transform | `Integer.MIN_VALUE + 50` | `afterBlockUse` | Tools native right click ability, intended to be overriden by any interaction modifier. |