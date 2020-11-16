# BasicArduino
I'm going to learn how to use an Arduino, and make awesome things with it!


## TableofContents
* [TableOfContents](#TableOfContents)
* [HelloArduino](#HelloArduino)
* [FiniteLEDBlink](#FiniteLEDBlink)

## HelloArduino

### Description & Code

```C++

 // Wes Swanson
// Hello arduino
/* This makes an LED blink once a second and prints the word blink twice a 
second.
*/
void setup() // Happens once, turns on the arduino uno before void loop starts.
{
 pinMode(13, OUTPUT); // This sets pin 13 to be an output
 Serial.begin(9600); // This turns on the serial moneter
}
void loop()
{
  digitalWrite(13, HIGH); // turns pin 13 on
  Serial.println("Blink"); // writes the word blink
  delay(500); // Delay 1/2 second
  digitalWrite(13, LOW); // turns pin 13 off
  Serial.println("Blink"); // writes the work blink
  delay(500); // Delay 1/2 second
} // End of loop, starts over again
```

### Evidence
[Here is my code on Arduino Create](https://create.arduino.cc/editor/wswanso44/c20ec904-8017-485b-bea4-df879d8c8323/preview)

### Image or Wiring

### Reflection

## FiniteLEDBlink

### Description & Code

```C++
Code Goes Here
```

### Evidence

### Image or Wiring

### Reflection
