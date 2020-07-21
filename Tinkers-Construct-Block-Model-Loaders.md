In Tinkers Construct 1.15, we have several custom model loaders that are used to define data in our tile entity renderers. This page documents those loaders. Unless otherwise stated, all our model loaders support everything available in the [vanilla block model format](https://minecraft.gamepedia.com/Model#Block_models).

## Common elements

The following subsections describe some common elements in our model JSON.

### Model item

A model item describes the placement of an item in the tile entity renderer. This is used in the casting table and basin, along with most of our table blocks. In general, the item should be kept within close proximity to the base model, as the game will stop rendering the items if you look too far away from the base block.

#### Format

* *Object*: Base object
  * `center` (*array*): Center of where to render the model according to the scheme `[x, y, z]`. Must contain exactly 3 elements.
  * `size` (*number*): Size of the model in pixels. 16 would be a full size model.
  * `x` (*number*): Model X rotation in degrees. Must be 0, 90, 180, or 270. If unset, defaults to 0. Applied before Y rotation.
  * `y` (*number*): Model Y rotation in degrees. Must be 0, 90, 180, or 270. If unset, defaults to 0. Applied after X rotation.

#### Example

The following model item:
```json
{
  "center": [ 8, 5, 8 ],
  "size": 2,
  "x": 90
} 
```
Will tell the block to render an item centered at `8,5,8` at a size of 2 pixels, or it will be rendered from `7,4,7` to `9,6,9`. The item will be rotated 90 degrees in the X direction, and 0 degrees in the Y direction.

### Fluid Cuboid

A fluid cuboid is used to specify where a fluid renders within a block. It is used within the casting blocks, casting channel and faucet to determine where the flowing texture is rendered. The rendering logic will automatically choose which fluid texture to render.

#### Format

* *Object*: Base object
  * `from` (*array*): Start point of the cube according to the scheme `[x, y, z]`. Must contain exactly 3 elements.
  * `to` (*array*): End point of the cube according to the scheme `[x, y, z]`. Must contain exactly 3 elements. In general, each coordinate should be larger than the corresponding value in `from`.
  * `faces` (*object*): Object of face data for the cube. If unset, defines all six faces using default values.
    * *A face* (*object*): A single face object. Name will be one of `north`, `east`, `south`, `west`, `up`, or `down`. Any unlisted faces will not show in the model.
      * `rotation` (*number*): Rotation in degrees to apply to the texture on the face. Must be one of 0, 90, 180, or 270. If unset, defaults to 0.
      * `flowing` (*boolean*): If true, this face is rendered with the flowing texture. If false (default), it will use the still texture

#### Example - Default faces

The following JSON:
```json
{
  "from": [ 2, 4, 2 ],
  "to": [ 14, 8, 14 ]
}
```
Defines a simple cube from `2,4,2` to `14,8,14` with all six faces. Faces will have no rotation applied and use the still texture.

#### Example - Face data

The following JSON:
```json
{
  "from": [ 2, 4, 2 ],
  "to": [ 14, 8, 14 ],
  "faces": {
    "up": {},
    "down": { "flowing": false },
    "north": { "flowing": true },
    "south": { "flowing": true, "rotation": 90 }
  }
}
```
Defines a cube at the same location as the first cube. The top and bottom will both have a non-rotated still texture. The north and south both will have flowing textures, rotated 90 degrees on the south. The east and west both will have no texture.

### Incremental Fluid Cuboid

The incremental fluid cuboid is an extension of the fluid cuboid to add one extra key, `increments`. This is used by tank models to determine how to render a partially filled tank. Unlike fluid cuboids, none of the models contain an array of incremental fluid cuboids.

#### Format

* *Object*: Base object
  * *All keys from [fluid cuboid](#fluid-cuboid)*
  * `increments` (*number*): Integer number of fluid increments. In other words, how many different fill values of the model should be generated. Higher values will be more smooth, while lower values will be more efficient when rendering. This key is required.

#### Example

The following JSON:
```json
{
  "from": [ 2, 4, 2 ],
  "to": [ 14, 8, 14 ],
  "increments": 8
}
```
Defines a fluid cuboid as in the previous examples. The cube is 4 pixels tall (as defined by `from` and `to`), so with 8 increments it means every increment is half a pixel.

## Model Loaders

To make use of the elements described on this page, Tinkers Construct includes several model loaders.

### `tconstruct:inventory`

The inventory model loader extends the vanilla block model with a list of [model items](#model-item) for in world display of items in a block. This model is supported by the following blocks, which also serve as examples:
* Crafting Station
* Part Builder
* Tool Station

#### Format

* *Object*: Base object
  * *All keys from [vanilla block models](https://minecraft.gamepedia.com/Model#Block_models)*
  * `items` (*array*): Array of [model item](#model-item) objects. The index of the item in the array corresponds to the slot index in the block
    * *An item* (*object*): A single [model item](#model-item). 

### `tconstruct:fluids`

The fluids model loader extends the vanilla block model with a list of [fluid cuboids](#fluid-cuboid). This model is supported by the following blocks, which also serve as examples:
* Seared Faucet

#### Format

* *Object*: Base object
  * *All keys from [vanilla block models](https://minecraft.gamepedia.com/Model#Block_models)*
  * `fluids` (*array*): Array of [fluid cuboid](#fluid-cuboid) objects. Any number of cuboids can be included.
    * *A fluid cube* (*object*): A single [fluid cuboids](#fluid-cuboid).

### `tconstruct:tank`

The tank model loader contains a scaled fluid cube for rendering any of the tanks in the mod. This model is supported by the following blocks:
* Seared Tank
* Seared Gauge
* Seared Window

#### Format

* *Object*: Base object
  * *All keys from [vanilla block models](https://minecraft.gamepedia.com/Model#Block_models)*
  * `fluid` (*object*): A single [incremental fluid cuboid](#fincremental-fluid-cuboid) object.

### `tconstruct:melter`

The melter model loader extends the tank model loader to also include items. This model is supported by the following blocks:
* Seared Melter

#### Format

* *Object*: Base object
  * *All keys from [vanilla block models](https://minecraft.gamepedia.com/Model#Block_models)*
  * `fluid` (*object*): A single [incremental fluid cuboid](#fincremental-fluid-cuboid) object.
  * `items` (*array*): Array of [model item](#model-item) objects. The index of the item in the array corresponds to the slot index in the block
    * *An item* (*object*): A single [model item](#model-item).

### `tconstruct:casting`

The casting model loader contains a fluid that is scaled. Unlike the tank or melter, this model does not require increments as the item form never contains the fluid. This model is supported by the following blocks:
* Casting Table
* Casting Basin

#### Format

* *Object*: Base object
  * *All keys from [vanilla block models](https://minecraft.gamepedia.com/Model#Block_models)*
  * `fluid` (*object*): A single [fluid cuboid](#fluid-cuboid) object.
  * `items` (*array*): Array of [model item](#model-item) objects. The index of the item in the array corresponds to the slot index in the block
    * *An item* (*object*): A single [model item](#model-item).

### `tconstruct:connected`

The connected model loader is used to allow connected textures on nearly any block. Due to a [Forge bug](https://github.com/MinecraftForge/MinecraftForge/pull/6841), this model does not currently work on models using multipart unless specifically coded, but any other models will work as expected. The following multipart blocks were given special support to work with a connected model:
* Clear Glass Pane
* Stained Clear Glass Pane (all 16 colors)
* Seared Glass Pane

#### Format

* *Object*: Base object
  * *All keys from [vanilla block models](https://minecraft.gamepedia.com/Model#Block_models)*
  * `connection` (*object*): Base object for all connected model keys.
    * `textures` (*array*): Array of texture names to apply connections. Each string must be defined in the model's textures.
      * *A texture key* (*string*): A single texture key in the model.
    * `predicate` (*string*): Resource location of the connection predicate to use for this block. A connection predicate determines when this block is considered connected to a neighbor. Supported values:
      * *default*: If unset, the default predicate is used. This will connect if the neighbor is the same block as this, ignoring all other stats
      * `tconstruct:pane`: This predicate will prevent from connecting a pane with edges to one that is center only and vice versa.

#### Textures

For every key in the `textures` array, texture dependencies are generated in the model. The model will require texture at the following names within a folder with the same name as the base texture: `u`, `d`, `l`, `r`, `ud`, `ul`, `ur`, `dl`, `dr`, `lr`, `udl`, `udr`, `ulr`, `dlr`, `udlr`. The texture at the key will be treated as the texture for no connections, which is also used for item models.

A single texture can also be overridden by defining a texture with the same name as the base, suffixed with an underscore and one of the above names.

#### Example

The following JSON:
```json
{
  "loader": "tconstruct:connected",
  "parent": "block/cube_all",
  "textures": {
    "all": "tconstruct:block/clear_glass",
    "all_udlr": "tconstruct:block/invisible",
  },
  "connection": {
    "textures": [ "all" ]
  }
}
```
Defines a connected model based on the standard 6 sided cube block.

The texture `all` is listed as connected. Since the texture is located in `assets/tconstruct/textures/block/clear_glass.png`, connected children will be in the folder `assets/tconstruct/textures/block/clear_glass/`. For example, the texture for `ul` will be located at `assets/tconstruct/textures/block/clear_glass/ul.png`.

Since the texture `all_udlr` is defined, instead of loading the texture for `udlr` from `assets/tconstruct/textures/block/clear_glass/udlr.png`, it will use `assets/tconstruct/textures/block/invisible.png`.