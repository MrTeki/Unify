<div style="text-align:center">
  <img src="https://cdn.modrinth.com/data/cached_images/47a9eed7f66a24dfa587d984c2f125d7087a168f.png" alt="Unify's icon">
</div>

---

https://modrinth.com/mod/unify

### Unify Mod for Minecraft

The "Unify" Minecraft mod is designed to simplify gameplay by reducing item duplication. Here's a breakdown of how it works and its configuration options:

#### How It Works

- **Item Unification**: The mod uses regex to search for items whose paths match specific patterns. Items are unified if they have the same path or belong to the same group of paths. If it finds duplicates, it selects one as the unified version and removes the others from various game elements like loot tables, tags, recipes, creative tabs, and REI (Roughly Enough Items mod).

- **Inheritance**: The unified version inherits tags, recipes, etc., from its duplicate versions, ensuring that functionality is preserved.

- **Creative Tab**: You can find duplicate items in the Unify creative tab, with a tooltip indicating the unified version.

- **Replace on Right-Click**: Duplicate items can be replaced with their unified version by right-clicking them.

- **Unification Recipes**: Crafting recipes are added to replace duplicates with their unified version.

#### Configuration

The mod is highly configurable, allowing you to customize which items are unified and how duplicates are identified. Here's a detailed look at the configuration options:

- **globalSearch**: This section allows you to set global rules for identifying duplicate items.

  - **itemsToIgnore**: List of items that the mod will ignore. These items won't be unified or considered duplicates.
    ```json
    "itemsToIgnore": [
      "examplemod:lead_block"
    ]
    ```

  - **namespacePriorities**: A prioritization list of namespaces. The mod will favor items from these namespaces in the order they appear to be the unified version.
    ```json
    "namespacePriorities": [
      "techreborn",
      "modern_industrialization"
    ]
    ```

  - **pathStartsWith**: Specifies patterns that the start of the item identifier path must match. This can be a string or a list of strings. When a list is provided, items matching any of the patterns in the list will be grouped together.
    ```json
    "pathStartsWith": [
      "raw_"
    ]
    ```

  - **pathEndsWith**: Specifies patterns that the end of the item identifier path must match. This can be a string or a list of strings. When a list is provided, items matching any of the patterns in the list will be grouped together.
    ```json
    "pathEndsWith": [
      "_ore",
      [
        "_block",
        "_storage_block"
      ],
      "_ingot",
      "_nugget",
      "_dust",
      "_plate",
      "_rod",
      "_gear"
    ]
    ```

- **itemsToUnify**: This section allows you to manually specify which items should be unified. The key is the unified item, and the value is an array of duplicate items.
  ```json
  "itemsToUnify": {
    "modern_industrialization:lead_block": [
      "techreborn:lead_storage_block"
    ]
  }
  ```

- **replaceOnUse**: Allows replacing duplicate items with their unified version by right-clicking.
  ```json
  "replaceOnUse": true
  ```

- **generateUnificationRecipes**: Adds crafting recipes to replace duplicates with their unified version.
  ```json
  "generateUnificationRecipes": true
  ```

- **hideDuplicatesInItemGroups**: Hide duplicates in Creative Item Groups.
  ```json
  "generateUnificationRecipes": true
  ```

- **hideDuplicatesInRecipeViewers**: Hide duplicates in recipes viewers (REI, JEI, ...).
  ```json
  "generateUnificationRecipes": true
  ```

#### Example Configuration

Here's an example configuration that demonstrates how you might set up the mod:

```json
{
  "globalSearch": {
    "itemsToIgnore": [
      "examplemod:lead_block"
    ],
    "namespacePriorities": [
      "techreborn",
      "modern_industrialization"
    ],
    "pathStartsWith": [
      "raw_"
    ],
    "pathEndsWith": [
      "_ore",
      [
        "_block",
        "_storage_block"
      ],
      "_ingot",
      "_nugget",
      "_dust",
      "_plate",
      "_rod",
      "_gear"
    ]
  },
  "itemsToUnify": {
    "modern_industrialization:lead_block": [
      "techreborn:lead_storage_block"
    ]
  },
  "replaceOnUse": true,
  "generateUnificationRecipes": true,
  "hideDuplicatesInItemGroups": true,
  "hideDuplicatesInRecipeViewers": true
}
```

This configuration ensures that items like `raw_iron` from different mods are unified according to the specified patterns and priorities, while `examplemod:lead_block` is ignored. Items like `iron_block` and `iron_storage_block` will be grouped together, with one being the unified version and the other a duplicate.

By customizing these settings, you can tailor the mod to fit your specific needs and preferences, streamlining your Minecraft gameplay experience.

---
