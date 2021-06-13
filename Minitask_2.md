# Project 2 - Non Contact IR thermometer

## Problem Statement:

Design a body thermometer which can measure temperature of body withut touching the body. 

## Ideation and Planning:

The way the prototype works is as follows,

*Proximity Sensor* -> *Arduino* <- *Temperature Sensor*
                          |
                          v
               *OLED Display, Piezo, LEDs*
               
Options for proximity sensors are, 

1. Ultrasonic Distance Sensor(HC SR04)
2. IR proximity sensor(FC 51)

Hc SR04 is a device which can calculate at what distance the object is and we provide signal accordingly. 

It is an effort to program the circuit to act according to distance.

Instead we can use the FC 51 which doesn't calculate distance but tells whther the object is in certain distance or not and provides signal accordingly.

I prefer IR sensor(FC 51) as proximity sensor for this project cost wise as well as effort wise.

It is obvious to use non contact sensors. The best choice is to use radiation sensors like GY 906 IR temperature sensor. 

Choice of Arduino is also important. We need smaller arduino with more pins preferably. Arduino Nano serves best to this purpose.

The hardware requirements are all met at this point and now it is time to assemble and test the prototype.

We have to take input from proximity sensor and if the object is in the proximity, we then take the input from temperaure sensor.

The temperature is then shown in the OLED display.

If the temperature is above the safe limit, red LED blinks and piezo buzzes for two seconds. 

If the temperature is below the safe limit, green LED blinks and piezo buzzes for a second.

The circuit should look something like this. 

<img width = "800" height = "400" src = "https://user-images.githubusercontent.com/85270751/121802169-c937d580-cc58-11eb-8235-9130f905eef7.jpg">

We can also add a charging module so that the prototype can be made rechargable.

For example, TP4056 Li-ion charging module with step up converters so that Arduino gets the voltage it needs. 

<img width = "600" height = "400" src = "https://user-images.githubusercontent.com/85270751/121802407-bc67b180-cc59-11eb-90b7-851205f217c1.png">

We can also add switch between batteries and Arduino so that we can get the temperature reading only when we want.

This also saves the battery power.

The code for arduino is given below in .txt format.

[project2.txt](https://github.com/SaiShashankGP/Task-1/files/6643663/project2.txt)

# Project 6 - Desktop GUI MP3 Player

## Problem Statement:

Creating an MP3 player with GUI tools like Tkinter and plays .mp3 files using pygame. 

## Ideation and Planning:

We want our MP3 player to 

1. Play .mp3 files
2. Create playlist
3. Navigate through playlist
4. Pause and Stop on command
5. Scroll through the playing .mp3 file
6. Show us the duration of .mp3 file and our current position

Why are we using Tkinter? Because it is one of the most common and simple modules which deal with GUI in python.

Why are we using pygame? Because it has simple functions that deal with .mp3 files. 

Why are we not using moviepy? Moviepy module is mainly used for editing and merging. It is not used to play songs. 

We not only use those two modules but also other modules which come in handy like Time and mutagen. 

Below is the code for the MP3 player by codemy.com

https://github.com/flatplanet/Intro-To-TKinter-Youtube-Course/blob/22e726271e3ebc3e7ac1938f4d505b5d5a10588c/player.py


