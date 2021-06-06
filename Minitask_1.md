# Project 1 - Automatic Water Tap
  Description:
    This project enables us to operate tap only when required and there won't be an human errors.
    For example, forgetting to shut the tap off and not turning it off properly etc...
  Components required:
    1. Arduino Uno R3 
    2. Bistable Solenoid Valve
    3. L293D Motor Driver IC
    4. IR sensor
    5. Breadboard
    6. LED
    7. Resistors
    8. Connecting wires
  Ideation:
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
    When the valve is opened we have to make LED glow and when closed, stope the LED.
  Prototyping and testing:
    I have done a simplified version of the project on tinkercad. I'm providing the link for the circuit design.
    https://www.tinkercad.com/things/fdK7WbLImMX
  Comments:
    The project blog suggested to use bistable solenoid valve only since it has two normal states and a single pulse is enough for it reach the other.
    They have explained some cases of power cuts where the disadvantages are there. 
    If power is cut when it is in open state, it remains open until the power is back on.
    If power is cut when it is in closed state, it remains closed until the power is back on.
    Manual operation has to be done in both cases.
    In my point of view, monostable solenoid valve is a better choice. 
    Because it has only one normal state(that can be chosen as NC) and as long as pulse is given, it stays at Open and returns to closed immediately.
    This solves the first case because pulse is cut off when power is cut. This saves water without involving humans in atleast one case. 
    
    
    
