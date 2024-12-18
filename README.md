# Challenge-2
# printing the menu for the customer

# This is the menu the customer will be selecting from.
[
  {
    "Item name": "string",
    "Price": float,
    "Quantity": int
  },
  {
    "Item name": "string",
    "Price": float,
    "Quantity": int
  },
]
# Menu dictionary
menu = {
    "Snacks": {
        "Cookie": .99,
        "Banana": .69,
        "Apple": .49,
        "Granola bar": 1.99
    },
    "Meals": {
        "Burrito": 4.49,
        "Teriyaki Chicken": 9.99,
        "Sushi": 7.49,
        "Pad Thai": 6.99,
        "Pizza": {
            "Cheese": 8.99,
            "Pepperoni": 10.99,
            "Vegetarian": 9.99
        },
        "Burger": {
            "Chicken": 7.49,
            "Beef": 8.49
        }
    },
    "Drinks": {
        "Soda": {
            "Small": 1.99,
            "Medium": 2.49,
            "Large": 2.99
        },
        "Tea": {
            "Green": 2.49,
            "Thai iced": 3.99,
            "Irish breakfast": 2.49
        },
        "Coffee": {
            "Espresso": 2.99,
            "Flat white": 2.99,
            "Iced": 3.49
        }
    },
    "Dessert": {
        "Chocolate lava cake": 10.99,
        "Cheesecake": {
            "New York": 4.99,
            "Strawberry": 6.49
        },
        "Australian Pavlova": 9.99,
        "Rice pudding": 4.99,
        "Fried banana": 4.49
    }
}

# 1. Set up order list. Order list will store a list of dictionaries for
# menu item name, item price, and quantity ordered

order = []  # Initialize an empty list

# 2. Create a function to print the menu for the customer
item_order = {
    "Item name": "Apple",
    "Price": 0.49,
    "Quantity": 2
}
# Step 3: Append the dictionary to the order list
order.append(item_order)

# You can add more items similarly
item_order2 = {
    "Item name": "Banana",
    "Price": 0.69,
    "Quantity": 3
}
order.append(item_order2)

# Print the order list to see the result
print(order)
# Launch the store and present a greeting to the customer
print("Welcome to the variety food truck.")

# Customers may want to order multiple items, so let's create a continuous
# loop to allow the customer to order as many items as they want.

# Menu dictionary
menu = {
    "Snacks": {
        "Cookie": .99,
        "Banana": .69,
        "Apple": .49,
        "Granola bar": 1.99
    },
    "Meals": {
        "Burrito": 4.49,
        "Teriyaki Chicken": 9.99,
        "Sushi": 7.49,
        "Pad Thai": 6.99,
        "Pizza": {
            "Cheese": 8.99,
            "Pepperoni": 10.99,
            "Vegetarian": 9.99
        },
        "Burger": {
            "Chicken": 7.49,
            "Beef": 8.49
        }
    },
    "Drinks": {
        "Soda": {
            "Small": 1.99,
            "Medium": 2.49,
            "Large": 2.99
        },
        "Tea": {
            "Green": 2.49,
            "Thai iced": 3.99,
            "Irish breakfast": 2.49
        },
        "Coffee": {
            "Espresso": 2.99,
            "Flat white": 2.99,
            "Iced": 3.49
        }
    },
    "Dessert": {
        "Chocolate lava cake": 10.99,
        "Cheesecake": {
            "New York": 4.99,
            "Strawberry": 6.49
        },
        "Australian Pavlova": 9.99,
        "Rice pudding": 4.99,
        "Fried banana": 4.49
    }
}
menu_items = {}
i = 1   
for key in menu.keys():
        print(f"{i}: {key}")
        
        # Store the menu category associated with its menu item number
        menu_items[i] = key
       
        # Add 1 to the menu item number
        i += 1

# Print the options to choose from menu headings (all the first level
# dictionary items in menu).

i = 1

# Print the options to choose from menu headings

print("Please choose a menu category:")
for key in menu.keys():
        print(f"{i}: {key}")
        i += 1

# Create a dictionary to store the menu for later retrieval 

for key in menu.keys():
    print(f"{i}: {key}")
    # Store the menu category associated with its menu item number
    menu_items[i] = key
    # Add 1 to the menu item number
    i += 1

# Print the options to choose from menu headings (all the first level
# dictionary items in menu).

menu_items = {}
i = 1
print("Please choose a menu category:")

for key in menu.keys():
        print(f"{i}: {key}")
        menu_items[i] = key # Store the menu category associated with its menu item number
menu_category = input("Please enter the menu category number: ")
if menu_category.isdigit() and int(menu_category) in menu_items.keys():
    menu_category_name = menu_items[int(menu_category)] # Add 1 to the menu item number

    # Print out the menu category name they selected
    
    print(f"You selected {menu_category_name}")
    
    # Print out the menu options from the menu_category_name
    
    print(f"What {menu_category_name} item would you like to order?")
    i = 1
    print("Item # | Item name                | Price")
    print("-------|--------------------------|-------")

    menu_items = {}
    for key, value in menu[menu_category_name].items():
                    num_item_spaces = 24 - len(key)
                    item_spaces = " " * num_item_spaces
                    print(f"{i}      | {key}{item_spaces} | ${value}")
                    menu_items[i] = {
                        "Item name": key,
                        "Price": value
                    }
                    i += 1
    
    # Save the menu category name to a variable
    
    menu_category_name = menu_items[int(menu_category)]
    
    # Print out the menu category name they selected
    
    print(f"You seleted {menu_category_name}")

    # Print out the menu options from the menu_category_name
    
    print(f"What {menu_category_name} item would you like to order?")
    i = 1
    menu_items = {}
    print("Item # | Item name                | Price")
    print("-------|--------------------------|-------")
    
    for key, value in menu[menu_category_name].items():
                
                # Check if the menu item is a dictionary to handle differently
                if type(value) is dict:
                    for key2, value2 in value.items():
                        num_item_spaces = 24 - len(key + key2) - 3
                        item_spaces = " " * num_item_spaces
                        print(f"{i}      | {key} - {key2}{item_spaces} | ${value2}")
                        menu_items[i] = {
                            "Item name": key + " - " + key2,
                            "Price": value2
                        }
                        i += 1
                else:
                    num_item_spaces = 24 - len(key)
                    item_spaces = " " * num_item_spaces
                    print(f"{i}      | {key}{item_spaces} | ${value}")
                    menu_items[i] = {
                        "Item name": key,
                        "Price": value
                    }
                    i += 1
            # 2. Ask customer to input menu item number
    menu_selection = input("Type menu number: ")

# Assuming menu_items is a dictionary containing the menu items and their corresponding numbers
    menu_selection = input("Type menu number: ")

            # 3. Check if the customer typed a number
    
    if menu_selection.isdigit():
                menu_selection = int(menu_selection)     
            
            # The isdigit() method checks if the input is a number.
            # If it is not an integer, we convert it to an integer and 
            # check if it exists in the menu_items dictionary. 
                
            # Convert the input to an integer
                
                menu_selection = int(menu_selection)
                            
            # 4. Check if the menu selection is in the menu items
                
                if menu_selection in menu_items.keys():
  
 # Proceed with the order process
                    item_name = menu_items[menu_selection]["Item name"]
                    print(f"You selected {item_name}.")
                else:
                
                # Tell the customer that their input isn't valid
                    print("Sorry, that number isn't an option.")
                
                # Store the item name as a variable
                    item_name = input("Enter the name of the item you want to purchase: ")                    

                    # Assuming you have the item name stored in a variable called item_name
                    # Ask the customer for the quantity of the menu item                  
    
    quantity = input(f"What quantity of {item_name} would you like? (This will default to 1 if not entered) ")

                    # Check if the quantity is a number
    
    if not quantity.isdigit():
                    # Check if the quantity is a number, default to 1 if not
        
        quantity = 1    # Default to 1 if the input is not a valid number
    else:
        quantity = int(quantity)  # Convert the input to an integer

                    # Add the item name, price, and quantity to the order list

# Initialize the order list
    
    order_list = []

# Assume you have the following variables after getting user input
    
    item_name = "Example Item"  # Replace with the actual item name
    item_price = 5.99           # Replace with the actual item price
    quantity = 2                # Replace with the actual quantity

# Create a dictionary for the order item
    
    order_list = {
    "Item name": item_name,
    "Price": item_price,
    "Quantity": quantity
}
# Append the order item to the order list
    
    order_list.append(item_name, item_price, quantity)  

# Now, order_list contains the item details
    
    print(order_list)

# Check if the menu selection is in the menu items
    
    if menu_selection in menu_items.keys():
        
        # Proceed with the order process
        
        item_name = menu_items[menu_selection]["Item name"]
        print(f"You selected {item_name}.")
    
    else:

        # Tell the customer that their input isn't valid
        
        print("Sorry, that number isn't an option.")

        # Tell the customer they didn't select a menu option
    
    print(f"{menu_category} was not a menu option.")

# Tell the customer they didn't select a number
   
print("You didn't select a number.")
                   
# Proceed with the order process

item_name = menu_items[menu_selection]["Item name"]
print(f"You selected {item_name}.")


# In this code:

# If the customer inputs 'y', the order process continues.
# If they input 'n', the order process stops, and a thank you message is displayed.
# If the input is anything else, the customer is prompted to try again.

while True:
       
       # Ask the customer if they would like to order anything else
        
        keep_ordering = input("Would you like to keep ordering? (Y)es or (N)o ")

        # 5. Check the customer's input
        
        match keep_ordering.lower():
            case "y":
                # Keep ordering
                place_order = True
                break  # Exit the keep ordering question loop
            case "n":
                # Exit the keep ordering question loop

                # Complete the order
                
                place_order = False
                print("Thank you for your order.")
                break  # Exit the keep ordering question loop
            case _:
                
                # Tell the customer to try again
                
                print("I didn't understand your response. Please try again.")
                
                # Since the customer decided to stop ordering, thank them for their order.
                
                print("Thank you for your order.")
                break    # Exit the keep ordering question loop
                
                # Tell the customer to try again
                
                print("I didn't understand your response. Please try again.")


# Print out the customer's order

print("This is what we are preparing for you.\n")
order = []
for item in order_list:
    order +print(f"{item['Item name']} | ${item['Price']} | {item['Quantity']}")
print("\n".join(order))

print(order_list)
      
print("Item name                 | Price  | Quantity")
print("--------------------------|--------|----------")

# 6. Loop through the items in the customer's order
# Assuming 'order' is your list of dictionaries

for i in range(len(order)):
    # Store the dictionary items as variables
    item_name = order[i]["Item name"]
    price = order[i]["Price"]
    quantity = order[i]["Quantity"]

    # You can now use these variables to print or process the order items
    
    print(f"Item: {item_name}, Price: ${price}, Quantity: {quantity}")

# Alternatively, you can loop through the list directly without using the index:

for item in order:
    item_name = item["Item name"]
    price = item["Price"]
    quantity = item["Quantity"]
    print(f"Item: {item_name}, Price: ${price}, Quantity: {quantity}")

# Both methods will allow you to access and work with each item in the customer's order.

# 7. Store the dictionary items as variables
# Example dictionary representing an order item

order_item = {
    "Item name": "Apple",
    "Price": 0.50,
    "Quantity": 3
}

# Storing the dictionary items as variables

item_name = order_item["Item name"]
price = order_item["Price"]
quantity = order_item["Quantity"]

# Now you can use these variables
print(f"Item: {item_name}, Price: ${price}, Quantity: {quantity}")

# If you are looping through a list of such dictionaries (like in a customer's order), you would do it like this:

# Assuming 'order' is a list of dictionaries

for item in menu:
    item_name = item["Item name"]
    price = item["Price"]
    quantity = item["Quantity"]
    
    # Now you can use these variables
    print(f"Item: {item_name}, Price: ${price}, Quantity: {quantity}")

# This way, you can easily access and manipulate the values stored in the dictionary.


    # 8. Calculate the number of spaces for formatted printing
    # Example data

items = [
    {"Item name": "Apple", "Price": 0.50, "Quantity": 3},
    {"Item name": "Banana", "Price": 0.30, "Quantity": 5},
    {"Item name": "Cherry", "Price": 0.20, "Quantity": 10}
]

# Print header

print(f"{'Item name':<10} {'Price':<10} {'Quantity':<10}")

# Print each item in the order

for item in items:
    item_name = item["Item name"]
    price = item["Price"]
    quantity = item["Quantity"]
    
    # Print each item with formatted spaces
    
    print(f"{item_name:<10} {price:<10} {quantity:<10}")


# In this example:
# The < operator in the f-string specifies right alignment.
# The number after < (e.g., <10) indicates the width of the field. This means that each 
# item will take up at least 10 characters of space in the output.

# You can adjust the width to fit your needs. 
# If you want to right-align or center the text, you can use > or ^ respectively:
# This way, you can control the spacing and alignment of your printed output effectively. 

    # 9. Create space strings
def new_func(item_name, quantity, price): # Centered

    # 10. Print the item name, price, and quantity

    print(f"{item_name:>10} {price:>10} {quantity:>10}")  # Right-aligned
    print(f"{item_name:^10} {price:^10} {quantity:^10}")


# 11. Calculate the cost of the order using list comprehension
# Multiply the price by quantity for each item in the order list, then sum()
# and print the prices.

order = [
    {"Item name": "Apple", "Price": 0.49, "Quantity": 2},
    {"Item name": "Tea - Thai iced", "Price": 3.99, "Quantity": 1},
    {"Item name": "Fried banana", "Price": 4.49, "Quantity": 3}
]
# You can calculate the total price using list comprehension as follows:

total_price = sum([item["Price"] * item["Quantity"] for item in order])
print(f"Total price: ${total_price:.2f}")
