# LED Control with Button Press

## Overview
This project demonstrates how to control multiple LEDs based on button presses, with debouncing to prevent unintended multiple button state changes. The project uses an AVR-based microcontroller (e.g., Arduino) and toggles the state of three LEDs (connected to Pins 13, 12, and 11) in a cycling manner with each button press. The state changes are controlled via the button press, and debouncing ensures that only one state change happens per press.

### **Note**: The project is implemented using **register-level programming**, and no inbuilt functions are used in the code.

## Components
- **Microcontroller (e.g., Arduino)**  
- **3 LEDs**  
- **1 Pushbutton**  
- **Resistors** (for LED and pushbutton connections)
  
## Working of the Project
1. **Button Press**  
   The pushbutton (connected to Pin 8) is used to control the state of the LEDs. Each time the button is pressed, the state of the LEDs cycles through the following states:
   - **State 1**: Only LED1 (Pin 13) is ON
   - **State 2**: Only LED2 (Pin 12) is ON
   - **State 3**: Only LED3 (Pin 11) is ON
   - **State 4**: All LEDs are ON
   - **State 0**: All LEDs are OFF

2. **Debouncing**  
   To avoid multiple button presses from being registered as one, the program implements a debounce mechanism using a delay of 50ms. This ensures that only one button press is counted even if the button contact is noisy or bounces.

3. **LED Control**  
   The LEDs are turned on or off based on the current state, and the state is toggled each time the button is pressed. When the button is pressed, the `ledstate` variable increments, and the LEDs are updated accordingly.

## Circuit Connections
For the hardware setup, follow the circuit diagram below. I have attached a JSON file for the connection diagram. 

1. **LEDs**
   - **LED1**: Pin 13
   - **LED2**: Pin 12
   - **LED3**: Pin 11

2. **Pushbutton**
   - One side of the pushbutton connects to **Pin 8** (configured as an input with a pull-up resistor), and the other side connects to **Ground**.

3. **Resistors**  
   Ensure each LED has a current-limiting resistor (e.g., 220Ω) to prevent excessive current flow. Similarly, use a pull-up resistor for the pushbutton.

## JSON Diagram for Circuit
For the connection setup, you can refer to the attached JSON diagram code.

### How to View the Diagram
1. Open the [Wokwi](https://wokwi.com) platform.
2. Create a new project or open an existing one.
3. Copy and paste the attached JSON code into the Wokwi editor to visualize the circuit and simulate the project.

### **Review the Project on Wokwi**
You can view and simulate this project directly on Wokwi using the following link:
[View on Wokwi](https://wokwi.com/projects/419441645494336513)

## 📝 Author  
**Harsha Vardhan Katuri**  

## 🔗 License  
This project is licensed under the **MIT License**.  



---
