see also store.arduino.cc/uno-r3

## Arduino Uno R3 board specs

|Field | Value
---|---
|Chip|ATmega328P
|Memory|32 KB (*Flash - program storage space*)<br/>2 KB (*SRAM - dynamic memory for global and local variables*)|1 KB (*EEPROM*)
|Interfaces| 12 C, SPI, UART
|Voltages|7-12V (*input*)<br/>5V USB (*operating*)
|Pinout|20 (*digital*)<br/>6 (*PWM*)<br/>6 (*analog*)
|Dimensions|68.6 x 53.4 mm

## Electronics

[Resistor color code calculator](https://resistorcolorcodecalc.com/)

(Georg Simon) **Ohm's Law**: **Voltage** (*V*; volts) is equal to the product of the **Current** (*I*; amperes or 'amps') and the **Resistence** (*R*; *Ω* (Greek Omega char) ohms) of a circuit, or V = I * R


## Language (Sketch(?))

Statements end with `;` semicolon

void setup() {} -  the setup function runs once when you press reset or power the board  
void loop() {} - runs over and over again forever  


pinMode(int pin, `INPUT` / `OUTPUT`)

analogWrite(int pin, long value) - sends a voltage between 0 and 2^10 (1024) (?)  
digitalWrite(int pin, `HIGH`/`LOW`) - sends a binary value of 1 or 0  
digitalRead(int pin)  

delay(int milliseconds)

Serial.begin(9600); // open a serial port  
Serial.print("string") // prints without returning carriage  
Serial.println("string") // prints and goes to new line (returns carriage)

### Special names

`LED_BUILTIN` - the LED on the board  
`OUTPUT` - `INPUT` - used when setting `pinMode`  
`HIGH` (1) - `LOW` (0)  
`INPUT` - `OUTPUT`  
