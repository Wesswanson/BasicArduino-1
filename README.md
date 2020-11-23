# BasicArduino
I'm going to learn how to use an Arduino, and make awesome things with it!


## TableofContents
* [HelloArduino](#HelloArduino)
* [FiniteLEDBlink](#FiniteLEDBlink)
* [VariableLEDBlink](#VariableLEDBlink)

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

This assignment was to make an LED blink five times and than stop. I used the code from the assignment above and added more code to make three LEDs blink five times each and then stop. Here is my code with descriptions for what it does:
```C++
// Wes Swanson
// 11/18/20
// finite LED blink
/* This makes three LEDs blink in turn for 1/4 second with 1/4 second between each blink. Each time
  an LED turns on, the serial monitor will display the pin that is blinking (13, 12, or 11) and the
  work "Blink". It will also count up from 0 the number of times that LED has blinked. after blinking
  5 times each, the loop will stop.
*/
int led = 13;
int W = 0; 
/* These functions creates variables that are always an integer (that is why int is written
  before the variable). The number sets that variable to an initial value before they possibly change
  later in the code.
*/
void setup()
{
  pinMode(led, OUTPUT); // This sets pin led to be an output pin.
  pinMode((led - 1), OUTPUT); // This sets pin led-1 to be an output pin.
  // Because led is set to pin 13, led-1 is pin 12.
  pinMode((led - 2), OUTPUT); // This sets pin led-2 to be an output pin.
  // Because led is set to pin 13, led-2 is pin 11.
  Serial.begin(9600); // This turns on the serial moneter.
  Serial.println("Hello"); // This writes the word hello.
}
void loop()
{
  if (W < 5) { // This line says that everything below happens only if W is less than five.
    digitalWrite(led, HIGH);
    Serial.print(led); // writes the value of led at that time (it could be 13, 12, or 11).
    Serial.print(" Blink \t"); // writes the word blink and creates a space (like the tab key)
    Serial.println(W); // writes the value of W at that time (it could be 0 through 4)
    delay(250);
    digitalWrite(led, LOW);
    delay(250); //
    led = led - 1; // sets the value of the variable led one lower.
    if (led == 10) {
      /* this is a conditional statement. == means that the computer should check to see
        if led is equal to ten. If it is, the code below will happen, if not, it will jump to the end of
        the loop and start over again.*/
      led = 13; // this sets led back to 13 again.
      W = W + 1;
      /* this makes the value of W (the variable that counts the number of times each led
        has blinked) go up 1. This is part of the conditional statement so it happens every three
        times this loop is run. */
    }
  }
} // End of loop, starts over again
```
### Evidence

Here is a [link](https://create.arduino.cc/editor/wswanso44/c20ec904-8017-485b-bea4-df879d8c8323/preview) to my code on Arduino Create.

### Image or Wiring

This is a wiring diagram I made on tinkercad.com:

![image](https://github.com/Wesswanson/BasicArduino-1/blob/main/Screenshot%202020-11-18%20at%203.50.12%20PM.png?raw=true)

### Reflection

This assignment taught me about variables and "if" statements, and I used those as well as my knowledge from the previous assignment to create a very cool project. It is very important to define your variables correctly and use capitalization correctly when using variables. It is also important to use "If" statements correctly. Remember:
* Start with the word if, then a space.
* in parentheses, write the statement such as (x>4).
* If you want the computer to find out whether something is equal to something, rather than making it equal, use double equal signs, like if (y == 1).
* After the parentheses, write what should happen if your if statement is true inside brackets like this: {digitalWrite (9, HIGH)}

As I learn to edit this code, it's getting more fun because I can do so many more things. I'm excited to learn more about this topic.

## VariableLEDBlink

### Description & Code
```C++
/* Wes Swanson
  11/20/20
  Variable LED Blinker
  This code makes three LEDs in pins 13, 12, and 11. Each one blinks for 2 seconds with 2 seconds in between before the delay time is lowered to
  1.8 seconds and then 1.6 seconds and so on. When it reaches zero delay time it will jump back up to 2 seconds of delay time. The serial
  monitor will display the LED that is blinking as well as the current delay time when each LED turns on.
*/
int LED = 13; //This variable is the LED that is on. It starts at 13 but will also be 12 and 11.
int delayvar = 2000; //This variable is the delay time during and between when each LED blinks.

void setup() {
  pinMode(LED, OUTPUT);
  Serial.begin (9600);
}

void loop() {
  digitalWrite(LED, HIGH);
  Serial.print(LED);
  Serial.print("\t"); // This prints a space between the value of LED and the value of delayvar the size of the tab key.
  Serial.print(delayvar);
  Serial.print("\n"); // This starts a new line on the serial monitor.
  delay(delayvar);
  digitalWrite(LED, LOW);
  delay(delayvar);
  LED = LED - 1;
  if (LED == 10) { // the == makes the computer check if LED = 10. If it is, the folowing things will happen.
    LED = 13;
    delayvar = delayvar - 200;
  }
  if (delayvar == 0) { // Here is another if statement that makes delayvar go back up to 2000 when it reaches 0.
    delayvar = 2000;
  }
}
```
### Evidence

Click [here](https://create.arduino.cc/editor/wswanso44/aac22c82-238b-4d9d-bd26-709a020c845f/preview) to view the code on arduino create.

### Image or Wiring

This project uses the same wiring as the finite LED blinker:

[image](https://github.com/Wesswanson/BasicArduino-1/blob/main/Screenshot%202020-11-18%20at%203.50.12%20PM.png?raw=true)

### Reflection
---
