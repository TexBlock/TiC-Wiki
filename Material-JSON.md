All JSONs that pertain to the same material *must* have the same file name.
# Data  
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
`texture`: [[Resource Location|Common-JSON-Value-Types#resourcelocation]]. A suffix for an untinted texture for the material. WARNING: This texture will still be loaded from the same namespace as the rest of the material.  
--Result: `tconstruct:cobalt` -> `head_tconstruct_cobalt.png`.  
`fallbacks`: List of strings. Default suffixes the mod tries to load before it gives up and loads the default texture. Used in order from left to right.  
--Known defaults: `wood`, `rock`, `metal` (heads); `stick`, `bone` (handles).  
`color`: [[Color|Common-JSON-Value-Types#color]]. The color to paint the material with.

### Example
    {
      "fallbacks": ["metal"],
      "color": "2376dd"
    }