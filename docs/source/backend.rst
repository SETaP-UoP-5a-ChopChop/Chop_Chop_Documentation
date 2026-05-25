Backend
===================

The **backend** of the application is responsible for data management and communication with the frontend. It consists of several managers that interact with the database and handle various aspects of the application, including user accounts, pantry management, recipe management, and shopping list management.

-------------

Accounts Manager
----------------

The **Accounts Manager** is responsible for handling user authentication and account management within the application. It allows users to register, log in, reset passwords, and securely manage their account credentials. The manager interacts with the database to store and retrieve user information while ensuring that passwords are securely encrypted using bcrypt hashing.

The **Accounts Manager** uses several request models to define and validate the structure of data received from the frontend. These models ensure that all account-related requests are properly formatted before being processed by the backend.

The **Accounts Manager**’s request classes include:

- **LoginRequest**: Defines the data required for a user to log in. It includes:
    - Email
    - Password
- **RegisterRequest**: Defines the data required when a new user registers an account. It includes:
    - Username
    - Email
    - Password
- **ForgotPasswordRequest**: Defines the data required when a user requests a password reset. It includes:
    - Email
- **ResetPasswordRequest**: Defines the data required when resetting a password. It includes:
    - Email
    - New Password
    - Confirm Password

The **get_user_by_email** method is responsible for retrieving a user from the database using their email address. It opens a database connection, executes a query to search for the user, and returns the matching user record if one exists. This method is used throughout the Accounts Manager to verify user existence during login, registration, and password reset operations.

The **create_user** method is responsible for creating a new user account in the database. Before storing the password, the method securely hashes it using bcrypt encryption to ensure sensitive user data is protected. The method then inserts the new user into the database and returns the created user’s information. If the email already exists or a database error occurs, an appropriate HTTP error response is returned.

The **verify_password** method is responsible for validating a user’s login credentials. It compares the plain-text password entered by the user with the hashed password stored in the database using bcrypt’s secure password comparison functionality. This ensures that passwords are never stored or compared in plain text.

The **login_user** method is responsible for authenticating a user during login. It searches the database for a user with the provided email address and verifies that the entered password matches the stored hashed password. If the credentials are valid, the method returns the user’s information; otherwise, it returns a failed login response.

The **update_user_password** method is responsible for updating a user’s password in the database. The new password is securely hashed before being stored. The method updates the password for the matching email address and returns the number of affected database rows to indicate whether the operation was successful.

The **hash_password** helper method is responsible for generating a secure bcrypt hash from a plain-text password. This helper function centralizes password hashing functionality to ensure consistency and security throughout the Accounts Manager.

The **Accounts Manager** also defines several API routes that allow the frontend to interact with the authentication system:
- **register** endpoint is responsible for creating a new user account. It validates the registration data, checks if the email is already registered, creates the user in the database, and returns a success response containing the user information.
- **login** endpoint is responsible for authenticating existing users. It verifies the provided email and password against the stored database records and returns a successful login response if the credentials are correct. If authentication fails, an unauthorized error response is returned.
- **forgot_password** endpoint is responsible for verifying whether a user account exists for a provided email address. If the email exists, the endpoint returns a response allowing the user to proceed with the password reset process. In a production environment, this endpoint would typically trigger a password reset email.
- **reset_password** endpoint is responsible for securely updating a user’s password. It validates that the new password and confirmation password match, checks that the user exists, updates the password in the database, and returns a success response once the password has been changed successfully.

Overall, the **Accounts Manager** ensures secure authentication and user account management by combining database operations, password encryption, validation models, and API endpoints into a centralized authentication system that can be reliably used by both the frontend and backend of the application.
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
