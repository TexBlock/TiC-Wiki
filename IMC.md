Tinkers' Construct allows you to integrate your mod partially through IMCs. This page contains the supported IMCs and how to use them.

**ALL IMCs HAVE TO BE SENT DURING PREINIT**

## Melting and casting your metal in the Smeltery

The integration works via Oredict, so everything has to be oredicted. You just supply the liquid and the Oredict-suffix.

    // create fluid.
    // You don't need to add textures for the fluid, just create a Fluid Class that overwrites getColor
    // and pass the following as still and flowing ResourceLocation:
    // still:  "tconstruct:blocks/fluids/molten_metal"
    // flowing: "tconstruct:blocks/fluids/molten_metal_flow"
    Fluid myFluid = new Fluid("myFluid", new ResourceLocation("tconstruct:blocks/fluids/molten_metal"), new ResourceLocation("tconstruct:blocks/fluids/molten_metal_flow"));
    FluidRegistry.registerFluid(myFluid); // fluid has to be registered
    FluidRegistry.addBucketForFluid(myFluid); // add a bucket for the fluid

    // add block for fluid (if desired)
    Block fluidBlock = new BlockFluidClassic(myFluid, Material.lava);
    // <register block regularly>

    // create NBT for the IMC
    NBTTagCompound tag = new NBTTagCompound();
    tag.setString("fluid", myFluid.getName()); // name of the fluid
    tag.setString("ore", "Foo"); // ore-suffix: ingotFoo, blockFoo, oreFoo,...
    tag.setBoolean("toolforge", true); // if set to true, blockFoo can be used to build a toolforge
    //tag.setTag("alloy", alloysTagList); // you can also send an alloy with the registration (see below)

    // send the NBT to TCon
    FMLInterModComms.sendMessage("tconstruct", "integrateSmeltery", tag);

## Adding Alloys

You can add alloys by sending an IMC with its components. The IMC consists of a list of FluidStacks, where the first entry is the output, and the remaining ones are the input to create the alloy.
The list is an NBTTagList and has to contain at least 3 entries (1 out, 2 in).
You can register alloys without knowing if all needed fluids exist. If one is missing, the alloy wont be added.

    NBTTagList tagList = new NBTTagList();
    // if you have access to the fluid-instance you can also do FluidStack.writeToNBT
    NBTTagCompound fluid = new NBTTagCompound();
    fluid.setString("FluidName", "bronze");
    fluid.setInteger("Amount", 144); // 144 = 1 ingot
    tagList.appendTag(fluid);
    // first alloy fluid
    fluid = new NBTTagCompound();
    fluid.setString("FluidName", "copper");
    fluid.setInteger("Amount", 108); // 3/4 ingot
    tagList.appendTag(fluid);
    // second alloy fluid
    fluid = new NBTTagCompound();
    fluid.setString("FluidName", "tin");
    fluid.setInteger("Amount", 36); // 1/4 ingot
    tagList.appendTag(fluid);

    NBTTagCompound message = new NBTTagCompound();
    message.setTag("alloy", tagList);
    FMLInterModComms.sendMessage("tconstruct", "alloy", message);


## Melting Blacklist

Tinkers automatically adds melting for items that are built out of other items that it can melt. In some cases this is not desired, usually because there are alternate ways of crafting said item, resulting in a dupe.
This IMC allows you to prevent specific items from being melted down.

    // blacklist IMC supports Itemstack (incl. wildcard) or Oredict-String
    // You cannot blacklist ingots, blocks, ores, and a few other selected general item types
    FMLInterModComms.sendMessage("tconstruct", "blacklistMelting", new ItemStack(Blocks.wool, 1, OreDictionary.WILDCARD_VALUE));
    FMLInterModComms.sendMessage("tconstruct", "blacklistMelting", "specialItemUnobtanium);

## Drying Rack Integration

You can add a drying rack recipe via IMC. Input can either be an itemstack, or an oredictionary entry. Time is given in seconds.

Via Itemstack:

    // Adding it via Itemstack: Turns vanilla gold ore into a gold block in 3 minutes
    NBTTagCompound tagCompound = new NBTTagCompound();
    tagCompound.setTag("input", new ItemStack(Blocks.GOLD_ORE).writeToNBT(new NBTTagCompound()));
    tagCompound.setTag("output", new ItemStack(Blocks.GOLD_BLOCK).writeToNBT(new NBTTagCompound()));
    tagCompound.setInteger("time", 60*3);
    FMLInterModComms.sendMessage(Util.MODID, "addDryingRecipe", tagCompound);

Via oredict:

    // Adding it via oredict: Turns all iron ore oredicts into iron blocks in 3 minutes
    NBTTagCompound tagCompound = new NBTTagCompound();
    tagCompound.setString("input", "oreIron");
    tagCompound.setTag("output", new ItemStack(Blocks.IRON_BLOCK).writeToNBT(new NBTTagCompound()));
    tagCompound.setInteger("time", 60*3);
    FMLInterModComms.sendMessage(Util.MODID, "addDryingRecipe", tagCompound);