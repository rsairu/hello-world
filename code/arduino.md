see also store.arduino.cc/uno-r3

## Arduino Uno R3 board specs

|Field | Value
---|---
|Chip|ATmega328P
|Memory|32 KB (*Flash - program storage space*)<br/>2 KB (*SRAM - dynamic memory for global and local variables*)|1 KB (*EEPROM*)
|Interfaces| 12 C, SPI, UART
|Voltages|7-12V (*input*)<br/>5V USB (*operating*)
|Pinout|20 (*digital*), 6 (*PWM ~*)<br/>6 (*analog*)
|Dimensions|68.6 x 53.4 mm

## Electronics

[Resistor color code calculator](https://resistorcolorcodecalc.com/)

(Georg Simon) **Ohm's Law**: **Voltage** (_V_; volts) is equal to the product of the **Current** (_I_; amperes or 'amps') and the **Resistence** (_R_; *Ω* (Greek Omega char) ohms) of a circuit, or _V = I * R_


## Language (Sketch(?))

Statements end with `;` semicolon

void setup() {} // runs once when you press reset or power the board  
void loop() {} // runs over and over again forever  


pinMode(int pin, `INPUT` / `OUTPUT`)

analogWrite(int _pin_, long _value_) // sends a voltage between 0 and 2^10 (1024) (?)  
digitalWrite(int _pin_, `HIGH`/`LOW`) // sends a binary value of 1 or 0  
digitalRead(int _pin_)  

delay(int _milliseconds_)

Serial.begin(9600); // open a serial port  
Serial.print(string(?) _string_) // prints without returning carriage  
Serial.println(string _string_) // prints and goes to new line (returns carriage)

### Special names

`LED_BUILTIN` // the onboard LED (labeled _L_)  
`OUTPUT``INPUT` // used when setting `pinMode`  
`HIGH``LOW` // 1 or 0  
