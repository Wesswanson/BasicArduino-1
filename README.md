# BasicArduino
I'm going to learn how to use an Arduino, and make awesome things with it!


## TableofContents
* [HelloArduino](#HelloArduino)
* [FiniteLEDBlink](#FiniteLEDBlink)

## HelloArduino

### Description & Code
The goal of this project was to learn how to use an arduino editor to create basic patterns for an arduino uno to follow.
I learned to make an LED blink, and make the serial monitor display words at specific times.
This is my code with comments to explain what each part does:
```C++
// Wes Swanson
// Hello arduino
/* This makes an LED blink twice a second and prints the word blink twice a 
second. It writes "Hello" in the void setup before it starts.
*/
void setup() // This happens once, turns on the Arduino Uno before void loop starts.
{
 pinMode(13, OUTPUT); // This sets pin 13 to be an output
 Serial.begin(9600); // This turns on the serial moneter
 Serial.println("Hello"); // writes the word hello
}
void loop()
{
  digitalWrite(13, HIGH); // turns pin 13 on
  Serial.println("Blink"); // writes the word blink
  delay(250); // Delay 1/4 second
  digitalWrite(13, LOW); // turns pin 13 off
  delay(250); // Delay 1/4 second
} // End of loop, starts over again
```

### Evidence
[Here is my code on Arduino Create](https://create.arduino.cc/editor/wswanso44/c20ec904-8017-485b-bea4-df879d8c8323/preview)

### Image or Wiring
![Image of wiring](https://cdn.sparkfun.com/r/600-600/assets/learn_tutorials/3/1/0/Arduino_circuit_01_1.png)

[Link to image source](https://learn.sparkfun.com/tutorials/sik-experiment-guide-for-arduino---v32/experiment-1-blinking-an-led)

### Reflection
This project taught me a lot about circuits, LEDs, the Arduino Uno, and the code to control it all. Here are some important things I will need to know in the future:
When wiring the LED:
* Put LEDs the right direction (long side goes on the positive end).
* use a resistor for the LEDs.
* put the positive end into pin 13 if you are using this code, and put the negative end into ground.

When writing the code it is important to know these definitions:
* Pinmode() sets a pin to input or output.
* Serial.begin() turns on the serial monitor.
* Serial.println() prints a line of text on the serial monitor.
* pinmode() turns a pin's output either on or off depending if you write "high" or "low",
* delay() sets a delay time before the next action (this is needed to prevent it from crashing).

Also, you will need to know:
* Put a semicolen after each line of code.
* Put two slashes before a line of text or a slash and a star before and after multiple lines of code.
* Make sure there is a bracket before and after the code in the void setup and the void loop.

## FiniteLEDBlink

### Description & Code

```C++
Code Goes Here
```

### Evidence

### Image or Wiring

### Reflection
