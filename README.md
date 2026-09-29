# smart-urban-parking-system
A conceptual computer engineering design for a sensor-driven, energy-efficient smart parking system.

## 1. Project Overview
The **Smart Urban Parking (SUP)** is a structural concept that switches up standard parking garages. Instead of just being concrete storage spaces, this system turns a parking structure into an active node that tracks cars and manages lighting energy efficiently

## 2. Core Operational Goals
To make a parking garage smart, the engineering logic must solve these three problems:
* **Space Optimization:** The system must know exactly which parking spots are empty or occupied in real-time without human monitoring.
* **Energy Conservation:** The garage shouldn't waste electricity lighting up entire empty floors at night.
  
## 3. How the System Works
Instead of using a complex network, this design uses one basic microcontroller (like an Arduino) connected to a single distance sensor and an LED light at each parking space. 

The software logic runs on a continuous loop using basic "If/Else" rules:

* **IF a car is parked:** The distance sensor measures that an object is very close (less than 50 cm away). The system switches the overhead light to **Red** and sets the nearby structural lighting to **Full Brightness** for safety.
* **ELSE (The spot is empty):** The sensor measures a clear distance to the empty floor (more than 200 cm away). The system switches the overhead light to **Green** and **dims the structural lights to 20%** to conserve energy.

## 4. Next Steps for My Learning Tracker
I have already started practicing by writing a simple Python logic script for this project. My next step before starting university is to learn how to connect this code to real physical hardware. I want to learn how to wire an actual distance sensor to a microcontroller chip so that a real car can trigger the lights physically, moving my project from a software simulation to a physical device.

## 5. System Logic Workflow
This diagram shows how data flows when a car interacts with the sensor:

```text
[ Car Enters Parking Space ]
            │
            ▼
[ Distance Sensor Measures < 50cm ]
            │
            ▼
[ Microcontroller Runs "IF" Rule ]
            │
            ▼
[ Overhead Light Switches to RED ]
            │
            ▼
[ Structural Lights Go to 100% ]
```
## 6. Python Logic Prototype
I have written a simple Python script to demonstrate how the "If/Else" distance parameters operate computationally:

```python
# Smart Urban Parking System

# 1. Determine parking spot availability
user_entry = input("Is the parking spot occupied? Yes/No:").lower()

if user_entry == "yes":
    sensor_distance_cm < 50

else:
    sensor_distance_cm = 210

# 2. Run the decision-making logic using an If/Else statement
if sensor_distance_cm < 50:
    # This block runs ONLY if a car is close to the sensor
    bay_status = "Occupied (1)"
    overhead_light = "RED"
    structural_light_power = "100% (Full Brightness for Safety)"
    print("System Status: A vehicle has entered the parking space.")

else:
    # This block runs if the sensor measures a clear path to the floor
    bay_status = "Available (0)"
    overhead_light = "GREEN"
    structural_light_power = "20% (Dimmed to Conserve Energy)"
    print("System Status: The parking space is empty.")

# 3. Output the final physical results of the system
print("--------------------------------------------------")
print(f"Sensor Reading: {sensor_distance_cm} cm")
print(f"Parking Spot Status: {bay_status}")
print(f"Overhead Indicator Light: {overhead_light}")
print(f"Structural Lighting Level: {structural_light_power}")
print("--------------------------------------------------")
```

### Interactive Version
You can run and test this code on my Kaggle Notebook here: **(https://www.kaggle.com/code/nouroth/smart-urban-parking-logic)**
