## Sample data for the department store
collection = [
    {"item_id": 1, "item_name": "Tshirt", "item_price": 500, "quantity": 200},
    {"item_id": 2, "item_name": "Jeans", "item_price": 800, "quantity": 500},
    {"item_id": 3, "item_name": "Jacket", "item_price": 650, "quantity": 100},
    {"item_id": 4, "item_name": "Sneakers", "item_price": 1000, "quantity": 50},
    {"item_id": 5, "item_name": "Handbag", "item_price": 200, "quantity": 60},
    {"item_id": 6, "item_name": "Watch", "item_price": 2000, "quantity": 20},
    {"item_id": 7, "item_name": "Shampoo", "item_price": 300, "quantity": 40},
    {"item_id": 8, "item_name": "Bedsheet Set", "item_price": 200, "quantity": 400},
    {"item_id": 9, "item_name": "Towel", "item_price": 400, "quantity": 100},
    {"item_id": 10, "item_name": "Microwave Oven", "item_price": 15000, "quantity": 100},
    {"item_id": 11, "item_name": "Blender", "item_price": 5000, "quantity": 320},
    {"item_id": 12, "item_name": "Coffee Maker", "item_price": 30000, "quantity": 45},
    {"item_id": 13, "item_name": "Television", "item_price": 60000, "quantity": 500},
    {"item_id": 14, "item_name": "Laptop", "item_price": 40000, "quantity": 70},
    {"item_id": 15, "item_name": "Play Station", "item_price": 100000, "quantity": 100},
    {"item_id": 16, "item_name": "Phone", "item_price": 20000, "quantity": 500},
    {"item_id": 17, "item_name": "Water Bottle", "item_price": 70, "quantity": 350},
    {"item_id": 18, "item_name": "Toy Car", "item_price": 700, "quantity": 100},
    {"item_id": 19, "item_name": "Doll", "item_price": 100, "quantity": 60},
    {"item_id": 20, "item_name": "Clock", "item_price": 500, "quantity": 100},
]

cart = []

def display_items():
    print("Available Items:")
    for item in collection:
        print(f"ID: {item['item_id']}, Name: {item['item_name']}, Price: {item['item_price']}, Quantity: {item['quantity']}")

def add_to_cart():
    while True:
        item_id = int(input("Enter the item ID to add to cart: "))
        quantity = int(input("Enter the quantity: "))
        
        for item in collection:
            if item["item_id"] == item_id:
                if item["quantity"] >= quantity:
                    cart_item = {
                        "item_id": item["item_id"],
                        "item_name": item["item_name"],
                        "quantity": quantity,
                        "item_price": item["item_price"],
                        "total_price": item["item_price"] * quantity,
                    }
                    cart.append(cart_item)
                    item["quantity"] -= quantity
                    print(f"Added {quantity} of {item['item_name']} to cart.")
                    print(f"Remaining quantity of {item['item_name']}: {item['quantity']}")
                    break
                else:
                    print(f"Not enough quantity for {item['item_name']}. Available: {item['quantity']}")
                    break
        else:
            print("Item not found.")
        
        another = input("Do you want to add another item? (yes/no): ").strip().lower()
        if another != 'yes':
            break

def delete_from_cart():
    if not cart:
        print("Your cart is empty. No items to delete.")
        return
    
    while True:
        item_id = int(input("Enter the item ID to delete from cart: "))
        for cart_item in cart:
            if cart_item["item_id"] == item_id:
                # Restore the quantity in the collection
                for item in collection:
                    if item['item_id'] == item_id:
                        item['quantity'] += cart_item['quantity']
                        break
                cart.remove(cart_item)  # Remove item from cart
                print(f"Deleted {cart_item['item_name']} from the cart.")
                return
        else:
            print("Item not found in the cart.")
        
        another = input("Do you want to delete another item? (yes/no): ").strip().lower()
        if another != 'yes':
            break

def view_cart():
    if not cart:
        print("Your cart is empty.")
        return
    print("Your Cart:")
    total_amount = 0
    for cart_item in cart:
        print(f"{cart_item['item_name']} - Quantity: {cart_item['quantity']}, Total Price: {cart_item['total_price']}")
        total_amount += cart_item['total_price']
    print(f"Total Amount: {total_amount}")

def checkout():
    if not cart:
        print("Your cart is empty. Cannot checkout.")
        return
    total_amount = sum(item['total_price'] for item in cart)
    print(f"Checkout successful. Total amount to pay: {total_amount}")
    cart.clear()  # Empty the cart after checkout

def main():
    while True:
        print("\n1. Display Items")
        print("2. Add to Cart")
        print("3. View Cart")
        print("4. Delete from Cart")
        print("5. Checkout")
        print("6. Exit")
        
        choice = input("Choose an option: ")
        
        if choice == '1':
            display_items()
        elif choice == '2':
            add_to_cart()
        elif choice == '3':
            view_cart()
        elif choice == '4':
            delete_from_cart()
        elif choice == '5':
            checkout()
        elif choice == '6':
            print("Thank you for shopping!")
            break
        else:
            print("Invalid option. Please try again.")

if __name__ == "__main__":
    main()
