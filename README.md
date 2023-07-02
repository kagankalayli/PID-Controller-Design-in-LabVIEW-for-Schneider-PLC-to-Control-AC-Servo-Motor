# PID Controller Design in NI LabVIEW for Schneider Electric Modicon M238 PLC to Control AC Servo Motor

## Abstract
In this project, it is aimed to design a PID controller in NI LabVIEW software to control AC servo motor driven by Lexium 32 that connected to Schneider TM238LFDC24DT PLC. 
To establish communication between NI LabVIEW and Schneider TM238LFDC24DT PLC, Open Platform Communications (OPC) server has been used. OPC is a series of standards 
and specifications for industrial telecommunication. It is based on Object Linking and Embedding (OLE) for process control.

## Server
Server is hardware or software that distributes a program or information on any network to different users. Servers are very important to ensure that data can be transmitted and stored securely. 
In computing, a server is a piece of computer hardware or software (computer program) that provides functionality for other programs or devices, called "clients". This architecture is called the client–server model. 
Servers can provide various functionalities, often called "services", such as sharing data or resources among multiple clients, or performing 
computation for a client. A single server can serve multiple clients, and a single client can use multiple servers. A client process may run on the same device or may connect over a network 
to a server on a different device. [1] Typical servers are database servers, file servers, mail servers, print servers, web servers, game servers, and application servers. [2]
Client–server systems are usually most frequently implemented by (and often identified with) the request–response model: a client sends a request to the server, which performs some 
action and sends a response back to the client, typically with a result or acknowledgment. Designating a computer as "server-class hardware" implies that it is specialized for running 
servers on it. This often implies that it is more powerful and reliable than standard personal computers, but alternatively, large computing clusters may be composed of many relatively 
simple, replaceable server components. A server is considered a hardware component at firstly. However, a server does not consist 
solely of a physical device. These devices require special software to run as a server. These softwares enable the server to present the data that it possesses in the most appropriate manner 
for its intended use. The most important feature of the server is that it can provide the data stream with safe, 
uninterrupted and stable performance. Therefore, each server has advanced hardware features and often powered by additional enhancements. 
The main types of servers with different usage areas are home server, network server, application server, ftp server, database server, game server, communication server, dns server, 
virtual server etc.
## OPC
OPC is based on Microsoft's Object Linking and Embedding (OLE) / Component Object Model (COM) standard. OLE / COM is an object-based technology that targets Microsoft's 
integration between different applications. OPC is an OLE-based communication standard and also provides a fast and reliable connection between different automation levels. 
Transferring data from one brand to another or communicating devices each other has often been an obstacle for automation employee. The manufacturers of the device / system use their 
own protocols for industrial communication; both producers and users are affected negatively. [3] Since each controller manufacturer's communication protocol is different, driver of each 
controller brand must be designed for each SCADA software. This situation creates many difficulties in practice. Such solutions based on product-specific driver development have 
created many problems. The concept of OLE for Process Control OPC has emerged as a result of the meeting of industrial automation system manufacturers, industrial communication systems manufacturers 
and automation firms to remove the obstacles in this area. OPC has created a clear line between the standard interface hardware manufacturers and 
software providers. Hardware manufacturers can communicate with software that has to all OPC client features on the market with a single driver. Thus, this saves resources and time. OPC UA is the last published standard and is the standard for making OPC technology safer.

## Lexium 32 AC Servo Motor Drive
The Lexium 32 product family consists of various servo drive models that cover different application areas. Together with Lexium BMH servo motors or Lexium BSH servo motors, the drives are ideally suited to implement compact, high-performance drive solutions for a wide range of power requirements. The reference values for numerous operating modes are supplied via communication interface for CANopen and CANmotion.

<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/lexium32.JPG" />
</p> 
<p align="center">
Fig. 1: Lexium 32 AC Servo Motor Drive [4]
</p>

## AC Servo Motor
Servo Motor are also called control motors. They are used in feedback control systems as output actuators and does not use for continuous energy conversion. The principle of the servo motor is similar to that of theother electromagnetic motor, but the construction and the operation are different. Their power rating varies from a fraction of a watt to a few hundred watts. The AC Servo Motors are divided into two types, 2 and 3 Phase AC servomotor. Most of the AC servo motor are of the two phase squirrel cage induction motor type. They are used for low power applications. The three phase squirrel cage induction motor is now utilised for the applications where high power system is required.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/acservomotor.JPG" />
</p> 
<p align="center">
Fig. 2: SE BMH0701P01A2A AC Servo Motor [5]
</p>

## PID Controller
A proportional–integral–derivative controller (PID) is a control loop mechanism employing feedback that is widely used in industrial control systems and a variety of other applications requiring continuously modulated control. A PID controller continuously calculates an error value e(t) as the difference between a desired setpoint (SP) and a measured process variable (PV) and applies a correction based on proportional, integral, and derivative terms (denoted P, I, and D respectively), hence the name. The first theoretical analysis and practical application of PID was in the field of automatic steering systems for ships, developed from the early 1920s. It was then used for automatic process control in the manufacturing industry, where it was widely implemented in at first pneumatic and then electronic controllers. Today the PID concept is used universally in applications requiring accurate and optimized automatic control.The distinguishing feature of the PID controller is the ability to use the three control terms of proportional, integral and derivative influence on the controller output to apply accurate and optimal control. The block diagram belove shows the principles of how these terms are generated and applied. It shows a PID controller, which continuously calculates an error value 
e(t) as the difference between a desired setpoint SP=r(t) and a measured process variable PV. Applies a correction based on proportional, integral, and derivative terms. The controller attempts to minimize the error over time by adjustment of a control variable u(t).
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/pid.png" />
</p> 
<p align="center">
Fig. 3: A Block Diagram of a PID Controller in a Feedback Loop [6]
</p>

## NI LabVIEW
Laboratory Virtual Instrument Engineering Workbench (LabVIEW) is a system-design platform and development environment for a visual programming language from National 
Instruments.

### PID Controller Design in LabVIEW
1. The Control & Simulation Loop was created. The Control & Simulation Loop executes the simulation diagram until the Control & Simulation Loop reaches the 
simulation final time.
2. Necessary circuit components for PID Controller were placed in The Control & Simulation Loop.
3. Connections in the PID Controller were made according to PID Control Function.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/labviewpid.PNG" />
</p> 
<p align="center">
Fig. 4: PID Controller Designed in LabVIEW
</p>

## Transfer Function of AC Servo Motor
### Transfer Function Formulas for AC Servo Motor
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/transfer.PNG" />
</p> 
<p align="center">
Fig. 5: Formulas for AC Servo Motor
</p>

***In order to calculate the transfer function of the ac servo motor for the PID Controller, the constants of the motor are needed.***

The specifications and the calculated transfer function of the SE BMH0701P01A2A Model AC Servo Motor are below;

<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/acmotorspecs.PNG" />
</p> 
<p align="center">
Fig. 6: Calculated Transfer Function
</p>

### Transfer Function Configuration in LabVIEW
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/transferfuncmotor.PNG" />
</p> 
<p align="center">
Fig. 7: Transfer Function of the PID Controller
</p>

### PID Controller Output
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/pidoutput.PNG" />
</p> 
<p align="center">
Fig. 8: PID Control Simulation
</p>

### LabVIEW OPC Configuration
1. Created a new channel on NI OPC Server.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/opcchannel.PNG" />
</p> 
<p align="center">
Fig. 9: Channel Name Configuration
</p>

2. Device driver selected as Telemecanique Uni-Telway Slave.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/telemecanique.PNG" />
</p> 
<p align="center">
Fig. 10: Device Driver Configuration
</p>

3. After necessary settings were made for the configuration, tag names and addresses for shared variables in LabVIEW and SoMachine are created. 
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/tag.PNG" />
</p> 
<p align="center">
Fig. 11: Tag Properties
</p>

## SoMachine Logic Buider
SoMachine is the OEM solution software for developing, configuring and commissioning the entire machine in a single software environment including logic,
motion control, HMI and related network automation functions.
### SoMachine Configuration
1. Created new project on SoMachine software with TM238LFDC24DT logic controller.
2. Added a new POU. “Ladder Diagram (LD) is selected.
3. On devices tree tab, right clicked to CAN and selected Add Device.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/candevice.PNG" />
</p> 
<p align="center">
Fig. 12: CAN Device Addition.
</p>

4. "CANopen Optimized" was selected and the device was added. Driver model name is LXM32MU90M2 so “Lexium 32M”  was added.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/canconfig.PNG" />
</p> 
<p align="center">
Fig. 13: CAN Configurations
</p>

5. Established connection between CAN module and Lexium 32 module.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/canconnection.PNG" />
</p> 
<p align="center">
Fig. 14: CAN Connection
</p>

6. Built the ladder diagram for the PID control of AC Servo Motor.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/somachine.PNG" />
</p> 
<p align="center">
Fig. 15: SoMachine Ladder Logic
</p>

**System setup is as below;**
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/panotanim.jpg" />
</p> 
<p align="center">
Fig. 16: System Setup
</p>

## References
[1] Windows Server Administration Fundamentals. Microsoft Official Academic Course. 
Hoboken, NJ: John Wiley & Sons. 2011. pp. 2–3. ISBN 978-0-470-90182-3.

[2] Comer, Douglas E.; Stevens, David L (1993). Vol III: Client-Server Programming and 
Applications. Internetworking with TCP/IP. West Lafayette, IN: Prentice Hall. pp. 11d. ISBN 
978-0-13-474222-9.

[3] OPC Foundation website. Retrieved October 7, 2021.

https://opcfoundation.org/about/what-is-opc/

[4] Lexium32 Servo Drive Image

https://www.se.com/ww/en/product/LXM32MU90M2/motion-servo-drive-lexium-32-single-phase-supply-voltage-115-230-v-0-3-0-5-kw/

[5] SE BMH0701P01A2A AC Servo Motor Image

https://www.se.com/ww/en/product/BMH0701P01A2A/servo-motor-bmh-1-2-nm-8000-rpm-untapped-shaft-without-brake-ip54/

[6] Block Diagram Of A PID Controller In A Feedback Loop Image

https://en.wikipedia.org/wiki/PID_controller#/media/File:PID_en.svg
