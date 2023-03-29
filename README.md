# PID Controller Design in NI LabVIEW for Schneider Electric Modicon M238 PLC to Control AC Servo Motor

## Abstract
In this project, it is aimed to design a PID controller in NI LabVIEW software to control AC servo motor driven by Lexium 32 that connected to Schneider TM238LFDC24DT PLC. 
To establish communication between NI LabVIEW and Schneider TM238LFDC24DT PLC, Open Platform Communications (OPC) server is going to be used. OPC is a series of standards 
and specifications for industrial telecommunication. It is based on Object Linking and Embedding (OLE) for process control.

### What is Server?
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
### What is OPC?
OPC is based on Microsoft's Object Linking and Embedding (OLE) / Component Object Model (COM) standard. OLE / COM is an object-based technology that targets Microsoft's 
integration between different applications. OPC is an OLE-based communication standard and also provides a fast and reliable connection between different automation levels. 
Transferring data from one brand to another or communicating devices each other has often been an obstacle for automation employee. The manufacturers of the device / system use their 
own protocols for industrial communication; both producers and users are affected negatively. [3] Since each controller manufacturer's communication protocol is different, driver of each 
controller brand must be designed for each SCADA software. This situation creates many difficulties in practice. Such solutions based on product-specific driver development have 
created many problems. The concept of OLE for Process Control OPC has emerged as a result of the meeting of industrial automation system manufacturers, industrial communication systems manufacturers 
and automation firms to remove the obstacles in this area. OPC has created a clear line between the standard interface hardware manufacturers and 
software providers. Hardware manufacturers can communicate with software that has to all OPC client features on the market with a single driver. Thus, this saves resources and time.
OPC has become a set of standards with time. These standards can be listed as follows: OPC Data Access (OPC DA), OPC Historical Data Access (OPC HDA), OPC Alarm & Events 
(OPC A&E), OPC Extensible Markup Language (OPC XML) and OPC Unified Architecture (OPC UA). OPC DA is the standard for real-time streaming of data. OPC HDA is the standard that regulates the transfer of historical data records.
OPC A&E is the standard that regulates the alarm and the related standard. OPC XML is the standard that regulates OPC-compatible interface development.
OPC UA is the last published standard and is the standard for making OPC technology safer.

**OPC Client - OPC Server Communications - (OPC DA Server, OPC HDA Server, OPC A&E Server)**
Classic OPC Servers utilize the Microsoft Windows’ COM/DCOM infrastructure as a means of exchanging data. This means these OPC Servers must run on the Microsoft Windows 
operating system. An OPC Server can support communications with multiple OPC Clients simultaneously.

**OPC Server - Data Translation/Mapping**
A key OPC server function is to translating data native to the data source into an OPC format that’s compatible with one or more OPC Specifications mentioned above (example: OPC 
DA for real-time data). OPC Foundation specifications only define what the OPC portion of OPC Server communications so the efficiency and quality of the Native-to-OPC and OPC-toNative translations depends entirely on each vendor’s OPC Server implementation.

**OPC Server-Data Source Communications**
OPC Servers communicate natively with data-sources examples of which are: devices, controllers, and applications. OPC Foundation specifications do not specify how OPC Servers 
connect to and communicate with data sources because of the wide variety of data sources available.

### Lexium 32 AC Servo Motor Drive:
The Lexium 32 product family consists of various servo drive models that cover different application areas. Together with Lexium BMH servo motors or Lexium BSH servo motors as 
well as a comprehensive portfolio of options and accessories, the drives are ideally suited to implement compact, high-performance drive solutions for a wide range of power 
requirements. The reference values for numerous operating modes are supplied via communication interface for CANopen and CANmotion.

<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/lexium32.JPG" />
</p> 
<p align="center">
Fig. 1: Lexium 32 AC Servo Motor Drive [4]
</p>

### AC Servo Motor:
Servo Motor are also called control motors. They are used in feedback control systems as output actuators and does not use for continuous energy conversion. The principle of the 
servo motor is similar to that of theother electromagnetic motor, but the construction and the operation are different. Their power rating varies from a fraction of a watt to a few hundred 
watts. The AC Servo Motors are divided into two types 2 and 3 Phase AC servomotor. Most of the AC servomotor are of the two-phase squirrel cage induction motor type. They are used for 
low power applications. The three phase squirrel cage induction motor is now utilised for the applications where high power system is required.
<p align="center">
  <img src="https://github.com/kagankalayli/PID-Controller-Design-in-LabVIEW-for-Schneider-PLC-to-Control-AC-Servo-Motor/blob/main/automationlabviewopc/acservomotor.JPG" />
</p> 
<p align="center">
Fig. 2: SE BMH0701P01A2A AC Servo Motor [5]
</p>

### PID Controller:
A proportional–integral–derivative controller (PID) is a control loop mechanism employing 
feedback that is widely used in industrial control systems and a variety of other applications 
requiring continuously modulated control. A PID controller continuously calculates an error 
value e(t) as the difference between a desired setpoint (SP) and a measured process variable 
(PV) and applies a correction based on proportional, integral, and derivative terms (denoted P, 
I, and D respectively), hence the name.
The first theoretical analysis and practical application of PID was in the field of automatic 
steering systems for ships, developed from the early 1920s. It was then used for automatic 
process control in the manufacturing industry, where it was widely implemented in at first 
pneumatic and then electronic controllers. Today the PID concept is used universally in 
applications requiring accurate and optimized automatic control.
The distinguishing feature of the PID controller is the ability to use the three control terms of 
proportional, integral and derivative influence on the controller output to apply accurate and 
optimal control. The block diagram belove shows the principles of how these terms are 
generated and applied. It shows a PID controller, which continuously calculates an error value 
e(t) as the difference between a desired setpoint SP=r(t) and a measured process variable 
PV = y(t):e(t) = r(t) - y(t)} and applies a correction based on proportional, integral, and 
derivative terms. The controller attempts to minimize the error over time by adjustment of a 
control variable u(t).
