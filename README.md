# smart-urban-parking-system
A conceptual computer engineering design for a sensor-driven, energy-efficient smart parking system.

## 1. Project Overview
The **Smart Urban Parking & Micro-Grid System (SUPM)** is a structural concept that reimagines standard parking garages. Instead of just being passive concrete storage spaces, this system turns a parking structure into an active node that tracks cars, manages energy efficiently, and dynamically distributes electrical power to Electric Vehicles (EVs).

## 2. Core Operational Goals
To make a parking garage smart, the engineering logic must solve three distinct problems:
* **Space Optimization:** The system must know exactly which parking spots are empty or occupied in real-time without human monitoring.
* **Energy Conservation:** The garage shouldn't waste electricity lighting up entire empty floors at night.
* **Grid Balancing:** When multiple EVs plug into chargers at the same time, the system must balance the power distribution so it doesn't overload the building's electrical circuit.

## 3. How the System Works (The Simple Logic)
Instead of using a complex network, this design uses one basic microcontroller (like an Arduino) connected to a single distance sensor and an LED light at each parking space. 

The software logic runs on a continuous loop using basic "If/Else" rules:

* **IF a car is parked:** The distance sensor measures that an object is very close (less than 50 cm away). The system automatically switches the overhead light to **Red** so other drivers know the spot is taken.
* **ELSE (The spot is empty):** The sensor measures a clear distance to the empty floor (more than 200 cm away). The system switches the overhead light to **Green**, signaling that the spot is available.

## 4. Next Steps for My Learning Tracker
I have already started practicing by writing a simple Python logic script for this project. My next step before starting university is to learn how to connect this code to real physical hardware. I want to learn how to wire an actual distance sensor to a microcontroller chip so that a real car can trigger the lights in person, moving my project from a software simulation to a physical device.

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
```

## 6. Python Logic Prototype
I have written a basic Python script to demonstrate how the "If/Else" distance parameters operate computationally:

```python
# --- Smart Urban Parking System: Core Logic Simulation ---
sensor_distance_cm = 45 

if sensor_distance_cm < 50:
    bay_status = "Occupied (1)"
    overhead_light = "RED"
    print("System Status: A vehicle has entered the parking space.")
else:
    bay_status = "Available (0)"
    overhead_light = "GREEN"
    print("System Status: The parking space is empty.")

print("--------------------------------------------------")
print(f"Sensor Reading: {sensor_distance_cm} cm")
print(f"Parking Spot Status: {bay_status}")
print(f"Overhead Indicator Light: {overhead_light}")
print("--------------------------------------------------")
```

### Interactive Version
You can run and test this code on my Kaggle Notebook here: **(https://www.kaggle.com/code/nouroth/smart-urban-parking-logic)**
