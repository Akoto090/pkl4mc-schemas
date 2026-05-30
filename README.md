# pkl4mc-schemas

PKL schema package for [pkl4mc](https://git.akoto.dev/akoto090/pkl4mc), a Minecraft mod that lets you write datapacks and configs in [PKL](https://pkl-lang.org) instead of JSON.

## Schemas

| Schema | Usage |
|---|---|
| `recipes.pkl` | crafting, smelting, blasting, smoking, stonecutting, smithing |
| `recipe_removals.pkl` | remove vanilla/modded recipes |
| `loot_table.pkl` | block, chest, entity, fishing loot tables |
| `advancement.pkl` | advancements |
| `biome.pkl` | biome definitions |
| `configured_feature.pkl` | world generation features |
| `configured_carver.pkl` | world generation carvers |
| `placed_feature.pkl` | placed feature definitions |
| `structure.pkl` | structure definitions |
| `structure_set.pkl` | structure sets |
| `noise_settings.pkl` | noise settings |
| `surface_rules.pkl` | surface rules |
| `tag.pkl` | tags |
| `dimension_type.pkl` |dimension types |

## Usage

1. Add to your `PklProject`:

```pkl
amends "pkl:Project"

dependencies {
["pkl4mc"] { uri = "package://pkg.pkl-lang.org/github.com/Akoto090/pkl4mc-schemas@0.3.2" }
}
```
2. Resolve the pkl project to generate PklProject.deps.json and than start to amend any schema.
```pkl
amends "@pkl4mc/recipes.pkl"

shapeless {
  new {
    name = "sea_pickle_dye"
    category = "misc"
    ingredients { new { item = "minecraft:sea_pickle" } }
    result { item = "minecraft:lime_dye" }
  }
}
```
3. Place .pkl files in your datapack under data/<namespace>/ and load them with the pkl4mc mod at

## Requirements
- pkl4mc lib installed (mod)
- PKL CLI or just IDE plugin for editing
