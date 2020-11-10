import crafttweaker.item.IItemStack;
import crafttweaker.item.IIngredient;

function addProcessing(input as IItemStack, output as IItemStack)
{
	//#region Smelting
	// furnace.addRecipe(IItemStack output, IIngredient input);
	furnace.addRecipe(output, input);
	// mods.mekanism.smelter.addRecipe(IIngredient inputStack, IItemStack outputStack);
	mods.mekanism.smelter.addRecipe(input, output);
	//#endregion Smelting

	//#region Crushing
	// mods.mekanism.crusher.addRecipe(IIngredient inputStack, IItemStack outputStack);
	mods.mekanism.crusher.addRecipe(input, output);
	// mods.immersiveengineering.Crusher.addRecipe(IItemStack output, IIngredient input, int energy, @Optional IItemStack secondaryOutput, @Optional double secondaryChance);
	mods.immersiveengineering.Crusher.addRecipe(output, input, 2048);
	// mods.actuallyadditions.Crusher.addRecipe(IItemStack output, IItemStack input, @Optional IItemStack outputSecondary, @Optional int outputSecondaryChance);
	mods.actuallyadditions.Crusher.addRecipe(output, input);
	// mods.extrautils2.Crusher.add(IItemStack output, IItemStack input, @Optional IItemStack secondaryOutput, @Optional float secondaryChance);
	mods.extrautils2.Crusher.add(output, input);
	// mods.thermalexpansion.Pulverizer.addRecipe(IItemStack output, IItemStack input, int energy, @Optional IItemStack secondaryOutput, @Optional int secondaryChance);
	mods.thermalexpansion.Pulverizer.addRecipe(output, input, 20);
	//#endregion Crushing
}

for compressedOre in <ore:oreCompressed*> {
	val normalOreName = "ore" ~ compressedOre.name.substring("oreCompressed".length);
	if (oreDict has normalOreName) {
		val normalOre = oreDict.get(normalOreName);

		for compressedOreItem in compressedOre.items {
			addProcessing(compressedOreItem, normalOre.firstItem * 3);
		}
	}
}

for netherOre in <ore:oreNether*> {
	val normalOreName = "ore" ~ netherOre.name.substring("oreNether".length);
	if (oreDict has normalOreName) {
		val normalOre = oreDict.get(normalOreName);

		for netherOreItem in netherOre.items {
			addProcessing(netherOreItem, normalOre.firstItem * 2);
		}
	}
}

for endOre in <ore:oreEnd*> {
	val normalOreName = "ore" ~ endOre.name.substring("oreEnd".length);
	if (oreDict has normalOreName) {
		val normalOre = oreDict.get(normalOreName);

		for endOreItem in endOre.items {
			addProcessing(endOreItem, normalOre.firstItem * 2);
		}
	}
}
