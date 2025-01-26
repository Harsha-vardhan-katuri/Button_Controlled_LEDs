unsigned long ledstate = 0;  // Current state of LEDs
byte buttonstate;
byte lastbuttonstate = HIGH;  // Start with HIGH due to pull-up resistor
unsigned long lastDebounceTime = 0;  // Timestamp of the last debounce
unsigned long debounceDelay = 50;  // Delay for debouncing (in milliseconds)

void setup() {
  // Set LED pins (Pin 13, 12, 11 as output)
  DDRB |= (1 << PB5);  // Set Pin 13 (PB5) as output
  DDRB |= (1 << PB4);  // Set Pin 12 (PB4) as output
  DDRB |= (1 << PB3);  // Set Pin 11 (PB3) as output

  // Set button pin (Pin 8 as input with pull-up resistor)
  DDRB &= ~(1 << PB0);  // Set Pin 8 (PB0) as input

  // Turn off LEDs initially
  PORTB &= ~(1 << PB5);  // Turn off LED1 (Pin 13)
  PORTB &= ~(1 << PB4);  // Turn off LED2 (Pin 12)
  PORTB &= ~(1 << PB3);  // Turn off LED3 (Pin 11)

  Serial.begin(9600);  // Start Serial communication for debugging
}

void loop() {
  int reading = PINB & (1 << PB0);  // Read Pin 8 (PB0)
 Serial.println(ledstate);
  // If the button state has changed
  if (reading != lastbuttonstate) {
    lastDebounceTime = millis();  // Reset debounce timer
  }

  // Only change the button state if the debounce time has passed
  if ((millis() - lastDebounceTime) > debounceDelay) {
    if (reading != buttonstate) {
      buttonstate = reading;
      
      // If the button is pressed (LOW due to pull-up resistor)
      if (buttonstate == LOW) {
        ledstate++;  // Cycle through LED states
        if (ledstate == 5) {
          ledstate = 0;  // Reset if we reach 5
        }
      }
    }
  }

  // LED control based on the current state
  if (ledstate == 1) {
    PORTB |= (1 << PB5);  // Turn on LED1 (Pin 13)
  } else {
    PORTB &= ~(1 << PB5);  // Turn off LED1 (Pin 13)
  }

  if (ledstate == 2) {
    PORTB |= (1 << PB4);  // Turn on LED2 (Pin 12)
  } else {
    PORTB &= ~(1 << PB4);  // Turn off LED2 (Pin 12)
  }

  if (ledstate == 3) {
    PORTB |= (1 << PB3);  // Turn on LED3 (Pin 11)
  } else {
    PORTB &= ~(1 << PB3);  // Turn off LED3 (Pin 11)
  }

  if (ledstate == 4) {
    PORTB |= (1 << PB5);  // Turn on LED1 (Pin 13)
    PORTB |= (1 << PB4);  // Turn on LED2 (Pin 12)
    PORTB |= (1 << PB3);  // Turn on LED3 (Pin 11)
  } else {
    PORTB &= ~(1 << PB5);  // Turn off LED1 (Pin 13)
    PORTB &= ~(1 << PB4);  // Turn off LED2 (Pin 12)
    PORTB &= ~(1 << PB3);  // Turn off LED3 (Pin 11)
  }

  lastbuttonstate = reading;  // Save the current button state
}
