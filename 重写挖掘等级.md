Supported since TiC 2.6.1

The harvest level names displayed in TiC can be overwritten by providing a localization file (via Resource Pack) with the following entries:

`ui.mininglevel.X=Unobtanium`

where X stands for the corresponding harvest level.

**HOWEVER** to use the feature you need to start at 0 (stone), and all entries up to X have to be present, e.g.

    ui.mininglevel.0=Stone
    ui.mininglevel.1=Copper
    ui.mininglevel.2=Iron
    ui.mininglevel.3=Diamond
    ui.mininglevel.4=Cobalt
    ui.mininglevel.5=Manyullyn
    ui.mininglevel.6=Unobtanium

## Custom Colors for the Harvest Levels

It's a bit technical, but [this](https://github.com/SlimeKnights/TinkersConstruct/issues/3370) issue shows how to use the internal color codes in text in language strings.