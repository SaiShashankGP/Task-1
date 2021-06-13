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









