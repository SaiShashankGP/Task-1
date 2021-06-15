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

The power to all the operation happening here comes from 18650 batteries. They are made rechargable by adding TP 4056 module.

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

![project2](https://user-images.githubusercontent.com/85270751/121809618-1e84de80-cc7b-11eb-8728-9f85304606a3.gif)


#### Reference Project:

https://www.instructables.com/Portable-Power-Supply-18650-Battery/

#### Comments:

Some modification in circuit like the 1\*6 socket to USB I\/O port can make it useful for moblies etc...

# Project 5 - Line following bot
#### Description:

This bot follows the line infront of it and stops when the line stops.

This product uses Raspberry pi and python to achieve the task.

#### Components required:

1. Raspberry pi 
2. DC motors
3. Motor controller board
4. Battery holder and Batteries
5. Wheels
6. Line sensors

#### Ideation:

Connect the motors to Motor contrller board. Connect motor controller board to raspberry pi and battery holder.

Conenect the line sensors to raspberry pi. 

The battery provides the power to run motors. Now, program raspberry pi to take input from line sensors and make motors run according to input.

Connect the wheels to motors and put the whole circuitry inside a box and wheels outside the box.

For example, take two line sensors and mark one as left and other as right. 

If left sensor detects line and right doesn't, tilt right.

If right sensor detects line and left doesn't, tilt left.

If both detect line then move forward. 

If both doesn't detect line the stop.

#### Reference project:

https://projects.raspberrypi.org/en/projects/rpi-python-line-following

#### Comments:

This is a simple version of sensory robot. We can use similar logic and make it ultrasonic frequency following robot.

Like, producing a certain frequency and having a sensor that can detect the origin of frequency and move in that direction.

That would also have some limitations and we can improve further to make it autonomous.

# Project 6 - Desktop GUI MP3 Player app
#### Description:
This app is user intearcting mp3 player in which we can 
1. play mp3 files on the device
2. create playlists
3. shuffle playlists
4. Increase and decrease volume

#### Python modules used:

1. Tkinter
2. Pygame
3. Mutagen.mp3
4. Time

#### Ideation:

Here, I will be showing a basic play, pause and stop mp3player. It is just to show how it can be done.

We create a GUI app using Tkinter. 

```
from tkinter import *

root = Tk()
root.title("MP3 Player")
root.iconbitmap("/Desktop/Python_Project/mpp3player.py")
root.geometry(500x500)

root.mainloop()
```
We the import pygame and start by creating place for playlist.

```
import pygame

pygame.mixer.init()

playlist_area = Listbox(root, bg = "black", fg = "green', width = 60, selectbackground = "grey", selectforeground = "white")
playlist_area.pack(pady = 20)
```

We then give an option to add .mp3 file

```
from tkinter import filedialog

def add_song():
    song = fledialog.askopenfilename(initialdir = '/Music', title = 'Choose a song', filetypes = (('mp3 files', '*.mp3'), )
    song = song.replace("/Music/", "")
    song = song.replace(".mp3", "")
    playlist_area.insert(song, END)
  
my_menu = Menu(root)
root.config(menu = my_menu)

add_song_menu = Menu(my_menu)
my_menu.add_cascade(label = "Add Songs", menu = add_song_menu)
add_song_menu.add_command(label = "Add one song to playlist", command = add_song)
```
Now, we can define play, pause and stop buttons.

```
def play():
    song = song_box.get(ACTIVE)
    song = f'/Users/saishashankgp/Desktop/{song}.mp3'

    pygame.mixer.music.load(song)
    pygame.mixer.music.play(loops = 0)

def stop():
    pygame.mixer.music.stop()
    song_box.selection_clear(ACTIVE)
  
def pause():
    pygame.mixer.music.pause(ACTIVE)
    pygame.mixer.music.unpause(ACTIVE)

play_btn = PhotoImage(file = '/Desktop/play.png')
pause_btn = PhotoImage(file = '/Desktop/pause.png')
stop_btn = PhotoImage(file = '/Desktop/stop.png')

controls_frame = Frame(root)
controls_frame.pack()

play_button = Button(controls_frame, image = play_btn, borderwidth = 0, command = play)
pause_button = Button(controls_frame, image = pause_btn, borderwidth = 0, command = pause)
stop_button = Button(controls_frame, image = stop_btn, borderwidth = 0, command = stop)

play_button.grid(row = 0, column = 0, padx = 10)
pause_button.grid(row = 0, column = 1, padx = 10)
stop_button.grid(row = 0, column = 2, padx = 10)
```
These codeblocks when put together give a simple play-pause-stop mp3 player.

#### Reference project:

https://www.youtube.com/watch?v=CXMcNbo8PLE&list=RDCMUCFB0dxMudkws1q8w5NJEAmw&start_radio=1&rv=CXMcNbo8PLE&t=0

#### Comments:

This is a pretty hard one to do as said in the reference project. 

It was very long to code all those and understand everything.

But I think when given a sufficient amount of time and as a group, it can be done with much more improvements than the above one.

# Project 7 - Seismograph
#### Description:
Home made seismograph can be used to know when an earthquake happens near our home and we can take measures accordingly.
This uses some simple components like Raspberry pi, Raspberry Shake OS etc... 

#### Components required:

1. Raspberry pi
2. Racotech RGI-20DX geophone
3. Shake RS1D board
4. micro SD card

#### Prototyping and Testing:

First, we need to connect the geophone's terminals to positive and negative ( for this, we have twist the wires and then connect)

Place the raspberry pi in the raspberry shake enclosure and insert the micro SD card given by the raspberry shake into raspberry pi.

Enclose the geophone in a plastic casing in the raspberry shake board.

We have to level it by adjusting the levelling screws and there is a given spirit level in the board.

We then conncet the whole apparatus to the router via ethernet. Makers suggest we keep it on ground.

We then configure the seismograph by connecting it to Raspberry shake database.

We then have a working seismograph in our home.

<img width = 800 height = 600 src = "https://user-images.githubusercontent.com/85270751/121531594-327ed500-ca1c-11eb-8e1e-ecc80fd2c73e.jpg">

#### Reference project:

https://magpi.raspberrypi.org/articles/build-a-seismograph-with-raspberry-shake

#### Comments:

This is a pretty simple yet very useful project.

We have yet to know the underlying mechanism to fully understand how this works.

# Project 8 - Simple Lie Detector
#### Description:

This simple circuit is based on an experimental conclusion that, "Human skin varies onductance depending on our state".

This property can be usedd to differentiate truth from lie.

Ofcourse this simple project is not the most accurate but it works wth dependable accuracy.

#### Components required:

1. Arduino nano
2. LEDs
3. Breadboard
4. resistors

#### Ideation:

We take the input to arduino is the voltage at our fingers.

This fluctuates rapidly but whenever someone lies, this changes even more.

Those values differ from subject to subject and is to adjusted every time.

#### Prtotyping:

<img width="600" height = "200" alt="Project 8" src="https://user-images.githubusercontent.com/85270751/121800186-f03cda00-cc4d-11eb-8009-64528172e767.png">

#### Reference project:

https://create.arduino.cc/projecthub/BuildItDR/arduino-lie-detector-a0b914?ref=tag&ref_id=arduino&offset=8

#### Comments:

This is a very vague project and has t be improved further.

More data is needed to proceed further and generalise it to everyone and every condition of the user.

Accuracy is also an important factor and it also needs to be improved.

# Project 9 - Automatic Brigtness Adjustment in PC

#### Description:

This project enables PC to adjust brightness on its own.

This is a thing that is seen only in smart phones but not in PCs.

#### Components required:

1. Arduino Pro Micro
2. Photoresistor

#### Ideation:

We collect the data of brightness in the room by the output of Photoresistor. 

The data collected is sent to PC by serial communication of Arduino. 

We have some python libraries which control screen brightness and also work with serial communication. 

Those are pyserial and screen-brightness-control. 

We then write a python program telling the computer to adjust to the brightness level of room using the two libraries mentioned. 

#### prototyping and testing: 

https://www.youtube.com/watch?v=j0BjPwwgyi0

#### Reference project:

https://www.instructables.com/Hack-Computer-to-Make-It-Smart/

#### Comments:

This is a cool project but it is a not worth it. Instead I would adjust brightness manually. 

But the underlying concept is very interesting. It is worth learning it. 

# Project 10 - CO2 concentration Indicator
#### Description:

This project enables us to measure CO2 concentration and indicate us whether its safe or not via LED "dangeometer"

#### Componenets required:

1. SCD30CO2 and RH/T sensor
2. ESP32 NodeMCU
3. LED 10 segment bar graph(Blue, Green, Yellow, Red)

#### Ideation:

It is simple in assembly but prograaming the NodeMCU is the tough part.

we take input from SCD30 CO2 sensor and NodeMCU processes it. 

Depending on the data from SCD30 CO2 sensor, LED bar graph gets to display the level of CO2 conc. 

#### Prototyping:

Here is the Github file for the code(code by mosivers from instructables.com) and Photo of circuit design

https://github.com/vonsivers/LED-Bargraph-CO2-Sensor/blob/08222008966075d18f10085d19e68a61365c593f/code/LEDbargraph_CO2sensor/LEDbargraph_CO2sensor.ino

<img width="426" alt="project 10" src="https://user-images.githubusercontent.com/85270751/121884915-230bce80-cd31-11eb-854f-38594e9b0f4e.png">

#### Reference project:

https://www.instructables.com/Simple-LED-Bar-Graph-CO2-Sensor/

# Project 11 - Dice Rolling Simulator
#### Description: 

This is a GUI app which mimicks the fair dice rolling. 

#### Ideation:

We use Tkinter(for GUI), PIL(for dice) and random(for fair dice rolling) modules here. 

here is he code,

```
import tkinter
from PIL import Image, ImageTk
import random

# top-level widget which represents the main window of an application
root = tkinter.Tk()
root.geometry('400x400')
root.title('DataFlair Roll the Dice')

# Adding label into the frame
BlankLine = tkinter.Label(root, text="")
BlankLine.pack()

# adding label with different font and formatting
HeadingLabel = tkinter.Label(root, text="Hello from DataFlair!",
   fg = "light green",
     bg = "dark green",
     font = "Helvetica 16 bold italic")
HeadingLabel.pack()

# images
dice = ['die1.png', 'die2.png', 'die3.png', 
    'die4.png', 'die5.png', 'die6.png']
# simulating the dice with random numbers between
# 0 to 6 and generating image
DiceImage = ImageTk.PhotoImage(Image.open(random.choice(dice)))

# construct a label widget for image
ImageLabel = tkinter.Label(root, image=DiceImage)
ImageLabel.image = DiceImage

# packing a widget in the parent widget 
ImageLabel.pack( expand=True)

# call the mainloop of Tk
# keeps window open
root.mainloop()
```

#### Reference project:

https://data-flair.training/blogs/dice-rolling-simulator-python/


#### Prototyping and testing:

# Project 12 - YouTube video downloader
#### Description:

The project name is self expalantory. 

We write a python code which enables us to download YouTube videos.

#### Ideation:

We use pytube(for YouTube download) and sys(for CLI input) modules. 

Here is the code(I have slightly improvised it from the reference project).

```
import sys
from pytube import YouTube

link = input("Paste the link here: ")

print("Video downloading")

link = YouTube(link)
video = link.streams.first()
video.download()

print("Video downloaded")
```
#### Reference project:

https://data-flair.training/blogs/python-youtube-downloader-with-pytube/

#### Prototyping and testing:

![project12](https://user-images.githubusercontent.com/85270751/121932546-9ed23f00-cd62-11eb-85e6-f9f39df123f6.gif)

# Project 13 - Random Passsword Generator
#### Description:

This application is very helpful in setting a strong password to our requirement. 

#### Ideation:

We use Tkinter(for GUI), random(for password generation), pyperclip(to copy automatically to clipboard) modules. 

Here is the code, 

```
from tkinter import *
import pyperclip
import random
iport string

root = Tk()
root.geometry("500x500")
root.title("Password Generator")

pass_len_label = Label(root, text = 'PASSWORD LENGTH').pack()
pass_len = IntVar()
length = SpinBox(root, from_ = 8, to_ = 32, textvariable = pass_len, width = 15).pack()

pass_str = StrVar()
def Generator():
    password = ''
    for x in range(0, 4):
        password = random.choice(string.ascii_uppercase) + random.choice(string.ascii_lowercase) + random.choice(string.digits) + random.choice(string.punctuations)
    for y in range(pass_str.get()-4):
        password = password + random.choice(string.ascii_uppercase) + random.choice(string.ascii_lowercase) + random.choice(string.digits) + random.choice(string.punctuations)
    pass_str.set(password)

def Copy_password():
    pyperclip.copy(pass_str.get())

Button(root, text = 'GENERATE PASSWORD', command = Generator).pack(pady = 5)

Entry(root, textvariable = pass_str).pack()

Button(root, text = 'COPY TO CLIPBOARD', command = Copy_password).pack(pady=5)
```

#### Reference project:

https://data-flair.training/blogs/python-password-generator/

#### Prototyping and testing:










