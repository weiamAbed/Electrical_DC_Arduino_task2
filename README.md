# Electrical_DC_Arduino_task2
This repository is for task 2 of the ELECTRICAL track of my summer training at Smart-Methods

-----------------------------------------------------

# Steps

1- Add a battery

2- Add Arduino and connect it's power and ground to the battery

3- Add a potentiometer and connect it to the Power, Ground, A0 in the Arduino.

4- Add hbridge and connect it to power and ground.

5- Add two DC Motors and connect it to the hbridge outputs.

6- Assign the motors to digital inputs 5,6,9,10 To the Arduino.

# Code

    //Potentiometer
      int pot=A0; 

    //Motor A
      int Dc_dir1_A=5;
      int Dc_dir2_A=6;

    //Motor B
      int Dc_dir1_B=9;
      int Dc_dir2_B=10;


      void setup(){

          pinMode(pot, INPUT);
          pinMode(Dc_dir1_A, OUTPUT);
          pinMode(Dc_dir2_A, OUTPUT);
          pinMode(Dc_dir1_B, OUTPUT);
          pinMode(Dc_dir2_B, OUTPUT);
      }


    void loop(){

    int speed = analogRead(pot);

    if(speed >= 512) {

         speed = map(analogRead(pot), 512, 1023, 0, 255);

         analogWrite(Dc_dir1_A, 0);
         analogWrite(Dc_dir2_A, speed);

         analogWrite(Dc_dir1_B, speed);
         analogWrite(Dc_dir2_B, 0);

    }

    else {
  
        speed = map(analogRead(pot), 512, 0, 0, 255);

        analogWrite(Dc_dir1_A, speed);
        analogWrite(Dc_dir2_A, 0);

        analogWrite(Dc_dir1_B, 0);
        analogWrite(Dc_dir2_B, speed);
     }

    } 

# Link

To Simulate in Tinkercad: "https://www.tinkercad.com/things/5You570WjGD"

# Figure

<img width="930" alt="DC_Motor" src="https://user-images.githubusercontent.com/63375443/124164578-7dcf5500-daa9-11eb-8f8e-d2a0f69ea28a.png">

# Video

https://user-images.githubusercontent.com/63375443/124165039-11a12100-daaa-11eb-9e8f-094b087d191b.mov



