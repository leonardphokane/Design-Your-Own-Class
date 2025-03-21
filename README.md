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
