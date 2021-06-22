All JSONs that pertain to the same material *must* have the same file name and resource ID.
# Data
## Definition
Location: `/data/<resource_id>/materials/definition/`

### Keys
`craftable`: Boolean. Whether the Material can be crafted into parts in the Part Builder.  
`tier`: Integer. Material's tier.  
`sortOrder`: Integer. Material's order within the tier, for sorting.  
--Known defaults: `0`: general, `1`: harvest, `2`: weapons, `3`: special, `5`: compat, `7`: Nether materials in lower tiers, `10`: End materials in lower tiers.  
`fluid`: [[Fluid|Common-JSON-Value-Types#fluid]]. The fluid this material can be cast from or molten down into.  
`fluidPerUnit`: Integer. The amount of the fluid per one unit.  
`textColor`: [[Color|Common-JSON-Value-Types#color]], but, like, with a # in front of it. The color of the material's text.  
`temperature`: Integer. The material fluid's smeltery temperature. For melting and casting.  

### Example
    {
      "craftable": false,
      "tier": 3,
      "sortOrder": 7,
      "fluid": "tconstruct:molten_cobalt",
      "fluidPerUnit": 144,
      "textColor": "#2376DD",
      "temperature": 950
    }
## Stats
Location: `/data/<resource_id>/materials/stats/`

### Keys
`stats`: An object that gives part types a stat block. If a stat block for a part type is not defined, the material cannot be used with parts that use that stat.  

### Example
    {
      "stats": {
        "tconstruct:extra": {},
        "tconstruct:handle": {
          "durability": 1.1,
          "miningSpeed": 1.1,
          "attackSpeed": 1.1,
          "attackDamage": 1.0
        },
        "tconstruct:head": {
          "durability": 800,
          "miningSpeed": 8.0,
          "harvestLevel": 3,
          "attack": 2.5
        }
      }
    }

## Traits
Location: `/data/<resource_id>/materials/traits/`  

### Keys
`default`: List of [[Modifier Entries|Common-JSON-Value-Types#modifierentry]]. The default trait.  
`perStat`: An object that gives part types a list of [[Modifier Entries|Common-JSON-Value-Types#modifierentry]] to use.  

### Example
    {
      "default": [
        {
          "name": "bone_hurting_mod:bone_hurting_trait",
          "level": 1
        }
      ],
      "perStat": {
        "bone_hurting_mod:bone": [
          {
            "name": "bone_hurting_mod:juicy_trait",
            "level": 1
          }
        ]
      }
    }

# Assets  
Location: `/assets/<resource_id>/models/tool_materials/`  

### Keys
`texture`: [[Resource Location|Common-JSON-Value-Types#resourcelocation]]. A suffix for an untinted texture for the material. Note that this texture will still be loaded from the same namespace as the part texture, the texture namespace just gets included in the suffix.
--Result: `tconstruct:cobalt` -> `head_tconstruct_cobalt.png`.  
`fallbacks`: List of strings. Default suffixes the mod tries to load before it gives up and loads the default texture. Used in order from left to right.  
--Known defaults: `wood`, `rock`, `metal` (heads); `stick`, `bone` (handles).  
`color`: [[Color|Common-JSON-Value-Types#color]]. The color to paint the material with.

### Example
    {
      "fallbacks": ["metal"],
      "color": "2376dd"
    }