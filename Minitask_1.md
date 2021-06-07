# Project 1 - Automatic Water Tap
#### Description:

This project enables us to operate tap only when required and there won't be an human errors.
    
For example, forgetting to shut the tap off and not turning it off properly etc...
    
#### Components required:

1. Arduino Uno R3 
2. Bistable Solenoid Valve
3. L293D Motor Driver IC
4. FC 51 IR proximity sensor
5. Breadboard    
6. LED
7. Resistors
8. Connecting wires
    
#### Ideation:

Our goal here is to automate the water flow. 
    
One can control the water flow by using a valve and a solenoid valve is used to control the flow of fluid using eletric signals.

Controlling a solenoid valve is similar to motor. So, L293D IC is used.

We need to program the whole system to act accordingly. So, an arduino is used.

RGB LED indicates the state of valve to better understand the system working.

We should make the valve be in NC position(Normally Closed).

We need to take IR sensor reading as input constantly. Sensor detects the object(Hand here) within its range of detection.

When it detects the object, we need to make the valve rotate so that the water flow is allowed.

It has to allow the water flow as long as the object is in the detection range.

If the object moves out of detection range, it has to wait for a second or two and then return to its initial position.

When the valve is opened we have to make LED glow and when closed, off the LED.
    
#### Prototyping and testing:

I have done a simplified version of the project on tinkercad. I'm providing the link for the circuit design.

https://www.tinkercad.com/things/fdK7WbLImMX

<img width="600" alt="Screenshot 2021-06-07 at 11 32 22 AM" src="https://user-images.githubusercontent.com/85270751/120966678-2ed12100-c784-11eb-86c9-45b5ad00c963.png">

#### Reference project:

https://www.instructables.com/AUTOMATIC-WATER-TAP/

#### Comments:

The project blog suggested to use bistable solenoid valve only since it has two normal states and a single pulse is enough for it reach the other.

They have explained some cases of power cuts where the disadvantages are there. 

If power is cut when it is in open state, it remains open until the power is back on.

If power is cut when it is in closed state, it remains closed until the power is back on.

Manual operation has to be done in both cases.

In my point of view, monostable solenoid valve is a better choice. 

Because it has only one normal state(that can be chosen as NC) and as long as pulse is given, it stays at Open and returns to closed immediately.

This solves the first case because pulse is cut off when power is cut. This saves water without involving humans in atleast one case. 

# Project 2 - Non contact IR Thermometer
#### Description:

This IR Thermometer reads the temperature of a person or object in its range without touching it.

#### Components required:

1. Arduino nano
2. 18650 batteries
3. GY 906 Temeperature sensor
4. FC 51 IR proximity sensor
5. MT 3608 boost converter
6. TP 4056 Li-ion charger module
7. OLED display
8. Green and Red LEDs
9. Piezo buzzer

#### Ideation:

We detect the temperature of object by using GY 906 sensor. 

But we cannot detect temperature for objects that are beyond certain distance within the sensor accurately. 

So, we include a FC 51 proximity sensor to know if object is in range or not.

When object is in range, the detected temperature is taken as input and it decides the output of LEDs, OLED display, buzzer.

If the object's temperature is in normal, then the buzzer buzzes for a second normally, Green LED lights up while Red LED remains off and OLED displays the temperature.

If ithe objects temperature isn't normal, the the buzzer buzzes for two seconds with a bit high intensity, Red LED lights up and OLED displays the temperature.

After two seconds, all the indicators return to their original state and be ther until the next object is detected by FC 51.

The power to all the operation happening here comes from 18650 batteries. They are mage rechargable by adding TP 4056 module.

#### Prototyping and Testing:

All this circuitry goes into a case which is 3D printed. Only the IR proximity sensor, LEDs, OLED display and USB input for recharge is visible outside.

<img width = "600" alt = "project 2" src = "https://user-images.githubusercontent.com/85270751/120969759-2d095c80-c788-11eb-9a38-8403a7f062e3.jpg">

#### Reference Project:

https://www.instructables.com/DIY-Non-Contact-IR-Thermometer/

#### Comments:

This is automatic and detects temperature of object in its range automatically. 

We can include a switch between power and circuit and make it manual and use it at public place entrances as we see now.

# Project 3 - Password based Locking system
#### Description:

This is a simple passwrod based locking system where one enters a password and if it matches with the predefined password, they can access the door.

#### Components required:

1. 8051 Microcontroller
2. L293D motor driver IC
3. 16x2 LCD display
4. DC motor
5. 4x4 keyboard

#### Ideation:

Microcontroller is chosen here because we need to store a predefined password, take and process inputs and give outputs. 

First, we give the micricontroller a password. It stores it in its ROM.

We take input from keyboard which is the password given by user. The user sees a "\*" in place of his entered chracter on LCD.

The microcontroller checks whether the given input is equal to the predefined password.

If it matches, microcontroller makes LCD display "correct pasword" and it sends a signal to L293D IC such that the IC turns the motor to open the door.

If it doesn't match, the microcontroller sends signal to LCD such that it displays "wrong password" to user.

#### Prototyping and Testing:

<img width="600" alt="Screenshot 2021-06-07 at 3 39 54 PM" src="https://user-images.githubusercontent.com/85270751/120999427-b891e600-c7a6-11eb-9011-8bd8d5537c6e.png">

#### Reference project:

https://www.electronicshub.org/password-based-door-lock-system-using-8051-microcontroller/

#### Comments:

User gets infinite tries and once the password is set, user cannot change it via keyboard and instead should change the hardcoded password.

This can be improved by attaching an external storage for just the password to the microcontroller. 

Then hardcoding a certain input that can be given via keyboard which can act as an indication to microcontroller to change the password in the external storage.
# Project 4 - Portable Power Supply
#### Description:

This product can be used as power supply in other projects. 

This is like a DIY Power supply

#### Components required:

1. J5019 charging module with step up converter
2. 18650 battery
3. LCD display voltmeter
4. 1\*6 pin header socket
5. Slide switch 
#### Ideation:

<img src = "https://user-images.githubusercontent.com/85270751/121040880-e2abce00-c7cf-11eb-9aa0-fc2fc04586c8.png" width = "600" height = "600">

The image shows the circuitry involved.

When SW2A is in 1-2 position and SW1A is in 2-3 position, the voltmeter measures the voltage power supply is giving as output.

When SW2A is in 2-3 position and SW1A is in 2-3 position, the voltmeter measures the voltage across battery.

When SW1A is in 1-2 position, the voltmeter is in off state and doesn't display anything.

We can even adjust the voltage output because J5019 has such property.

#### Prtotyping and Testing:

https://user-images.githubusercontent.com/85270751/121068424-e4828b00-c7e9-11eb-8e8c-01774fc607c6.mp4

#### Comments:

Some modification in circuit like the 1\*6 socket to USB I\/O port can make it useful for moblies etc...

# Project 5 - Line following bot
#### Description:

This bot follows the line infront of it and stops when the line stops.

This product uses Raspberry pi and python to achieve the task.

#### Components required:

1. Raspberry pi 
2. DC motors
3. 
