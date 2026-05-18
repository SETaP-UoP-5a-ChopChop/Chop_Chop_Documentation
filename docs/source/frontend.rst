Frontend
====================

The frontend of **ChopChop** is built using **React Native**, a JavaScript library for building user interfaces. It is responsible for delivering an intuitive, responsive, and user-friendly experience across the application.

The frontend communicates with the backend API to retrieve data, process user actions, and keep the interface updated in real time.

Each individual screen is stored as its own file within the frontend folder, allowing for a clean project structure and seamless navigation between pages.

-----------------------------------

Main Features
-------------

The frontend provides access to the following core features:

- Recipe Search  
- Saved Recipes  
- Pantry Management  
- Shopping List  
- User Accounts  
- Settings & Preferences  

-----------------------------------

Index
------

The **Index page** acts as the home page of the application and serves as the main navigation hub for users.

From this screen, users can quickly navigate to:

- **Recipe Search Page**
- **Saved Recipes Page**
- **Pantry Page**
- **Shopping List Page**

-----------------------------------

Settings Menu
-------------

Users can also navigate to the **Settings Page** via the burger menu located in the top-right corner of the screen.

From the settings page, users are able to:

- View account information
- Manage preferences
- Update profile settings
- Access additional app options

The intention of this page is to provide users with easy access to their account settings and preferences, with this information being used to personalize the user experience while recipe searching and meal planning. However, the current implementation may not fully utilize the user account information for personalization, and users may need to manually adjust their preferences for now to enhance their experience.

This file uses functions from backend file **Accounts Manager**

-----------------------------------

Recipe Search
----------------
The **Recipe Search** feature allows users to search for recipes based on an ingredient they want to use when cooking. Users can enter keywords to find recipes that match their needs.
The search results are displayed in a list format, showing the recipe name, a brief description, and an image. Users can click on a recipe to view more details, including the ingredients required and step-by-step cooking instructions.
Once a user finds a recipe they like, they can save it to the **Saved Recipes** page for easy access later. This feature helps users discover new recipes and make the most of the ingredients they have on hand.


The intention of this page is to suggest recipes and allow users to easily search for recipes based on the ingredients they have in their pantry, making meal planning more efficient and reducing food waste. However, the current implementation may not fully utilize the pantry information for recipe search, and users may need to manually enter ingredients for now to find relevant recipes.

This file uses functions from backend file **Recipe Manager** 

-----------------------------------

Saved Recipes
-----------------------------------
The **Saved Recipes** page allows users to view and manage the recipes they have saved from the search results. Users can see a list of their saved recipes, each displaying the recipe name, a brief description, and an image.
Users can click on a saved recipe to view its details, including the ingredients required and cooking instructions. They also have the option to remove recipes from their saved list if they no longer wish to keep them.
This feature provides users with a convenient way to organize and access their favorite recipes, making it easier to plan meals and try new dishes.


The intention of this page is to allow users to easily access and manage their saved recipes and add their ingredients to the shopping list, making meal planning more efficient. However, the current implementation may not fully utilize the saved recipes for meal planning, and users may need to manually browse their saved recipes for now to find relevant meals.


-----------------------------------------

Pantry
-----------------------
The **Pantry** page allows users to manage their ingredients that they already own. Users can add new ingredients to their pantry, update the quantity of existing ingredients, and remove ingredients they no longer have.
This feature helps users keep track of what they have in their pantry, making it easier to plan meals and avoid unnecessary purchases.
By maintaining an up-to-date pantry, users can make informed decisions when searching for recipes, ensuring they can cook meals with the ingredients they already have on hand.
The pantry page contains a camera icon that intends to allow users to scan images of their ingredients to quickly add them to their pantry. However, this feature is currently not working as expected due to changes in the FATSECRET API, and it is recommended to use the auto-complete search functionality instead for adding ingredients to the pantry.


The intention of this page is to allow users to easily add ingredients to their pantry by either manually entering them or using the image scanning feature. However, due to the current issues with the image scanning functionality, users may need to rely on manual entry for now to keep their pantry updated.

This file uses functions from backend file **Pantry Manager**

-----------------------------------

Shopping List
----------------------
The **Shopping List** page allows users to create and manage a list of ingredients they need to purchase for their recipes. Users can add ingredients to their shopping list, update quantities, and remove items as needed.
This feature helps users stay organized when grocery shopping, ensuring they have all the necessary ingredients for their meals. By keeping a shopping list, users can save time and avoid forgetting important items when they go to the store.
The shopping list can be easily accessed from the main navigation, making it convenient for users to add items while they are planning their meals or browsing recipes.


The intention of this page is to allow users to easily add ingredients from their saved recipes directly to their shopping list, making meal planning and grocery shopping more efficient. However, this functionality is currently not fully implemented, and users may need to manually add items to their shopping list for now.

This file uses functions from backend file **Shopping List Manager**