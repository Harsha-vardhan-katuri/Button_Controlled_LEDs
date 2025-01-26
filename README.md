# Button-Controlled LED State Machine

This project demonstrates a button-controlled LED system implemented on an AVR microcontroller using direct port manipulation. The LEDs cycle through different states based on the button presses, with debouncing logic to ensure accurate input reading.

## Features

1. **LED Control:** Three LEDs connected to pins 13, 12, and 11 of the microcontroller.
2. **Button Input:** A button connected to pin 8 with an internal pull-up resistor.
3. **Debouncing Logic:** Ensures that button presses are accurately detected by filtering out noise.
4. **State Management:** LEDs cycle through the following states:
   - **State 0:** All LEDs off.
   - **State 1:** LED1 on (Pin 13).
   - **State 2:** LED2 on (Pin 12).
   - **State 3:** LED3 on (Pin 11).
   - **State 4:** All LEDs on.

## Hardware Requirements

- AVR Microcontroller (e.g., ATmega328P)
- Three LEDs
- One push-button
- Pull-up resistor (internal or external)
- Breadboard and connecting wires

## Software Requirements

- Arduino IDE (or equivalent AVR development environment)
- Wokwi Simulator (optional, for virtual simulation)

## Pin Configuration

| Component   | Pin  | Description                |
|-------------|------|----------------------------|
| LED1        | 13   | Connected to PB5           |
| LED2        | 12   | Connected to PB4           |
| LED3        | 11   | Connected to PB3           |
| Button      | 8    | Connected to PB0 with pull-up resistor |

## How It Works

1. **Button Press Detection:**
   - A button press (LOW state) triggers a change in the current LED state.
   - Debouncing is implemented to ensure stable input readings.

2. **LED State Management:**
   - The LEDs cycle through predefined states.
   - The `ledstate` variable tracks the current state.

3. **Output Control:**
   - Based on the current state, LEDs are turned on or off using direct port manipulation.

## Usage Instructions

1. Clone the repository or copy the code into your development environment.
2. Connect the hardware as per the pin configuration table.
3. Upload the code to the AVR microcontroller using the Arduino IDE.
4. Press the button to cycle through the LED states.

## Simulation on Wokwi

Run the project directly in the Wokwi simulator:
[![Run on Wokwi](https://wokwi.com/projects/419441645494336513)

## File Structure

- **`main.c`**: Contains the source code for the project.
- **`README.md`**: This documentation file.
- **`wokwi.json`**: Configuration file for the Wokwi simulator (if applicable).

## Future Enhancements

- Add support for more LEDs or states.
- Implement long-press detection for additional functionality.
- Integrate external interrupts for button handling.

## License

This project is licensed under the MIT License. You are free to use, modify, and distribute the code.

## Author

**Harsha Vardhan Katuri**  
katuriharshavardhan369@gmail.com

