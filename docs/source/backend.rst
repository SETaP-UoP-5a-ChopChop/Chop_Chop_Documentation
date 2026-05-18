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

The **Pantry Manager** also interacts with the FATSECRET API to convert the data received from the API into a format that can be easily used by the frontend.

The pantry manager's **Ingredient Class** defines an ingredient with the following attributes:

- ID: A unique identifier for the ingredient.

- Name: The name of the ingredient.

- Calories: The number of calories in the ingredient.

- Protein: The amount of protein in the ingredient.

- Carbs: The amount of carbohydrates in the ingredient.

- Fat: The amount of fat in the ingredient.

- Serving Size: The recommended serving size for the ingredient.

The **from_fatsecret** method within the Ingredient Class is responsible for converting the data received from the FATSECRET API into an instance of the Ingredient class. It takes the API response as input and extracts the relevant information to populate the attributes of the Ingredient instance. This allows the application to easily utilize the ingredient data in a consistent format across the frontend and backend.
This method works for most API responses, but edge cases such as image and barcode search results may require additional handling to ensure that the data is correctly parsed and converted into the Ingredient class format.

**PantryItemIn**, **PantryItemOut**, and **ImageScanResult** Classes are used to manage the pantry items and image scan results and define the structure of the data that is sent to and received from the frontend. They ensure that the data is properly formatted and can be easily used by the frontend to display pantry information and image scan results to the user.

**auto_complete_search** method is responsible for providing auto-complete suggestions for ingredient names based on user input. It interacts with the FATSECRET API to retrieve a list of ingredients that match the user's input and returns the suggestions in a format that can be easily used by the frontend to display the auto-complete options to the user.

**scan_image** method is responsible for handling image scanning functionality. It takes a base64-encoded image as input, interacts with the FATSECRET API to analyze the image and extract relevant information about the ingredients present in the image. The method then returns the results in a format that can be easily used by the frontend to display the scanned ingredient information to the user.
This function is depreciated and may not work as expected due to changes in the FATSECRET API. It is recommended to use the auto_complete_search method for ingredient search functionality instead of relying on image scanning.

**delete_from_pantry** method is responsible for deleting an ingredient from the user's pantry. It takes the ingredient ID and the user ID as input, interacts with the database to remove the specified ingredient from the user's pantry, and returns a response indicating whether the deletion was successful or if any errors occurred during the process. This allows users to easily manage their pantry inventory by removing ingredients they no longer have or need.

**add_to_pantry** method is responsible for adding an ingredient to the user's pantry. It takes the ingredient information as an Ingredient object and the user ID as input, interacts with the database to store the new ingredient in the user's pantry, and returns a response indicating whether the addition was successful or if any errors occurred during the process. This allows users to easily manage their pantry inventory by adding new ingredients they have acquired or want to keep track of.

**get_pantry** method is responsible for retrieving the user's pantry information. It takes the user ID as input, interacts with the database to fetch the list of ingredients in the user's pantry, and returns the pantry information in a format that can be easily used by the frontend to display the pantry contents to the user. This allows users to view and manage their pantry inventory effectively.

----------------

Recipe Manager
----------------
The **Recipe Manager** is responsible for managing recipes within the application. It allows users to search for recipes based on ingredients, save their favorite recipes, and view recipe details. The manager interacts with the database to store and retrieve recipe information, ensuring that users can easily access and manage their recipes.

----------------

Shopping List Manager
---------------------
The **Shopping List Manager** is responsible for managing the user's shopping list. It allows users to add, update, and delete items from their shopping list. The manager interacts with the database to store and retrieve shopping list information, ensuring that users can easily manage their shopping needs.
