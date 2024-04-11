
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
##  DATE: 11-04-2024
##  NAME: Suriya Pravin M
##  ROLL NO : 212223230223
##  DEPARTMENT: AI&DS
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM:
```
int in1=5;
int in2=6;
int en=3;
void setup()
{
  pinMode(in1, OUTPUT);
   pinMode(in2, OUTPUT);
    pinMode(en, OUTPUT);
}

void loop()
{
   analogWrite (en,225);
  digitalWrite(in1,LOW);
   digitalWrite(in2,HIGH);
  delay(500);
 
}
```
### OUTPUT
![Circuit](https://github.com/Suriya-Pravin-M/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/150010919/4ad1778e-6681-4474-abaa-38ba3321ac3c)
![Diagram](https://github.com/Suriya-Pravin-M/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/150010919/1b10e432-3c27-463a-82fc-ee9ffac00326)


### GRAPH AND TABULATION 
![Graph](https://github.com/Suriya-Pravin-M/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/150010919/9a663fc1-9dff-43c9-b765-baab436b2885)
![Table](https://github.com/Suriya-Pravin-M/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/150010919/9e193cc2-1a0a-4ad7-9632-b65eea8d0f27)


### RESULTS AND DISCUSSION 
The program to control the speed and the direction of a DC motor using L293D driver ic( H- bridge) is completed and executed successfully.
