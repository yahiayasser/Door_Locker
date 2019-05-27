# Door_Locker
--------------
Door_Lock_project Two micro-controllers, one acts as a HMI (Human Machine Interface) This micro-controller has a Dio module, LCD Module, Keypad Module and UART Module This one will be used just interfacing with user. 

The other micro-controller will be responsible for controlling the motor (actuation part) This micro-controller has a Dio module, Timer Module, DC_Motor Module and UART Module This one will be used for just Controlling the motor that will act as the lock for the door. 

The scenario will be as following:  

1- first use Mode: 
the user will be prompted to enter pass and confirm it using keypad, if passwords are matched the password will be saved to the internal EEPROM of the first micro-controller. If the passwords are not matched it will tell you that the passwords are not matched and ask you to re-enter passwords.  

2- Operating Mode: 
LCD Shows Supported Operations: 
a- Open the door: If the user choose to open the door he will be prompted to enter the password, if he fails with 4 trials, he will have to wait for 30 seconds to re-enter the password again. if the password is right, a message will be sent to the other micro-controller using uart to open the door. 
b- Change Password : user must enter the old password first to change.  

3- Opening the door: 
When the message of opening the door will be received at the second micro-controller, it will rotate the motor 0.5 in the clockwise direction.  

4- Closing the door: 
At first micro-controller, a message will be shown: "[1]Close Lock", if the user entered 1 a message will be sent to the other micro-controller to close the door, the second micro-controller will receive the message and rotate motor will rotate 0.5 in the anticlockwise direction.  

The LCD at the first micro controller will reflect any action / State happens at the system. for example if the door is opening it should show : Lock is opened
