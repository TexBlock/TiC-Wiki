There are a few things to note when creating a Resource Pack for Tinkers' Construct.
It is possible to have custom textures for every material, but I advise against it since all simple materials reuse textures and therefore save the already limited texture space in Minecraft 1.8.
Furthermore animated textures should also be kept at a minimum for the same reason and because each additional animated texture actually decreases performance.

### Material Textures:
* There is a base texture for every toolpart, which will be colored or used to generate the other textures
* There are additional base textures (currently only contrast) which are used instead of the base texture for some materials
* Each material can have a custom texture by appending a _materialid suffix to the texture name. E.g. "axe_head_flint". Material IDs usually match the english name in lowercase.

### GUI Textures:
* Tinkers generates outline textures to use in some GUIs.
* Since the outlines are only 1 pixel thick they are missing parts when scaled down through GUI size, when using bigger textures
* Outlines per part can be provided by adding textures for the "_internal_gui" material. E.g. "axe_head__internal_gui"
* Note that there's a double _ in that name.

### Fluid Textures:
* Fluids are all colored textures for performance and simplicity reasons
* You cannot provide specific textures for a fluid