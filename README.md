# GRBL BASED CNC MACHINE

![image](https://user-images.githubusercontent.com/19898602/134227224-73fd4ca8-d6e8-4f99-ba57-a33c02d36386.png)


This CNC is based on GRBL0.9 Firmware and CNC V3 shield GRBL is Hacked for Z-axis Servo.

# OVERVIEW

This CNC is based on GRBL0.9 Firmware and CNC V3 shield GRBL is Hacked for Z-axis Servo.

CNC Shield & GRBL combinly works very preciselyIt is loaded with very useful functions like Hard limit, Soft limit, Homing, etc![How to configure 6-Axis MP-6050 Gyroscope Sensor for first run beginner tutorial_1](https://user-images.githubusercontent.com/19898602/134229334-244a5538-f56a-43d1-a533-082602daca71.gif)


This is about how to make

GRBL+CNCV3 shield+Arduino based CNC machine

This guide include all necessary instruction required

> like How to assemble CNC machine

> How to Load GRBL to arduino

> Inkscape extension installation

> GRBL Configuration & G-code streaming



It is loaded with very useful functions like Hard limit, Soft limit, Homing, i will guide you in detail how to Make GRBL Based mini CNC machine at home

Before moving fuurther I would like to tell you something about PCB

Yes PCB are the heart of the electronics based project usually we hesitate to try custom PCB and opt to homemade solutions

like breadboard or Zero PCB earlier I also was in the same boat, I hesitate to try custom PCB my belief was they are much expensive.

but then I came to know about [JLCPCB.com](https://jlcpcb.com/IAT) and I was totally surprised how low price PCB's are they offering 

there PCB quality is best in market, now I always go with PCB for my project and [JLCPCB.com](https://jlcpcb.com/IAT) is my trusted 

PCB manufacturer, you can also try there PCB service for more details you can visit their website [JLCPCB.com](https://jlcpcb.com/IAT)
![image](https://user-images.githubusercontent.com/19898602/134224512-bea8d1c8-9ebe-448d-bbba-0cbecb42d528.png)


![image](https://user-images.githubusercontent.com/19898602/130722577-c30b7b43-ea89-4847-9c6b-058f9fabeda3.png)![image](https://user-images.githubusercontent.com/19898602/130722585-b5268db1-5f17-428f-ba60-b823140f2a70.png)



#   Video 

https://youtu.be/k1vzT-T8LJA

Watch this video it will clear you how to make and operate CNC machine



# Material Required

Material Required

This are the list of some use full material required

> Arduino UNO--------------------------------------QTY- 1 

> CNC V3 Shield------------------------------------QTY-1 

> servo motor----------------------------------------QTY-1 

> A4988 Stepper driver shield--------------------QTY-2 

> Old scrap DVD Drives---------------------------QTY-2 

> Some push buttons as limit S/W---------------QTY-2 

> Aacrylic sheet for base Pen holder (slavege from DVD Drive) 

> Some wires Hardware like nut bots etc.



# Software Required


> Arduino IDE


> GRBL LIBRARY :- Click here to download

> INKSCAPE


> SERVO CONTROL EXTENSION :-Click here to download

> UNIVERSAL G-CODE SENDER : - Click here to download




# Machine Assembley



Place X-axis Horizontally on the bolt mounted on acrylic sheet Four bolt mounted on a metal sheet to fit Y-axis on it.

Now place the Pen up down holder on y axis whit the help of A bolt through the center Now place Y-axis on metal sheet and place it vertically on X-axis. 

Now fit servo motor so that it will move z-axis which is our pen up and down Now mount CNC shield on Ardunino Do wiring 

AS shown in wiring circuit as in Next step For better understand please watch Video & pic attached here

![image](https://user-images.githubusercontent.com/19898602/134228176-28d0c9a4-3003-47c2-bfe8-25cb0116a2bf.png)![image](https://user-images.githubusercontent.com/19898602/134228225-28658d11-9143-4eea-b940-66017e06c769.png)


![image](https://user-images.githubusercontent.com/19898602/134228268-3425c254-3b0b-489e-8383-d4e9466901e0.png)![image](https://user-images.githubusercontent.com/19898602/134228287-477da10e-097f-4559-b448-1595e1932c3a.png)




## Wiring Diagram

![image](https://user-images.githubusercontent.com/19898602/134228406-61f4f5f5-72b0-4f3a-84de-0b386f4ef6be.png)


Do wiring as shown here in image

Limit switch are optional

You can use them by changing the GRBL setting as below

> $21=0 (hard limits, bool)

to

> $21=1 (hard limits, bool)


# GRBL Loading to Arduino

![image](https://user-images.githubusercontent.com/19898602/134228748-195e3dd7-d129-4a98-bea8-bb5c326bf3a7.png)

Link to download GRBL Setup

http://www.mediafire.com/file/c36xny4qw9b7s5k/MI_G...

Download the library file unzip it

and load to arduino

Now go to File>Example>grbl upload compile and upload code to arduino

Note:- delete any previously loaded GRBL library

![image](https://user-images.githubusercontent.com/19898602/134228880-8a9569a4-8163-4734-90d8-08472f83c498.png)


# G-CODE Setup in Inkscape


![image](https://user-images.githubusercontent.com/19898602/134228980-950f4e0d-2a6b-4a71-b73e-67330c09d9bf.png)


Again we are using here INKSCAPE software to make G-code

As we are using GRBL & CNC Shield for this machine s

o it will not support a servo motor as a Z-Axis

so here some hack by doing so we can able to manage Servo works on Z-axis

you need to add MI Extension here to get it work with Z-axis Servo

Download link http://www.mediafire.com/file/nl4w871suk192x2/MI_...

after download add this files to the

inkscape directory>Share>Extension folder

Now open inkscape set page size 40 x 40mm

draw what you want to plot

select image go to convert to path

then go to extension click on MI GRBL Z-AXIS SERVO CONTORL

> Servo up = M3

> Servo down = M5

> X-axis speed = 2000

> Y-axis speed = 2000 S

> Servo angle = 90

> Delay = 1

> Directory = as per you convenient or keep as it is

> File name = as per you convenient or keep as it is

> Clik on Apply now you G-code is saved @ location you mention



# GRBL Configuration & Streaming G-code

GRBL Configuration & Streaming G-code

Download link for Universal Gcode sender

https://www.mediafire.com/?2l16dvqivwgc9el

Open Universal G-code sender (Arduino must stay connected with PC/LAPTOP)

> Select COM port

> Set Baud rate 115200

> clik on "OPEN"

> go in "COMMANDS" Tab

> enter $$ for GRBL configuration

> Example Suppose we want to change the $0(step pulse, usec) value from 10 to 20

> so enter in command line $0=20 & hit enter its done

# My GRBL SETTING

$0=10 (step pulse, usec)

$1=25 (step idle delay, msec)

$2=0 (step port invert mask:00000000)

$3=0 (dir port invert mask:00000000)

$4=0 (step enable invert, bool)

$5=0 (limit pins invert, bool)

$6=0 (probe pin invert, bool)

$10=3 (status report mask:00000011)

$11=0.010 (junction deviation, mm)

$12=0.002 (arc tolerance, mm)

$13=0 (report inches, bool)

$20=0 (soft limits, bool)

$21=0 (hard limits, bool)

$22=0 (homing cycle, bool)

$23=0 (homing dir invert mask:00000000)

$24=25.000 (homing feed, mm/min)

$25=500.000 (homing seek, mm/min)

$26=250 (homing debounce, msec)

$27=1.000 (homing pull-off, mm)

$100=5.000 (x, step/mm)

$101=5.000 (y, step/mm)

$102=100.000 (z, step/mm)

$110=500.000 (x max rate, mm/min)

$111=500.000 (y max rate, mm/min)

$112=500.000 (z max rate, mm/min)

$120=10.000 (x accel, mm/sec^2)

$121=10.000 (y accel, mm/sec^2)

$122=10.000 (z accel, mm/sec^2)

$130=40.000 (x max travel, mm)

$131=40.000 (y max travel, mm)

$132=200.000 (z max travel, mm)

ok

Now time to stream Gcode to machine go to "FILE MODE" Tab Brows your gcode file and hit enter that's it

your machine start plotting Hope you like this Comment below if any doubt



![How to configure 6-Axis MP-6050 Gyroscope Sensor for first run beginner tutorial_1](https://user-images.githubusercontent.com/19898602/134229386-294431d4-dead-44d6-989a-5057ebc014c5.gif)
