# stepper_tasmota

How to use it:
Wemos Pin	GPIO	Component	Servo Signal
D3	0	Relay1	EN
D4	2	PWM1	PLS
D5	14	Relay2	DIR
You must add support for Shutter in my_user_config.h file (оr flash your ESP8266 module with tasmota.bin file).

Run commands in the console to run the "Shutter" mode (you must first configure the GPIO!):
SetOption80 1 // enable Shutters support.
Shuttermode 5 // enable Shutter mode for servo.
PWMfrequency 200 // this is a global variable for all Servos.
SetOption15 0 // to control the storage of values.
ShutterRelay1 1


Run commands in the console to configure the motor operation:
ShutterPwmRange1 100, 500 //this is a global variable for all Servos.
ShutterOpenDuration1 0.5 // define the open time, in seconds.
ShutterCloseDuration1 0.5 // define the close time, in seconds.
ShutterMotorDelay1 0.2 // servo does not like abrupt start / stop.
Restart 1

