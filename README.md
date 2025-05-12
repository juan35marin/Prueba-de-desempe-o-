# Prueba de desempeño
Below you will see the exercise resulting from the performance test and its respective Readme.md

### Prerequisites

Visual Studio Code is required, as is a GitHub account. If you don't have one, create one.

## Instructions to run the program


 * Install git if you don't have it on your device.
 * Open your terminal or command prompt.
 * Navigate to the Directory: Use the cd command to navigate to the directory where you want to download the repository.
 * Clone the Repository: Use the git clone command followed by the URL of the GitHub repository.
 * Excute the SQL project.

```
necesitas cliquear  en el costado derecho en el simbolo de Download raw file
```

## Another alternative

If you don't have Git installed, you can copy the code, paste it, and run it in Visual Studio.

```
necesitas cliquear  en el costado derecho en el simbolo de Copy raw file
```

## What each function does ?

 * def add_product(): This function is responsible for adding products, prices and quantities to the list.

    ```
    for i in range(5): # The for loop repeats the function or process the indicated number of times
        name: str = str(input(f"{i + 1} Enter the product name: "))  # Ask the user for the product name       
        if not name:  # If name is empty
            print("You must enter the product name.")  # Show error message
            return   # Exit the function
        try:
            price: float = float(input("Enter the product price: "))  # Ask for product price and convert to float
            quantity: int = int(input("Enter the product quantity: "))  # Ask for quantity and convert to integer
            if price < 0 or quantity < 0:  # Check for negative values
                print("Invalid value, prices or quantities cannot be negative.")  # Show error message
                return  # Exit the function
            product = {
                'name': name,  # Store product name
                'price': price,  # Store product price
                'quantity': quantity  # Store product quantity
            }
            inventory_list.append(product)  # Add product to the inventory list
            print(f"'{name}' has been added to the inventory list.")  # Confirm addition
        except ValueError:  # Handle case where input is not a number
            print("Invalid input, please enter numeric values.")  # Show error message
    ```
    * def consult_product(): It is responsible for going through the entire list in order to find the data desired by the user.
  
    ```
    def consult_product():
    name: str = str(input("Enter the name of the product you want to consult: "))  # Ask user for product name
    product = search(name)  # Search for the product in the inventory
    if product:  # If found
        print(f"Product: {product['name']}  Price: {product['price']}   Quantity: {product['quantity']}")  # Show details
    else:
        print("Product is not in the inventory list.")  # If not found, show message

    # Function to search for a product by name
    def search(name):
        for product in inventory_list:  # Loop through the inventory
            if product['name'].lower() == name.lower():  # Case-insensitive comparison
                return product  # Return the product if found
        return None  # Return None if not found
    
    ```
     * def update_price(): Allows you to change the value of the product price, generating a different price in the list.

      ```
      def update_price():
      name: str = str(input("Enter the name of the product you want to update the price for: "))  # Ask for product name
      product = search(name)  # Search for product
      if product:  # If found
        try:
            new_price = float(input("Enter the new price: "))  # Ask for new price
            if new_price < 0:  # Validate non-negative price
                print("Invalid option, prices cannot be negative.")  # Show error
                return
            product['price'] = new_price  # Update product price
            print(f"The new price is: {new_price:.2f} for '{name}'.")  # Confirm update
        except ValueError:  # Handle invalid number input
            print("Invalid option, price must be a number.")  # Show error message
      else:
        print("Product does not exist in the product list.")  # If not found

      ```
    *  def delete_product(): This is responsible for removing the product we do not want from the list, including its price and quantity.
      
       ```
        def delete_product():
        name: str = str(input("Enter the name of the product you want to delete: "))  # Ask for product name
        product = search(name)  # Search for product
        if product:  # If found
            print(f"{name} exist in the list")
            inventory_list.remove(product)  # Remove it from the list
            print(f"Product '{name}' has been removed from the inventory list.")  # Confirm deletion
        else:
            print("Product does not exist.")  # If not found
   
       ```
   * def calculate_total_value(): Se encarga de calcular el valor total de todos los productos.


        ```
          def calculate_total_value():
              # Use lambda to calculate price * quantity for each product
              total_value: float = sum(map(lambda p: p['price'] * p['quantity'], inventory_list))
              print(f"The total inventory value is: {total_value:.2f}")  # Print total value
        
        ```
    * Main() : Corresponds to the interactive menu with the user.
  
      
        ```
            def menu():
            print("--- Inventory Management ---")  # Menu title
            print("1. Add product")  # Option 1
            print("2. Consult product")  # Option 2
            print("3. Update price")  # Option 3
            print("4. Delete product")  # Option 4
            print("5. Calculate total inventory value")  # Option 5
            print("6. Exit")  # Option 6
      
       while True:  # Infinite loop until user exits
          try:
              option: int = int(input("Choose an option: "))  # Ask user for a menu option
          except ValueError:  # Handle non-integer input
              print("Invalid input. Please enter a number from 1 to 6.")  # Show error message
              continue  # Restart loop
        
        if option == 1:
            add_product()  # Call function to add product
        elif option == 2:
            consult_product()  # Call function to consult product
        elif option == 3:
            update_price()  # Call function to update price
        elif option == 4:
            delete_product()  # Call function to delete product
        elif option == 5:
            calculate_total_value()  # Call function to calculate total value
        elif option == 6:
            print("Program ended.")  # Exit message
            print("""TL realmente tuve varios percanses en la construccion de las funciones y en como llarmar los diccionarios
            por medio del nombre y no la posicion, espero que no se note tanto la influencias de ayudas de la red """)
            break  # Exit loop
        else:
            print("Invalid option. Please try again.")  # Handle unexpected input
      
      # Call the menu to start the program
      menu()

        
        ```


### Installing git in linux

  *  Install git if you don't have it on your device.
  *  Open your terminal or command prompt.
  *  Navigate to the Directory: Use the cd command to navigate to the directory where you want to download the repository.
  *  Clone the Repository: Use the git clone command followed by the URL of the GitHub repository.
  *  Excute the SQL project.






