# Debugging Project 2 - Non Contact IR Thermometer

There are many factors to take into consideration before finishing the prototype. We have check whether the prototype is working to its cap or not. 

This is where Debugging comes into play. We have debug the project and check whether the desired job is being done at every stage.

Before checking the components, we are assuming that wires, arduino nano and breadboard work fine and we are ot checking them.

#### Checking the condition of basic components:

1. LEDs can be checked by by making the come into contact with the respective terminals of a cell of full capacity. If they glow, they work. If they don't glow, they don't work.

2. The 18650 batteries we are going to use can be checked by connecting them to the working voltmeter. If the voltmeter shows a non zero value, they work. Else, they don't.

3. Piezo can be checked by making it come into conatct with the respective terminals of a power suplly which can vary voltage. If the buzzing varies proportionally with voltage, it works. If buzzing is constant or no buzzing is observed, it doesn't work.

4. OLED display can be checked by connecting it to arduino nano the right way (SCL - A5; SDL - A4; Vcc - 5V; GND - GND) and using all the correct values in the code such as Address of OLED, resolution of OLED, correct reset pin(-1 for OLEd with no in built reset pin) in the code. We can write the code we want it to execute(make sure no bugs in the code). If it displays the desired display, it works. else, it doesn't work. 

#### Check whether the proximity sensor is working or not:

This can be tested out by connecting it to arduino nano the right way(OUT - any digital pin(say D9), Vcc - 5V, GND - GND), LED to pin D8 and GND and using the following code. Upload it to nano and wave your hand near the sensor, if it glows with intensity to your choice, it works. 

```
#define IR_PIN 9   // OUT of IR pin is D9 of nano
#define LED 8      // + of LED is D8 of nano
bool IR_STATE = 0; // Initialising IR_STATE
void setup()
{
  pinMode(9, INPUT);    
  piMode(8, OUTPUT);
  IR_STATE = digitalRead(IR_PIN);   // IR_STATE will be 0 if object is near and 1 if object is not near
}

void loop()
{
  if(IR_STATE == 0)
  {
    digitalWrite(LED, HIGH);  // Glowing LED if hand is near 
  }
  else
  {
    digitalWrite(LED, LOW);  // Not glowing LED if hand is far
  }
}
```
#### Checking whether temperature sensor is working or not:

This can be tested out by connecting it to arduino nano the right way(SCL - A5; SDA - A4; VIN - 5V; GND - GND) and using the following code. Upload it to nano and see what temeperature it shows in the serial monitor. if it shows correct, it works. Else, you can replace it. 

```
#include <Wire.h>
#include <Adafruit_MLX90614.h>
Adafruit_MLX90614 mlx = Adafruit_MLX90614();
void setup() {
  Serial.begin(9600);
  Serial.println("Adafruit MLX90614 test");  
  mlx.begin();  
}
void loop() {
  Serial.print("*C\tObject = "); Serial.print(mlx.readObjectTempC()); Serial.println("*C");
  Serial.print("*F\tObject = "); Serial.print(mlx.readObjectTempF()); Serial.println("*F");
  Serial.println();
  delay(500);
}
```
#### Checking whether the charging module is working or not:

This can be done by using the similar setup as we did in project 4(portable power supply).

We connect the LCD voltmeter to batteries and try to charge them. 

If the voltmeter shows increase in voltage, they are charging. 

If not, check for bad connections and bad soldering joints and rectify them. If not working still, the module has to be replaced. 

### Final assembly:

At this stage, every basic component passed the quality check and are working good individually. 

We have check once more after assembling the prototype and make sure no further bugs are present.

#### If LEDs donot glow properly:

Check for bad connections and soldered joints. 

If they are all fine, check for any misconncetion in wires.

Check the pull up resistor for LED, if it is not working proeprly, LED might have burnt. Replace it to use the device properly.

If they are also fine, then bugs in the code is the only problem. Rectfying it should solve the problem.

#### If OLED display doesn't work properly:

Check for bad conncetions and soldered joints.

If they are all fine, check for any misconncetions in wires.

Check the voltage input for OLED, If it is more than not in recommneded range, use step down module or change the power source. 

If they are also fine, then bugs in the code is the only problem. Rectifying it should solve the problem.

#### If piezo doesn't buzz properly:

Check for bad conncetions and soldered joints.

If they are all fine, check for any misconncetions in wires.

Check the pull up resistor for piezo, piezo might have broken. Replace it to use the device properly.

If they are also fine, then bugs in the code is the only problem. Rectifying it should solve the problem.

#### If device is getting heated up:

This probably occurs if the resistance provided by pull ups is not sufficient. Check for it.

Do not use the device and turn off it for a while. 

Check the voltage input for arduino, If it is more than not in recommneded range, use step down module or change the power source. 

Chcek the voltage inputs for the other componenets similarly. 

# Debugging Project 6 - Desktop GUI MP3 Player

There are many factors to take into consideration before finishing the prototype. We have check whether the prototype is working to its cap or not. 

This is where Debugging comes into play. We have debug the project and check whether the desired job is being done at every stage.

While writing the code, we should be very careful withh syntax. Most of the code bugs are syntax errors only. 

From minitask_2.md, we take the requirements of the app. They are, 

1. Play .mp3 files
2. Create playlist
3. Navigate through playlist
4. Pause and Stop on command
5. Scroll through the playing .mp3 file
6. Show us the duration of .mp3 file and our current position

#### Check whether the app GUI is working or not:

The app GUI doesn't work when we get bugs at the start where we initialise the app using Tkinter. 

If we get bugs there, we get error and we won't be able to see the GUI. 

Make sure we get the Tkinter synatx correct.

#### Check whether the app is able to play .mp3 files:

This is our primary requirement besides others.

We have to check for bugs at pygame mixer initialisation and at play function. 

If they are correct we can play the .mp3 file in the playlist. 

Make sure we get the pygame syntax correct.

#### Check whether the app is able to create playslist:

This is our next important requirement. 

We have to check for bugs at creating master frame, playlist definition, add songs and delete songs menu definition and command definition. 

If we get bugs there, we might get error, it runs and does things that we don't want.

They use pygame and Tkinter modules in main. Make sure we get the syntax correct an we are doing what we want to do. 

#### Check whether we can navigate through playlist:

Navigation through playlist can be done in two ways:

1. Directly accessing the required .mp3 file by clicking it
2. Using next song and previuos song buttons

1st method always works because we have used the "ACTIVE" command to describe the current song and clicking the song activates it. 

2nd method is where we find more bugs compared to first.

Check for bugs at next song and previous song function definitions. 

They use mutagen and pygame modules in main. Make sure we get the synatx correct everywhere and we are doing what we want to do. 

#### Chek whether we can pause and stop:

If we cannot pause and stop or we get error while trying to pause or stop means tha there are bugs in pause and stop function definitions.

Check for bugs at pause and stop function definitions. 

They use pygame and mutagen modules in main. Make sure we get the synatx correct everywhere and we are doing what we want to do.

#### Check whether we can scroll through the .mp3 file:

Here, we can move through the .mp3 file only by scrolling throgh the position slider. 

If we can't move through it or the file isn't scrolling even if we move the slider means that there are bugs in the slide command.

check for bugs at slide function.

This uses pygame module in main. Make sure we get the syntax correct. 

#### Check whether the duration and position of .mp3 file playing are shown:

If we cannot see the position of .mp3 file playing and total duration/length of the .mp3 file, There are bugs in playtime function.

This is one of the complicated functions in the code where we use time module and pygame module. 

It is so because the concept involved is less and syntax is more.

Check for syntax mistakes there. Make sure we get the synatx correct everywhere and we are doing what we want to do.

















