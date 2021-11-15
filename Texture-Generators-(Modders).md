Texture generators are a feature in Tinkers' Construct for mass-producing textures from a given set of base textures. While they may not end up as high quality as artist made textures, they are much easier for modders and artists alike.

They are two ways to run the texture generators:
* Datagen: can be set up similar to data generators for tags or recipes. This method is ideal for modders to use, and is covered by this page.
* Command: designed for use in datapacks and resource packs. This page will cover the generator setup for modders, if you are a datapack/resource pack maker, see [[Texture Generators (Data Packs)]].

## Material Part Texture Generator

`MaterialPartTextureGenerator` takes as parameters a single [`AbstractPartSpriteProvider`](#part-sprite-provider) and one or more [`AbstractMaterialSpriteProvider`](#material-sprite-provider). Unlike many other generators, you should not need to extend this class, simply creating one or more instance in `GatherDataEvent` is sufficient. Based on the needs of your addons, there are a couple setups you may use. Note you reuse one of the Tinkers' providers rather than copying and pasting it despite it not being part of `library`. It is possible there will be changes to it which requires you to rerun datagen on update; however, this will only affect your mod in dev, it will never break a released build.

See the following sections for more specifics on these generators and recommended setups.

### Addon with new materials

For an addon that just adds new materials, you will need to create an instance of `AbstractMaterialSpriteProvider`, but you can reuse the existing `TinkerPartSpriteProvider`.

### Addon with new tools

For an addon that just adds new materials, you will need to create an instance of `TinkerMaterialSpriteProvider`, but you can reuse the existing `AbstractPartSpriteProvider`.

### Addon with mix of tools and materials

Each instance of `MaterialPartTextureGenerator` can only handle a single `AbstractPartSpriteProvider`, however its perfectly fine to have multiple instances. In general, its most efficient to only use each `AbstractPartSpriteProvider` a single time due to texture caching. The following setup is recommended for addons with both tools and materials:

* One instance handling Tinkers' Construct part textures with your new materials
* One instance handling your new part textures with both your new materials and those from Tinkers' Construct

This set of generators intentionally leaves out running Tinkers' Construct part textures with Tinkers' Construct materials, as those are provided by the base mod. Do not generate textures with that combination.

Addons can also freely support other addons using this setup. You should be able to safely reuse part and material texture providers from other addons with just a datagen time compile time dependency, meaning outside of dev there is no longer a hard dependency.

## Part Sprite Provider

If you are writing an addon that adds new tools, you will want to create a part sprite provider, extending `AbstractPartSpriteProvider`. The builders in that class will make it easy to add sprites both individually (for tool parts) or for the different pieces of a tool. Each sprite requires a path relative to `assets/<mod_id>/textures/item/tool/`. In addition to a path, each part also has a material stat ID (e.g. head or handle) which will prevent generating parts for materials that are not applicable. For instance, several materials in Tinkers' Construct are binding exclusive, so generating pickaxe head textures for them would not make sense.

If your addon adds new materials, you can reuse the built in one from Tinkers' Construct (`TinkerPartSpriteProvider`) to generate the base set of parts. It also doubles as an example of how to use the abstract class. Note that in order for datagen to actually load textures from the Tinkers' Construct mod jar, you need to add Tinkers' Construct as an existing mod for datagen by adding `'--existing-mod', 'tconstruct'` to your `build.gradle` datagen run configuration `args`. For an example, [see Materialis](https://github.com/RCXcrafter/Materialis/blob/10358fdbc22eb9d952b587eb540246049b50fd2c/build.gradle#L121).

### Generator Part Texture JSON Generator

If you add new part textures, you should use it in an instance of `GeneratorPartTextureJsonGenerator`. This will create a JSON file usable by the texture generator command, allowing modpack and resource pack devs to easily generate textures for your new tools.

## Material Sprite Provider

The material sprite provider lets you define three properties for a material:
* Stat types: determines which sprites will be supported. Most materials will find the shortcut `meleeHarvest` useful.
* Fallbacks: determines which base textures will be used in generation. This primarily affects shading, for instance `"metal"` is a much shinier base than `"rock"`. Note you can define your own base textures as long as you provide the relevant sprites.
* Transformer: Logic to map an uncolored sprite to the desired appearance.

If your addon adds new tools, you will likely want to reuse `TinkerMaterialSpriteProvider` to generate variants of your parts using the Tinkers' materials. It also doubles as an example of this provider.

### Transformers

By default, Tinkers' Construct provides two transformers, `RecolorSpriteTransformer` and `GreyToSpriteTransformer`. However, additional transformers can be registered by implementing `ISpriteTransformer`, allowing more complex behavior to be described. Ultimately, transformers have access to the full ARGB values of the base sprite, along with any number of additional sprites you wish to include.

#### `RecolorSpriteTransformer`

This transformer simply repalettes a texture pixel by pixel, using a mapping defined in an `IColorMapping`. Since this transformer is used so often, the builder provides a shortcut taking an `IColorMapping` as a parameter.

One default `IColorMapping` is provided, `GreyToColorMapping`. This works by by mapping grey values (`[0, 255]`) to ARGB values (`0xAARRGGBB`). All default tool textures in the mod use a six color palette with grey values at 63, 102, 140, 178, 216, and 255, so providing colors for each of those is ideal. If a grey value outside the palette is detected, some interpolation between color values will be performed, meaning technically a palette with just 2 colors would be sufficient.

#### `GreyToSpriteTransformer`

This transformer is an extension of `GreyToColorMapping`, with the ability to define a texture for a given grey value in addition to colors. If provided (relative to `assets/<mod_id>/textures/`), that texture will be used for each given X, Y location in the tool. Note that large tools use 32x textures. If the texture provided is smaller than the size needed for the part, it will be tiled.

### Material Render Info Provider

In addition to generating part textures, `AbstractMaterialRenderInfoProvider` accepts an optional `AbstractMaterialSpriteProvider` argument. This will provide you with two useful features in your render info:

* Matching materials will automatically get their color set from your palette, along with getting their fallbacks set
* The render info will be populated with `"generator"` information for the sake of the texture generator command.

It is strongly advised you use this generator if you plan to use material texture generators.