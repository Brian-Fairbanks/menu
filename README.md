# Menu

The start of a simple menu creation/grocery shopping list application

## Settings

This can start as a simple JSON file for now, but will likely need to expand to on the fly changes later on.

number of people - 2 for now
prefered stores
basic schedule - prefer overnight breakfasts for weekdays: mon and fri have option to cook fast/easy meals for lunch. Sandwiches, for example

## Recipe Storage

The goal of this application is to keep a store of recipes, likely stored as .json files. This json can maintain lists of instructions to be maintained as necissary, changes to be stored over time as recipes change, a list of ingrediants, and their aproximate weight, and a number of servings made from the recipe list, and predicted calories and macros.

Some meals do not reheat well, or are particularly costly, and this should be kept in mind for only once a week things. Our weekly steak dinner for example, or a specialty fish dinner.

Tags and or settings can be added, as well for:
Breakfast, lunch, dinner, overnight prep, vegiterian, keto, ect

Basic recipe scaling to match ammounts required for the base set number of people.
Change Log: Tracking recipe changes over time is a great feature! Consider versioning recipes, with the ability to revert to or compare previous iterations.

## Simple scheduling

This will likely need to start as hardcoded preferences in the settings, and expanded for easier functionality later on.
prefer overnight breakfasts for weekdays: mon and fri have option to cook fast/easy meals for lunch. Sandwiches, for example

## Meal Selection Process

The end goal of the app is to offer a suggested set of meals, and an ability to select between them- perhaps suggest 10 meals for the week, and let me pick a few of them.

Use the recipes/ingredient lists to generate a shopping list, and utilize a set of rules to attempt to add suggestions for a better list:
if my choice only uses 1 lb of chicken, know that it is difficult at HEB to get a single lb. I would want to suggest that an extra chicken meal would help with less food waste, and suggest adding another meal that would be easy to pick up.

    Use reccomended diet plans to suggest healthier eating habbits.  Compare macros of the meals, and make sure that, for example, im not choosing 60% meats for every meal.  Suggest options that would help to round out

My general method, for which makes other similar options difficult for me, is that I like to do a short set of meal prep - I want the ability to cook one meal nightly, and then have leftovers for the next day: so i generally prefer to pick 5 meals a week, anticipating at least a few events in the week that will require eating out.

Some meals do not reheat well, or are particularly costly, and this should be kept in mind for only once a week things. Our weekly steak dinner for example, or a specialty fish dinner. When this becomes a thing, suggest a simple meal for a monday or friday dinner.

Utilize the meal choices to make a grocery list for the weeks selections

Meal Balancing: Offer a visual breakdown of the week's macros and suggest swaps for more balanced nutrition.

Favorite recipes - if used regularly, suggest them regularly. If used commonly at one point, but not recently, try to suggest them again more often. This balance will likely be difficult to quantify, and will need further expansion and brainstorming when implemented.

EX: my wife and I love steak, and we usually have it every friday, but for the last few weeks we have chosen to skip it. Maybe suggest it again in a few weeks.

Thoughts for the future:
Customizable Diet Plans: Let users adjust the algorithm to favor certain diet styles (e.g., low-carb, high-protein).
Event Awareness: Incorporate a calendar to anticipate events where eating out is likely, adjusting the meal plan accordingly.

## Pantry Utilization

create a simple method of managing what we already have:
Before suggesting meals, request a quick fridge check. Common pantry staples like salt, pepper, and spices can be automatically excluded from recipes, but there should be some way to indicate when running low, so a bluk purchase can be added to the weekly shopping list

later in scope thoughts.
Allow users to track what's already in their pantry, auto-updating quantities when recipes are made.
Suggest recipes that use ingredients close to expiration to minimize waste.
Incorporate a “use what you have” mode for budget-conscious users.

## Grocery List

Take a look at the total recipes, and amount of people (the people should have an easy to change default, which in my case will start at 2), and generate a list of ingredients that will need to be purchased.

I want the ability to simplify recipies as needed. If a recipe calls for 4.5oz red bell pepper for example, round and add '1/2 small bell pepper' to the list, given that a bell pepper is between 4-16oz, and 10z would be the average. Round to simplify the shopping list.

In general, round down on unhealthy foods, and up on healther foods. If 1.2 lbs of bacon, add 1lb. If .

This will likely mean we need to build and consult a library of foods as healthy/unhealthy, preconfigured packaging options, ect. or utilize an existing API to pull information about ingredients that are being used in a recipe: like HEB or Targets inventory websites.
Allow users to set preferred stores, and pull real-time pricing and availability from APIs.

Show pricing estimates for the total shopping list

For maximum accuracy, if able to utilize, then we may need a setting for location.
Integrate a “Pantry Check” step to remove items already at home from the shopping list.
Add reminders for common pantry staples or suggest bulk buys for cost efficiency.
