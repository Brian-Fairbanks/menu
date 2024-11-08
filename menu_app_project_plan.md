
# Menu App - Project Plan

## Project Overview

The primary goal for the initial iteration:

- **Recipe Structure**: Create a system to store and manage recipes.
- **Recipe Scaling/Suggestions**: Implement scaling of recipes based on the number of people.
- **Grocery List Generation**: Generate a grocery list from selected recipes.
- **Favorite Recipes**: Keep track of recipe usage to suggest favorites.

---

## Proposed Plan of Attack

### 1. Project Structure

Organize your project into the following directories and files:

```
menu_app/
│
├── data/
│   ├── recipes/
│   │   ├── recipe1.json
│   │   ├── recipe2.json
│   │   └── ...
│   ├── pantry.json
│   ├── settings.json
│   └── staples.json
│
├── main.py
├── models/
│   ├── __init__.py
│   ├── recipe.py
│   ├── ingredient.py
│   ├── grocery_list.py
│   ├── pantry.py
│   └── user_preferences.py
│
├── services/
│   ├── __init__.py
│   ├── recipe_manager.py
│   ├── menu_planner.py
│   ├── grocery_list_generator.py
│   └── suggestion_engine.py
│
└── utils/
    ├── __init__.py
    ├── file_io.py
    └── scaling.py
```

---

### 2. Core Components and Classes

#### a. Models (Data Structures)

- **Recipe**
  - Attributes:
    - `name`
    - `ingredients` (list of `Ingredient` objects)
    - `instructions`
    - `servings`
    - `nutrition_info` (calories, macros)
    - `tags` (e.g., breakfast, vegetarian)
    - `reheatability_score` (for meal planning)
    - `cost_estimate`
    - `usage_history` (timestamps of when the recipe was used)
  - Methods:
    - `scale_recipe(factor)`
    - `update_usage_history()`
    - Stubs for future features (e.g., `versioning`, `compare_versions`)

- **Ingredient**
  - Attributes:
    - `name`
    - `quantity`
    - `unit` (e.g., grams, ounces)
    - `is_staple` (boolean)
    - `healthy_score` (for grocery list adjustments)
    - `packaging_info` (common packaging sizes)
  - Methods:
    - `adjust_quantity(factor)`
    - Stubs for future features (e.g., `fetch_nutrition_info()`)

- **GroceryList**
  - Attributes:
    - `items` (dictionary of ingredients and required quantities)
    - `store` (from user preferences)
  - Methods:
    - `generate_from_recipes(recipes_list)`
    - `simplify_quantities()`
    - `remove_pantry_items(pantry)`
    - Stubs for future features (e.g., `fetch_store_prices()`)

- **Pantry**
  - Attributes:
    - `items` (ingredients and their quantities)
  - Methods:
    - `update_pantry(used_ingredients)`
    - `check_staples()`
    - Stubs for future features (e.g., `track_expiration_dates`)

- **UserPreferences**
  - Attributes:
    - `number_of_people`
    - `preferred_stores`
    - `meal_schedule` (preferences for meal types on certain days)
  - Methods:
    - `load_preferences()`
    - `save_preferences()`

---

#### b. Services (Business Logic)

- **RecipeManager**
  - Responsibilities:
    - Load and save recipes.
    - Search and filter recipes based on tags and other criteria.
    - Manage favorite recipes (track usage and suggest accordingly).
    - Stubs for future features (e.g., `import_export_recipes`)

- **MenuPlanner**
  - Responsibilities:
    - Generate meal suggestions based on user preferences and recipe data.
    - Implement logic for suggesting additional meals to reduce waste.
    - Adjust meal plans to avoid repetition and balance nutrition.
    - Stubs for future features (e.g., `event_integration`, `dietary_customizations`)

- **GroceryListGenerator**
  - Responsibilities:
    - Collate ingredients from selected recipes.
    - Simplify quantities and adjust for healthy/unhealthy foods.
    - Generate the final grocery list, excluding pantry staples.
    - Stubs for future features (e.g., `optimize_shopping_route`)

- **SuggestionEngine**
  - Responsibilities:
    - Analyze recipe usage history to suggest favorites.
    - Balance suggestions between frequently used and less recent recipes.
    - Stubs for future features (e.g., `machine_learning_recommendations`)

---

#### c. Utilities

- **FileIO**
  - Responsibilities:
    - Handle reading from and writing to JSON files.
    - Manage file paths and data integrity checks.

- **Scaling**
  - Responsibilities:
    - Provide functions to scale ingredient quantities.
    - Adjust recipes based on the number of servings.

---

### 3. Development Steps

1. **Set Up Project Structure**
   - Create directories and placeholder files as per the structure.

2. **Implement Data Models**
   - Define the `Recipe` and `Ingredient` classes with necessary attributes and basic methods.
   - Ensure they can serialize and deserialize from JSON.

3. **Load and Manage Recipes**
   - Develop the `RecipeManager` service to load recipes from the `data/recipes/` directory.
   - Implement searching and filtering capabilities.

4. **Recipe Scaling**
   - Use the `Scaling` utility to adjust recipes based on the number of people.
   - Integrate scaling into the recipe selection process.

5. **Grocery List Generation**
   - Implement the `GroceryList` class to collect ingredients.
   - Develop the `GroceryListGenerator` to process selected recipes and generate the list.
   - Include logic to simplify quantities and adjust for healthiness.

6. **Pantry Integration**
   - Create a basic `Pantry` class to store staples and current inventory.
   - Adjust the grocery list by removing pantry items.

7. **Favorite Recipes Tracking**
   - Update the `Recipe` class to track usage history.
   - Implement methods in `SuggestionEngine` to analyze and suggest recipes.

8. **User Preferences**
   - Implement the `UserPreferences` class to handle settings.
   - Load preferences at the start and save any changes.

---

### 4. Future Stubs and Expansion Points

- **Versioning in Recipes**
  - Add placeholders in the `Recipe` class for version control methods.
  
- **API Integration**
  - In `GroceryListGenerator`, include stubs for future API calls to stores for pricing and availability.
  
- **Advanced Suggestion Algorithms**
  - In `SuggestionEngine`, plan for incorporating more advanced algorithms or machine learning for recipe suggestions.
  
- **Pantry Management Enhancements**
  - In `Pantry`, add methods for tracking expiration dates and quantities for future implementation.
  
- **Event Awareness and Calendar Integration**
  - In `MenuPlanner`, include placeholders for integrating with calendar events.

---

### 5. Considerations for Code Organization

- **Modularity**: Keep classes and functions focused on single responsibilities to make future testing and maintenance easier.
  
- **Data Persistence**: Ensure that reading from and writing to JSON files is handled gracefully, with error checking and data validation.
  
- **Extensibility**: Design classes and methods with extensibility in mind, so new features can be added with minimal refactoring.
  
- **User Interface**: For the initial iteration, interaction might be via the console or simple command-line prompts. Plan for potential GUI development later.

---

## Summary

By structuring your project with clear separation of concerns, you set a solid foundation for future expansion. Starting with the core functionality—recipe management, scaling, and grocery list generation—you can build a working prototype that meets your immediate needs while keeping the door open for enhancements.
