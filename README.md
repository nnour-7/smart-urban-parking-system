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
Because I do not know any programming languages yet, my goal as I start my studies is to learn basic **C++ or Python** so I can translate this simple physical logic into actual lines of code. I want to learn how to wire a real physical sensor to a microcontroller and write the basic script that triggers the lights automatically.

## 5. System Logic Workflow
This diagram shows how data flows when a car interacts with the sensor:

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
