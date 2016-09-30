There are a few things to note when creating a Resource Pack for Tinkers' Construct.
It is possible to have custom textures for every material, but I advise against it since all simple materials reuse textures and therefore save the already limited texture space in Minecraft 1.8.
Furthermore animated textures should also be kept at a minimum for the same reason and because each additional animated texture actually decreases performance.

### Material Textures:
* **Starting with 2.5.3 the automatically generated textures are defined in the resources!**
* There is a base texture for every toolpart, which will be colored or used to generate the other textures
* There are additional base textures (currently only contrast) which are used instead of the base texture for some materials
* Each material can have a custom texture by appending a _materialid suffix to the texture name. E.g. "axe_head_flint". Material IDs usually match the english name in lowercase.
* Some materials use block textures during their generation. In that case it's enough to provide a texture for the block. So if your resource pack has a new netherrack texture, the parts will automatically use it.

### GUI Textures:
* Tinkers generates outline textures to use in some GUIs.
* Since the outlines are only 1 pixel thick they are missing parts when scaled down through GUI size, when using bigger textures
* Outlines per part can be provided by adding textures for the "_internal_gui" material. E.g. "axe_head__internal_gui"
* Note that there's a double _ in that name.

### Fluid Textures:
* Fluids are all colored textures for performance and simplicity reasons
* You cannot provide specific textures for a fluid

### Material Texture Generators:
There are several algorithms implemented in TiC, that are used to automatically generate the tool textures from the base textures, which are present in png format. You can find them in the materials folder, the filename being the material identifier. Each file has a type, defining the generator, and can have a suffix if another base texture should be used. For parameters see existing files. If you encounter a type not listed here means that an addon adds its own generators, which will only work when the addon is present!

Available Generators (case sensitive):
* **colored** - This is the default, just colors the texture. This does not actually create a new texture in the texturemap, reducing vram required
* multicolor - Uses a different color for dark-, bright- and mid-tones
* inverse_multicolor - The negative of multicolor
* block - Generates the tools from a block-texture
* metal - Colors the texture, but processes the texture brightness with different parameters, to achieve a more shiny/metallic look
* metal_texture - Same as metal with an additional texture added into the mix