Backend
===================

The **backend** of the application is responsible for data management and communication with the frontend. It consists of several managers that interact with the database and handle various aspects of the application, including user accounts, pantry management, recipe management, and shopping list management.

-------------

Accounts Manager
----------------

The **accounts manager** is responsible for handling user accounts, including registration, authentication, and profile management. It ensures that users can securely create and manage their accounts while providing necessary functionalities such as password recovery and account settings.

----------------

Pantry Manager
----------------
The **Pantry Manager** is responsible for managing the user's pantry inventory. It allows users to add, update, and delete ingredients in their pantry. The manager interacts with the database to store and retrieve pantry information, ensuring that users can keep track of the ingredients they have on hand.
It defines an ingredient with the following attributes:
- ID: A unique identifier for the ingredient.
- Name: The name of the ingredient.
- Calories: The number of calories in the ingredient.
- Protein: The amount of protein in the ingredient.
- Carbs: The amount of carbohydrates in the ingredient.
- Fat: The amount of fat in the ingredient.
- Serving Size: The recommended serving size for the ingredient.
The **Pantry Manager** converts the data recieved from the API into a format that can be easily used by the frontend.

----------------

Recipe Manager
----------------

The **Recipe Manager** is responsible for managing recipes within the application. It allows users to search for recipes based on ingredients, save their favorite recipes, and view recipe details. The manager interacts with the database to store and retrieve recipe information, ensuring that users can easily access and manage their recipes.
----------------

Shopping List Manager
----------------
The **Shopping List Manager** is responsible for managing the user's shopping list. It allows users to add, update, and delete items from their shopping list. The manager interacts with the database to store and retrieve shopping list information, ensuring that users can easily manage their shopping needs.
