API
===
The Project Makes Use of 2 APIs:

- **FATSECRET**

- **TheMealDB**

These APIs are used to retrieve information about ingredients, recipes, and nutritional data to provide users with a comprehensive cooking and meal planning experience. The backend of the application interacts with these APIs to fetch the necessary data and deliver it to the frontend for display and user interaction.

-----------------------------------

FATSECRET API
----------------------
The FATSECRET API is communicated with in the pantry manager and the shopping list manager. 

It is used to retrieve information about ingredients, including their nutritional data, and to provide auto-complete suggestions for ingredient names based on user input. 

The pantry manager also uses the FATSECRET API to handle image scanning functionality, allowing users to scan images of their ingredients to quickly add them to their pantry.
However, due to changes in the FATSECRET API, the image scanning functionality may not work as expected, and it is recommended to use the auto-complete search functionality instead for adding ingredients to the pantry.
The FATSECRET API is communicated with VIA a proxy server with IP address http://13.62.210.12:3001/api/ to handle machine restrictions and ensure secure communication between the backend and the API.

-----------------------------------

TheMealDB API
----------------------
TheMealDB API is communicated with in the recipe manager. It is used to retrieve information about recipes, including their ingredients, cooking instructions, and nutritional data.


