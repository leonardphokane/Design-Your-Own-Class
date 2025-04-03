**Objective**: Create a custom class representing a real-life entity, initialize it with attributes, and add inheritance to explore OOP principles like polymorphism or encapsulation.

# Pseudocode
1. **Define a Class**
Define a class with a descriptive name (e.g., Smartphone, Book, Superhero).
1. Add Attributes
Inside the class, define attributes that represent characteristics of the object (e.g., model, color, battery_level for Smartphone).
Add Methods
Define methods to simulate actions or behaviors (e.g., make_call() for a Smartphone).
Create a Constructor
Define a constructor to initialize attributes with unique values when creating an object.
Define a Subclass (Inheritance Layer)
Create a subclass to inherit from the main class.
Add or override methods in the subclass to demonstrate polymorphism or encapsulation.
Initialize Objects
Instantiate objects of the class and subclass with unique values.

# Design-Your-Own-Class

# Assignment 1: Design Your Own Class (Smartphone Example)
class Smartphone:
    def __init__(self, brand, model, price):
        self.brand = brand  # Public attribute
        self.model = model  # Public attribute
        self.__price = price  # Private attribute (Encapsulation)

    def get_price(self):
        return self.__price  # Encapsulation: Providing controlled access

    def set_price(self, new_price):
        if new_price > 0:
            self.__price = new_price
        else:
            print("Price must be positive!")

    def display_info(self):
        print(f"Brand: {self.brand}, Model: {self.model}, Price: ${self.__price}")

# Inheritance: Extending Smartphone class
class GamingSmartphone(Smartphone):
    def __init__(self, brand, model, price, refresh_rate):
        super().__init__(brand, model, price)
        self.refresh_rate = refresh_rate
    
    def display_info(self):  # Overriding method
        print(f"Brand: {self.brand}, Model: {self.model}, Price: ${self.get_price()}, Refresh Rate: {self.refresh_rate}Hz")

# Creating objects
phone1 = Smartphone("Samsung", "Galaxy S23", 999)
gaming_phone = GamingSmartphone("Asus", "ROG Phone 6", 1200, 144)

phone1.display_info()
gaming_phone.display_info()
