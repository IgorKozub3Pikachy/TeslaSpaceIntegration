# TeslaSpaceIntegration
 self.battery_level = battery_level
# Tesla Space Integration
# This script simulates communication between a Tesla vehicle and a space station

class TeslaVehicle:
    def __init__(self, model, battery_level):
        self.model = model
        self.battery_level = battery_level

    def charge(self, amount):
        self.battery_level = min(100, self.battery_level + amount)
        print(f"{self.model} charged to {self.battery_level}%")

    def send_data_to_space(self, data):
        print(f"Transmitting data from {self.model} to space station: {data}")
        return "Data received successfully"

class SpaceStation:
    def __init__(self, name):
        self.name = name

    def receive_data(self, data):
        print(f"{self.name} received data: {data}")
        return "Acknowledged"

# Example usage
tesla = TeslaVehicle("Model X", 75)
station = SpaceStation("ISS")

tesla.charge(20)
response = station.receive_data(tesla.send_data_to_space("Battery status: 95%"))
print(response)
