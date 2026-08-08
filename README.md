
CAN-Based Vehicle Safety and Monitoring System using LPC2129 ARM7 and CAN protocol. The system monitors engine temperature, controls vehicle indicators, and detects reverse obstacles through communication between multiple CAN nodes, improving vehicle safety and real-time monitoring.

## Table of Contents
1. Project in One Minute.
2. Why Did I Develop This Project?
3. Basic Working.
4. Node 1 – Main Node.
5. Node 2 – Indicator Node.
6. Node 3 – Reverse Alert Node.
7. Complete Project Flow.
8. How CAN Communication Is Used.
9. Hardware Used.
10. Key Features.
11. Future Improvements.
12. Project Author.


## 1. Project in One Minute

This project is a CAN-based vehicle safety system developed using the LPC2129 ARM7 microcontroller.
The main purpose is to monitor important vehicle conditions and improve safety using three CAN nodes:
1. Main Node – Monitors temperature, controls vehicle mode and indicators, and receives obstacle information.
2. Indicator Node – Controls Left and Right indicators.
3. Reverse  Node – Detects obstacles while reversing.
All three nodes communicate through a CAN Bus.



## 2.Why Did I Develop This Project?

In a vehicle, different systems need to communicate with each other in real time.
For example:
* The temperature needs to be monitored.
* Indicators need to be controlled.
* Obstacles behind the vehicle need to be detected during reverse.
Instead of connecting everything directly to one controller, I used multiple LPC2129 nodes connected through CAN communication.
This helped me understand how CAN protocol is used in automotive embedded systems.


## 3. Basic Working
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/a2298814-fb16-45e5-a1a0-967562c5dd1d" />






# 4. Node 1 – Main Node
The Main Node is the central controlling node.

It performs the following operations:
* Reads engine temperature from DS18B20.
* Displays temperature on the 20x4 LCD.
* Reads Left and Right indicator switches.
* Detects Forward/Reverse mode.
* Sends indicator commands through CAN.
* Receives obstacle information from the Reverse Alert Node.
* Activates the warning LED when an obstacle is detected.

### Main Node Flow

<img width="1373" height="1145" alt="image" src="https://github.com/user-attachments/assets/ac34fb51-e2e1-410e-a80b-42db549b014b" />






# 5. Node 2 – Indicator Node
The Indicator Node receives commands from the Main Node through CAN.
<img width="1166" height="1349" alt="image" src="https://github.com/user-attachments/assets/9cbc3828-8880-423b-97e6-f7fa5ba1d0bf" />




# 6. Node 3 – Reverse Alert Node

This node detects obstacles behind the vehicle using the  ultrasonic sensor.
The measured distance is compared with 20 cm.

<img width="1156" height="1361" alt="image" src="https://github.com/user-attachments/assets/63e39fd6-9090-4ca3-b594-4905c4ca4fef" />



### Conditions

* Distance < 20 cm → ALERT
* Distance ≥ 20 cm → SAFE
* No object detected → 999 cm
The Main Node receives this information and displays the status / activates the warning LED.

# 7.Complete Project Flow


![Uploading image.png…]()



# 8.  How CAN Communication Is Used

CAN is used as the communication medium between the three LPC2129 nodes.
The CAN communication uses the MCP2551 CAN transceiver.
The CAN bus uses:
* CANH
* CANL
* 120 Ω termination resistors
The project README specifies that the three LPC2129 nodes communicate over this CAN Bus and that MCP2551 is used as the CAN transceiver

# 9.  Hardware Used

 Component       Purpose                          
 
 LPC2129 × 3  CAN nodes / Controllers          
 DS18B20      Temperature monitoring           
 HC-SR05      Reverse obstacle detection       
 20×4 LCD     Display                          
 LEDs         Indicator control                                 
 Switches     Indicator and vehicle mode input 
 MCP2551      CAN transceiver                  
 CANH/CANL   CAN communication                

# 10. Key Features

* Real-time engine temperature monitoring.
* Reverse obstacle detection.
* Left and Right indicator control.
* CAN communication between three LPC2129 nodes.
* LCD-based system status display.
* Warning indication when an obstacle is within 20 cm.
* Modular multi-node automotive system.

# 11. Future Improvements

Possible future improvements include:

* GPS-based vehicle tracking
* GSM emergency alerts
* IoT-based remote monitoring
* Vehicle speed and battery monitoring
* CAN FD
* Rear-view camera integration
* Mobile application for monitoring


## 12.Project Author
Bhavani Taddi
Embedded Systems | Embedded C | ARM7 | LPC2129 | CAN
