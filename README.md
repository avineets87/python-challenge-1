# python-challenge-1

## Order System

1.  Create an empty list. This list will later store a customer's order in dictionary format, as follows:
    
    ```python
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
    
    ```
    
2.  After the sub-menu is printed, prompt the customer to enter their selection from the menu, saving it as a variable `menu_selection`.
    
3.  Use input validation to check if the customer input `menu_selection` is a number. If it isn't, print an error message. If it is a number, convert the input to an integer and use it to check if it is in the keys of `menu_items`.
    
4.  If the user input is not in the `menu_items` keys, print an error. Otherwise, perform the following actions:
    
    -   Get the item name from the `menu_items` dictionary and store it as a variable.
        
    -   Ask the customer for the quantity of the menu item, using the item name variable in the question, and let them know that the quantity will default to `1` if their input is invalid. Save their answer as a variable called `quantity`.
        
    -   Check that the customer input is a number. If it isn't, set the `quantity` to the value `1`. If it is a number, convert the variable to an integer.
        
    -   Append the customer's order to the order list in dictionary format with the following keys: `"Item name"`, `"Price"`, and `"Quantity`. You will need this information to print the receipt at the end of the order. The price should be found in the `menu_items` dictionary.
        
5.  Inside the continuous `while` loop that prompts the customer if they would like to keep ordering, write a `match:case` statement that checks for `y` or `n` (upper or lowercase), and includes a default option if neither letter is entered by the customer. The following actions should be performed for each case:
    
    -   `y`: Set the `place_order` variable to `True` and break from the continuous while loop.
        
    -   `n`: Set the `place_order` variable to `False`, print "Thank you for your order", and break from the continuous while loop.
        
    -   Default: Tell the customer to try again because they didn't type a valid input.
        

## Order Receipt

6.  Create a `for` loop to loop through the order list.
    
7.  Inside the loop, save the value of each key as their own variable: `item_name`, `price`, and `quantity`.
    
8.  Calculate the number of empty spaces that should be added to the display so that the receipt uses the following format:
    
    ```text
    Item name                 | Price  | Quantity
    --------------------------|--------|----------
    Apple                     | $0.49  | 1
    Tea - Thai iced           | $3.99  | 2
    Fried banana              | $4.49  | 3
    
    ```
    
9.  Create the space strings as their own variables using string multiplication.
    
10.  Print the line for the receipt using the format in Step 8.
    
11.  Upon exiting the `for` loop, use list comprehension and `sum()` to calculate the total price of the order and display it to the customer. Make sure you multiply the price by the quantity in your list comprehension.

## Solution Logs

```text
(dev) (base) avineetsharma@Avineets-MacBook-Air python-challenge-1 % python menu.py
Welcome to the variety food truck.
From which menu would you like to order? 
1: Snacks
2: Meals
3: Drinks
4: Dessert
Type menu number: 1
You selected Snacks
What Snacks item would you like to order?
Item # | Item name                | Price
-------|--------------------------|-------
1      | Cookie                   | $0.99
2      | Banana                   | $0.69
3      | Apple                    | $0.49
4      | Granola bar              | $1.99
Type/Enter your selection from the menu: 2

Enter the quantity of 'Banana' you would like to order. 
 (If your input is invalid then we will default to '1') :3

Would you like to keep ordering? (Y)es or (N)o :y
From which menu would you like to order? 
1: Snacks
2: Meals
3: Drinks
4: Dessert
Type menu number: 3
You selected Drinks
What Drinks item would you like to order?
Item # | Item name                | Price
-------|--------------------------|-------
1      | Soda - Small             | $1.99
2      | Soda - Medium            | $2.49
3      | Soda - Large             | $2.99
4      | Tea - Green              | $2.49
5      | Tea - Thai iced          | $3.99
6      | Tea - Irish breakfast    | $2.49
7      | Coffee - Espresso        | $2.99
8      | Coffee - Flat white      | $2.99
9      | Coffee - Iced            | $3.49
Type/Enter your selection from the menu: 7

Enter the quantity of 'Coffee - Espresso' you would like to order. 
 (If your input is invalid then we will default to '1') :7

Would you like to keep ordering? (Y)es or (N)o :y
From which menu would you like to order? 
1: Snacks
2: Meals
3: Drinks
4: Dessert
Type menu number: 4
You selected Dessert
What Dessert item would you like to order?
Item # | Item name                | Price
-------|--------------------------|-------
1      | Chocolate lava cake      | $10.99
2      | Cheesecake - New York    | $4.99
3      | Cheesecake - Strawberry  | $6.49
4      | Australian Pavlova       | $9.99
5      | Rice pudding             | $4.99
6      | Fried banana             | $4.49
Type/Enter your selection from the menu: 6

Enter the quantity of 'Fried banana' you would like to order. 
 (If your input is invalid then we will default to '1') :8

Would you like to keep ordering? (Y)es or (N)o :n
Thank you for your order
This is what we are preparing for you.

Item name                 | Price  | Quantity
--------------------------|--------|----------
Banana                    | $0.69  | 3
Coffee - Espresso         | $2.99  | 7
Fried banana              | $4.49  | 8

|-------------------------------|
|Total cost of the order: $58.92|
|-------------------------------|
```