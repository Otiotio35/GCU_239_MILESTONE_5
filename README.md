Theory of Operation
The StoreFront application facilitates an e-commerce-like experience where users can interact with an inventory, add items to a shopping cart, and make purchases. The application operates with the following major components:

FileService: This is a utility class that handles file read and write operations.

It can read the entire content of a file and return it as a string.
It can write a given string to a file.
InventoryManager: Manages the store's inventory.

Uses FileService to read from and write to the inventory file.
Contains methods to display, add, remove, and purchase items, and sort the inventory by name or price.
The inventory is stored as a map with product names as keys for quick access.
StoreFront: This is the main user interface for the store.

Displays available actions like viewing the inventory, adding items to the cart, checking out, etc.
Uses InventoryManager for inventory-related actions and a ShoppingCart instance for cart-related actions.
Provides user feedback and handles user input through the command line.
ShoppingCart: Represents the user's shopping cart.

Can add items, remove items, view the cart, and calculate the total price.
The items are stored as a map with product names as keys for quick access.
Operational Flow:

The application starts by invoking the StoreFront class's main method.
A welcome message is displayed, and the main menu offers several choices to the user.
When the user opts to view the inventory, the InventoryManager retrieves and displays the list of products.
If the user wants to add an item to the cart, they are prompted for the product's name and quantity. The system checks if the item exists in the inventory and if there are sufficient quantities. If both checks pass, the product is added to the cart.
The user can view their cart at any time, showing the items added and their quantities.
During checkout, the user is shown the cart's contents and the total amount to be paid. They are then asked to confirm the purchase.
If confirmed, the purchase is completed, the cart is cleared, and the inventory is updated.
The application runs in a loop, allowing the user to perform multiple operations until they decide to exit.
In the background, the InventoryManager interacts with the FileService to load the inventory from a file when the application starts and to save changes back to the file when needed.

Error Handling:

Appropriate error messages are displayed in cases of file read/write errors, invalid user input, attempting to purchase more items than available in the inventory, etc.
