   Table of Contents
1. Getting Started..........................................................................................................................1



















































   Getting Started
What you need:
Arduino UNO R4 WiFi(https://store-usa.arduino.cc/products/uno-r4-wifi, $27.50)
Setup:
1. Create a Arduino account by going to arduino.cc and clicking "login".
2. Open Arduino Cloud by going to app.arduino.cc.
3. Click "Create  New" then click "</> Sketch".
Now it will bring you to the newly created sketch and it will display:
/*

*/

void setup() {
    
}

void loop() {
    
}

So now we will start coding! But first you will need to learn so basic syntax.
1. A "//" is a note. Example: ```//This is a note.```
2. A "/* */" is a note that can go for multiple lines. Example: /*this is another note.*/ 
3. Void setup(){} is were you put all of the setup code. Example: 
\`\`\`void setup(){
pinMode(LED_BUILTIN, OUTPUT); //pinMode is a initializer for writing stuff to a pin. 
}
4. Void loop(){} is were you put all the code to do the stuff. Example:
void loop() {
    digitalWrite(LED_BUILTIN, HIGH);//digitalWrite is where it writes stuff to a pin. digitalWrite(pin, value);
}
5. A delay() is what it sounds like. It puts a delay in the code. Example:
void loop() {
    digitalWrite(LED_BUILTIN, HIGH);// Put the led on.
    delay(1000);// Wait 1 second(delays go in milliseconds)
    digitalWrite(LED_BUILTIN, LOW);// Put the led off.
    delay(1000);
}
 \`\`\`
Now that you learned all that, let's make a complete code!












/*
Blinking LED
*/

void setup() {
    pinMode(13, OUTPUT);//Put pin 13 as a output.
}

void loop() {
digitalWrite(LED_BUILTIN, HIGH);// Put the builtin led (LED_BUILTIN) on.
delay(1000);// Wait 1 second(delays go in milliseconds)
digitalWrite(LED_BUILTIN, LOW);// Put the builtin led off.
delay(1000);
}
Upload:
Now plug your board into your computer via a USB-C cable. Next upload your code by clicking the upload button, at the bottom will be the console, When upload is clicked the console should the say Console Verifying then say Console Uploading.
Basic Debugging:
If you don't know what debugging is it's fixing error that are displayed in the console. 
Main things to look for when debugging:
1. Missing ";", a missing ; will cause a error, example: 
Code:

/*
Blinking LED
*/

void setup() {
    pinMode(LED_BUILTIN, OUTPUT);//Put pin 13 as a output.
}

void loop() {
digitalWrite(LED_BUILTIN, HIGH)// Put the led on.
delay(1000);// Wait 1 second(delays go in milliseconds)
digitalWrite(LED_BUILTIN, LOW);// Put the led off.
delay(1000);
} 
Error:
/run/arduino/sketches/new_sketch_1746123215504/new_sketch_1746123215504.ino: In function 'void loop()':
/run/arduino/sketches/new_sketch_1746123215504/new_sketch_1746123215504.ino:11:1: error: expected ';' before 'delay'
 delay(1000);// Wait 1 second(delays go in milliseconds)
 ^~~~~
As you can see it says "error: expected ';' before 'delay'" that means it needs a ";" before the delay, but that go for any thing. Now if we a the semicolon to fix the code it works, here's the fixed code: 




/*
Blinking LED
*/

void setup() {
    pinMode(LED_BUILTIN, OUTPUT);//Put pin 13 as a output.
}

void loop() {
digitalWrite(LED_BUILTIN, HIGH);//With the added ;
delay(1000);// Wait 1 second(delays go in milliseconds)
digitalWrite(LED_BUILTIN, LOW);// Put the led off.
delay(1000);
} 

2. Missing ( or ), example: 
Code:
/*
Blinking LED
*/

void setup() {
    pinMode(LED_BUILTIN, OUTPUT);//Put pin 13 as a output.
}

void loop() {
digitalWrite(LED_BUILTIN, HIGH;// Put the led on.
delay(1000);// Wait 1 second(delays go in milliseconds)
digitalWrite(LED_BUILTIN, LOW);// Put the led off.
delay(1000);
}
Error:
run/arduino/sketches/new_sketch_1746123215504/new_sketch_1746123215504.ino: In function 'void loop()':
/run/arduino/sketches/new_sketch_1746123215504/new_sketch_1746123215504.ino:10:31: error: expected ')' before ';' token
 digitalWrite(LED_BUILTIN, HIGH;// Put the led on.
                             ^

 As you can see again part of the error is error: expected ')' before ';' token saying to add a ) before a ;  an easy way to find were this error is that the line that is highlighted red.
3. Misspelling, misspelling can be even harder to debug so here how to do it. Example: Code: 










/*
Blinking LED
*/

void setup() {
    pinMode(LED_BUILTIN, OUTPUT);//Put pin 13 as a output.
}

void loop() {
digitalWrite(LED_BUILTN, HIGH);// Put the led on.
delay(1000);// Wait 1 second(delays go in milliseconds)
digitalWrite(LED_BUILTIN, LOW);// Put the led off.
delay(1000);
} Error: /run/arduino/sketches/new_sketch_1746123215504/new_sketch_1746123215504.ino: In function 'void loop()':
/run/arduino/sketches/new_sketch_1746123215504/new_sketch_1746123215504.ino:10:14: error: 'LED_BUILTN' was not declared in this scope
 digitalWrite(LED_BUILTN, HIGH);// Put the led on.
              ^~~~~~~~~~
/run/arduino/sketches/new_sketch_1746123215504/new_sketch_1746123215504.ino:10:14: note: suggested alternative: 'LED_BUILTIN'
 digitalWrite(LED_BUILTN, HIGH);// Put the led on.
              ^~~~~~~~~~
              LED_BUILTIN
As you can see the error is error: 'LED_BUILTN' was not declared in this scope saying that it "was not declared in this scope" is saying that it wasn't a valid constructer. But an easy way to fix this is  "note: suggested alternative: 'LED_BUILTIN' so if we change LED_BUILTN to LED_BUILTIN are error go away!

Quiz:
1. Fix this code:
*
Blinking LED
*/

void setup( {
    pinMode(LED_BUILTIN, OUTPUT);//Put pin 13 as a output.
}

void loop() {
digitalWrite(LED_BUILTN, HIGH);// Put the led on.
delay(1000);// Wait 1 second(delays go in milliseconds)
digitalWrite(LED_BUILTIN, LOW)// Put the led off.
delay(1000);
2. How to wait 500 milliseconds in a sketch that will repeat the wait.
3. How to write to a pin.






Learning how to use Libraries and Variables
What you need:
Arduino UNO R4 WiFi.
SG-90 Servo
Setup:
1. Create a new sketch.
2. Insert the red wire into the 5v pin, the black pin into the GND pin and, the orange pin into digital pin 2. 
Creating the Code:
1. First, we will need to include the Servo library, to do that you will need to add 
'''#include <Servo.h>''' what you are doing is including the servo library(Servo.h) so that you can use it. 
2. Creating a variable, you are going to create a integer variable, to do that you will add 
'''int myNumber'''


























