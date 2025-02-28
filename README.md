# Ass-1
class Order:
    # Order class represents a customer's order
    def __init__(self, order_id, recipient_name, delivery_address, order_date, total_amount):
        self.__order_id = order_id  # Unique order ID
        self.__recipient_name = recipient_name  # Name of recipient
        self.__delivery_address = delivery_address  # Delivery address
        self.__order_date = order_date  # Date of the order
        self.__total_amount = total_amount  # Total cost of the order
    
    # Getter methods to access private attributes
    def get_order_id(self):
        return self.__order_id
    
    def get_recipient_name(self):
        return self.__recipient_name
    
    def get_delivery_address(self):
        return self.__delivery_address
    
    def get_order_date(self):
        return self.__order_date
    
    def get_total_amount(self):
        return self.__total_amount
    
    # Setter methods to modify private attributes
    def set_recipient_name(self, name):
        self.__recipient_name = name
    
    def set_delivery_address(self, address):
        self.__delivery_address = address
    
    def set_total_amount(self, amount):
        self.__total_amount = amount
    
    # Function to create a new order
    def create_order(self):
        return f"Order {self.__order_id} has been created successfully."
    
    # Function to cancel an order
    def cancel_order(self):
        return f"Order {self.__order_id} has been canceled."


class DeliveryNote:
    # DeliveryNote class represents a note generated for an order
    def __init__(self, note_id, order_id, delivery_date, package_weight):
        self.__note_id = note_id  # Unique note ID
        self.__order_id = order_id  # Associated order ID
        self.__delivery_date = delivery_date  # Date of delivery
        self.__package_weight = package_weight  # Weight of the package
    
    # Getter methods
    def get_note_id(self):
        return self.__note_id
    
    def get_order_id(self):
        return self.__order_id
    
    def get_delivery_date(self):
        return self.__delivery_date
    
    def get_package_weight(self):
        return self.__package_weight
    
    # Setter methods
    def set_delivery_date(self, date):
        self.__delivery_date = date
    
    def set_package_weight(self, weight):
        self.__package_weight = weight
    
    # Function to generate a delivery note
    def generate_note(self):
        return f"Delivery note {self.__note_id} for Order {self.__order_id} has been generated."


class Customer:
    # Customer class represents a person who places an order
    def __init__(self, customer_id, name, email, contact):
        self.__customer_id = customer_id  # Unique customer ID
        self.__name = name  # Customer name
        self.__email = email  # Customer email
        self.__contact = contact  # Customer contact number
    
    # Getter methods
    def get_customer_id(self):
        return self.__customer_id
    
    def get_name(self):
        return self.__name
    
    def get_email(self):
        return self.__email
    
    def get_contact(self):
        return self.__contact
    
    # Setter methods
    def set_name(self, name):
        self.__name = name
    
    def set_email(self, email):
        self.__email = email
    
    def set_contact(self, contact):
        self.__contact = contact
    
    # Function to track an order
    def track_order(self):
        return f"Tracking order for {self.__name}."


class Admin:
    # Admin class represents a system administrator who manages orders
    def __init__(self, admin_id, name, role):
        self.__admin_id = admin_id  # Unique admin ID
        self.__name = name  # Admin name
        self.__role = role  # Admin role (e.g., manager)
    
    # Getter methods
    def get_admin_id(self):
        return self.__admin_id
    
    def get_name(self):
        return self.__name
    
    def get_role(self):
        return self.__role
    
    # Setter methods
    def set_name(self, name):
        self.__name = name
    
    def set_role(self, role):
        self.__role = role
    
    # Function to update the order status
    def update_order_status(self):
        return f"Order status has been updated by {self.__name}."

# Create objects based on the provided information
customer = Customer(101, "Sarah Johnson", "sarah.johnson@example.com", "+971-50-1234567")
order = Order("DEL123456789", customer.get_name(), "45 Knowledge Avenue, Dubai, UAE", "January 25, 2025", 283.50)
delivery_note = DeliveryNote("DN-2025-001", order.get_order_id(), "January 25, 2025", "7 kg")

# Display the delivery note information
print("Delivery Note")
print("-----------------------------")
print(f"Name: {customer.get_name()}")
print(f"Contact: {customer.get_email()}")
print(f"Delivery Address: {order.get_delivery_address()}")
print("\nDelivery Information:")
print(f"Order Number: {order.get_order_id()}")
print(f"Reference Number: {delivery_note.get_note_id()}")
print(f"Delivery Date: {delivery_note.get_delivery_date()}")
print(f"Delivery Method: Courier")
print(f"Package Dimensions: N/A")
print(f"Total Weight: {delivery_note.get_package_weight()}")
print("\nSummary of Items Delivered:")
print("---------------------------------")
print("Wireless Keyboard - 1 unit - 100 AED")
print("Wireless Mouse & Pad Set - 1 unit - 75 AED")
print("Laptop Cooling Pad - 1 unit - 120 AED")
print("Camera Lock - 3 units - 45 AED")
print("\nSubtotal: AED 270.00")
print("Taxes and Fees: AED 13.50")
print("Total Charges: AED 283.50")
