# Smart-Desk-Lamp-System
Graduation design works, report documents and objects, and etc.

With the popularity and rapid development of the Internet of Things, more and more household products have chosen functions linked to smart prices. However, traditional table lamps have shortcomings such as few gears, lack of functions, and waste of resources. Therefore, we propose a smart desk lamp system based on the concept of the Internet of Things. This system aims to establish a multi-functional and low-consumption smart lamp system based on smart phones. Users can use the temperature sensor, humidity sensor and photoresistor sensor to control the switch and brightness of the light through the application program. In addition, automatic reminder, automatic adjustment, temperature and humidity display will also be realized.
In response to the problems of traditional desk lamp with single function, no automatic dimming and wasted energy, we plan to design an intelligent desk lamp system to complete real-time IOT control and monitoring functions. The system aims to provide people of different ages and needs with the ability to control the on/off and brightness of the desk lamp through a mobile application. In addition, the user will complete the setting of the lamp usage time and the monitoring of temperature and humidity according to this application.
Our project has only one system. The application in the mobile phone is combined with the Arduino UNO development board by integrating the Bluetooth 4.0 communication module. Arduino is an open source electronic prototyping platform that is convenient, flexible and easy to use. It consists of two parts: the hardware part is the Arduino circuit board used for circuit connection; the other part is the Arduino IDE, which is an application program used to provide a program development environment, which integrates code writing functions, analysis functions, and compilation functions. [1] Software. It can perceive the environment through a variety of sensors, and it can also feedback and influence the environment by controlling lights, motors and other devices. Based on this feature, we will use a temperature sensor and a humidity sensor to add the function of displaying temperature and humidity to the desk lamp. After the user uses the built-in Bluetooth to match the Bluetooth of the mobile phone, the user will complete the access to functions such as temperature and humidity through the application. And realize real-time brightness adjustment and alarm setting according to IDE code.
With the development of information technology and the continuous improvement of people's living standards and quality, it is difficult for traditional lighting to meet the needs of home lighting for safety, convenience, comfort, environmental protection and energy saving. Traditional bright lights are generally only can achieve open and close operation. Some lights have a wireless switch and adjust brightness function of lighting lamp, but they need for additional equipped with wireless remote control. Therefore, multiple light requires multiple remote controller, which not only increases cost but also are not convenient to use. Furthermore, manual switch also has certain security issues affecting people's life quality. Therefore, some enterprises have already made some intelligent lights. 
The existing system is mainly composed of MCU control module such as Arduino development board, lighting module, Bluetooth communication module and mobile APP. After the system is initialized, users first open the APP terminal of the mobile phone to connect and pair with the system, and then send operation instructions to operate the lights remotely. The operation instruction data is first transmitted from the APP of the mobile phone to the Bluetooth communication module, and then transmitted to the MCU control module. The MCU control module will control the corresponding lights after receiving the operation instructions. In order to increase the convenience and redundancy, these systems also adopts the way to control the lights manually. The following diagram shows current software control flows.
The system will be mainly divided into four subsystems. The first part will mainly include the explicit control of the desk lamp. This is also the "switch" of the application. We will control and operate the desk lamp switch. When the desk lamp is turned on, it will enter the next sub-part, the brightness adjustment system. In this system, we can set the brightness of the desk lamp, and can also set the automatic adjustment mode of the brightness. The main function of the next subsystem is parallel to and separate from the second part. This is a room temperature and humidity display system, which mainly uses sensors to obtain temperature and humidity and display them on apps and desk lamps. The last is the time reminder system. Mainly rely on the application on the smart phone to set the lamp usage time and remind the function to complete the user's energy-saving goal.
This software contains a number of subsystems:
1. Super administrator subsystem. In this system, administrators can complete all the operations of the system, such as: evaluation system formulation, modify database display information, and add/delete file content.

2. Sensing and display subsystem. This system will mainly accept data from sensors and display the brightness, temperature and humidity of the lamp.

3. Information file subsystem. The subsystem contains all the text files, including the attributes of various labels, and can make quick changes to the information files.

4. Desk lamp adjustment and setting system. Users can rely on this system to access the intelligent desk lamp and enter the setting link with permission to complete the setting of intelligent control.
  In our smart desk lamp system, the user touches the on/off button in the user interface and the touch signal turns on the desk lamp through the sensor control system and Bluetooth function. The user can complete the brightness control of the lamp by using the application designed by the Arduino UNO development board hardware. In addition, thanks to the addition of temperature and humidity sensors, the sensors can acquire the external space temperature and humidity and upload them to a data processing service for display in the application. Finally, using the IDE design target program, users can set the usage time and reminder time as well as the delay off for the switch in the application. This can facilitate the sleeping user to turn off the desk lamp automatically after sleeping.
  In this section, we will discuss the persistent data management for our project. For the current time display, we will direct get the time through time API from Arduino library because this time is almost impossible to be inaccurate when our produce is online, because it directly comes from the global atomic clock. We also provide the manual time adjusting function for setting current in case our product is running offline and the time may not keep accurately. Another important function for our product is the alarm. The users can set multiple alarm and decide whether they will repeat or turn on. In addition, the content of alarm also will be displayed. Therefore, in order to store and retrieve information, we design a table in database to manage them. Table 1 shows an example of the alarm table in database. 
  For setting the delay time of light, we no longer to create a table to store this information because normally only one delay time can be set. So, in order to achieve this function, we directly store this time in a variable of programming like what we did in storing current time. For temperature and humidity display, we can create two tables in order to show them in history. The tables 2 and table 3 shows examples of these two tables.
  As we did for storing current time and delay time of turning off the light, we also need one variable to store the value of brightness of the light. This variable is also shored directly in the program and we will not create a table in database to store it because normally this data only can be set once every time. 
  Another important table that we have to store in database is the account table. For security consideration, each password corresponding to an account must be encrypted by hash function. Furthermore, an account may link to multiple lights. Therefore, we design following table as example to show how they are stored in database. 
  Since the product will be using both online and offline, we have to using hash function to secure all sensitive data like account and password. This method effectively prevents users from decompiling the file for malicious purposes. To achieve reliable protection, when users use the app, the context will not record their browsing history or related privacy.
  Adding global control buttons to the cell phone application interface to control the software is critical in this framework. To begin, add a script to the system, which can then be called by global control buttons to control the software's activity, server, initialization, and shutdown.
  Second, the program has introduced a global control button for the language selection feature to make it easier to remember the user's choice of language. And if the scene is changed after the user selects the language, the device will remember the user's initial option.  
  Finally, if the code becomes stuck or crashes for some reason, the system context will directly call the global control script, which will then run the shutdown feature, allowing users to shut down the program.
  We will use the Arduino UNO development board connected to the Bluetooth module to form communication with the mobile application. In addition, the development board has the ability to connect sensing and read it. Arduino can sense the environment through a variety of sensors and can also give feedback and influence the environment by controlling lights, motors and other devices. We will base on this to complete the reading of the temperature sensor and humidity sensor.
  Arduino ide is a professional Arduino development tool, mainly used for Arduino program writing and development, with open source circuit diagram design, support ISP online burning. It is compatible with C language and has become our main development language. We need to download specific IDE function libraries to assist us in developing this IoT application.

##### Version 1.1 Description

Add Login page to access the smart light.

Improve the UI design of the App.

Updated project file to Github

