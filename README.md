# SOLEDRYhaha

##### 🌟 Introducing SoleDry: A Smart Shoe Drying Box! 🌟
Thrilled to share my latest project at The University of Pennsylvania, where my team designed and implemented SoleDry for the final project for the course ESE 5190: Smart Devices taught by professor Nicholas McGill-Gardner, an automatic shoe-drying system powered by the ATmega328PB microcontroller. This project was part of my journey in embedded systems engineering from August to December 2024, and it was an incredible learning experience!
##### 💡 What is SoleDry?
SoleDry is a smart shoe dryer system that ensures your footwear is dried efficiently without compromising quality. Specifically designed for people living in regions with heavy monsoons, for ex: India, Bangladesh, Korea, China, Japan, etc, SoleDry offers a reliable and easy way to take care of your shoes in a way that has never been done before. From the working class to the school-going children, SoleDry is the solution for all the problems your shoe faces during monsoons, be it the wetness that doesn’t dry in the humid atmosphere naturally, or be it the smell that comes with wet shoes, or be it the reduction of the lifespan of the shoe. Sole Dry is the SOLE solution to all your wet shoe problems. 
* SoleDry offers the user to use 3 modes: 
1. Automatic Mode- in this mode the user just has to put the shoe inside the shoe drying compartment. The system is programmed to automatically measure the weight of the shoe when it's wet and it turns on the drying process while constantly measuring the weight of the shoe, comparing it with the previously registered value( the value gets registered every 30 minutes in the Atmega328PB), It turns off the drying mechanism when the shoe is dry completely when the last two registered values are the same. 
	In addition, the automatic mode also considers overheating of the shoe and preserves the quality of the shoe to its optimum, by turning off the drying system when the temperature inside the shoe compartment reaches close to 40°C. 
2. Manual Mode- The manual mode allows the user to set a custom temperature and time limit for your shoe to dry. 
3. New Profile mode- In the new profile mode you get to set your shoe’s dry weight, and let the machine know when to stop the drying process. For example, you can set your new shoe with your name like “Jack’s shoes”, this will register the dry weight of jack’s shoes. So the next time Jack’s shoes are placed in the drying compartment, and the profile “Jack’s shoes” is selected, the system will begin the drying process and will only get turned off when the weight of the shoes reaches the dry weight of his shoes, or when the shoe compartment gets overheated. 

* 🔧 Technical Highlights:
Baremetal C Programming: Developed the firmware for the system on an ATmega328PB microcontroller.
Sensor Integration:
HDC3020 (Temperature & Humidity Sensor): Monitors and displays real-time conditions, halting the drying process when the temperature exceeds 40°C to protect shoe materials.
NAU7802 (Load Sensor ADC): Tracks shoe weight every second and registers changes every 30 minutes to determine drying completion.
I2C Protocol Communication:  Enabled seamless interaction between the microcontroller and sensors.
Power Management: Successfully integrated a 120V AC heater, two 12V fans, sensors, and AC-DC relays into a single efficient circuit.
Automated Shutoff: The system intelligently halts operation when it detects consistent weight measurements, signaling that the shoes are dry.


# Team Details
    
    * Team Name: ohm-sweet-ohm
    * Team Members: Venkatesh, Komalika & Jyotiraditya 
    * Github Repository URL: https://github.com/upenn-embedded/final-project-ohm-sweet-ohm
    * Github Pages Website URL: https://komalika18.github.io/SOLEDRY.github.io/

## Final Project Proposal

### 1. Abstract

In a few sentences, describe your final project. This abstract will be used as the description in the evaluation survey forms.

SoleDry
SoleDry is a sustainable solution designed to dry wet shoes, prevent bad odors, and extend shoe lifespan, especially during the monsoon season. The system uses humidity and temperature control to efficiently dry shoes overnight without causing damage. A display provides real-time updates on weight, temperature, and humidity, allowing users to monitor the drying process effectively. This prototype demonstrates the feasibility of maintaining shoe freshness and durability through automated environmental control.

### 2. Motivation

What is the problem that you are trying to solve? Why is this project interesting? What is the intended purpose?

**Problem:** Wet shoes, especially in countries with long rainy seasons, lead to bad odors, bacterial growth, and a shorter shoe lifespan. Traditional drying methods are often inefficient and can damage shoes due to improper temperature control or excessive moisture retention, making it difficult to maintain shoe quality and hygiene.

**Interesting Because:** SoleDry provides an innovative, automated solution to a common problem by using real-time humidity and temperature control to efficiently dry shoes without compromising their quality. It's particularly useful in humid climates, offering a sustainable way to extend shoe lifespan and improve hygiene.

**Intended Purpose:** The goal is to create an efficient, user-friendly system that dries shoes overnight, prevents odor, and maintains the structural integrity of shoes. It ensures shoes remain fresh and usable, making it a convenient and sustainable tool for everyday life, especially during wet seasons.


### 3. Goals

These are to help guide and direct your progress.

1. Maintaining Air Flow: Ensure proper air circulation through vents, exhausts, and fans to promote efficient and uniform drying of shoes.
2. Humidity Control: Use sensors and controlled air flow to regulate and maintain optimal humidity levels, preventing excess moisture or drying too fast.
3. Temperature Control: Incorporate a reliable heating system to control the temperature inside the box, ensuring shoes dry efficiently without overheating.
4. Weight Monitoring: Utilize a weight sensor to track the reduction in shoe weight, enabling precise monitoring of moisture loss during drying.
5. LED Display: Show real-time values for humidity, temperature, and weight, along with a calculated percentage indicating how much the shoes have dried based on initial and dry weights.
6. Buzzer Notification: Include an alert system (buzzer) to notify the user when the desired dry weight is achieved, signaling that the shoes are fully dry.

### 4. System Block Diagram

![Block Diagram](image.png)

### 5. Design Sketches

![Design Sketches](image-1.png)

### 6. Software Requirements Specification (SRS)


#### 6.1 Overview

 SoleDry, is a system designed to automate the process of drying wet shoes. The software controls various input devices such as humidity, temperature, and weight sensors, as well as output devices like relays, fans, and heaters. The system processes sensor data, makes decisions based on pre-set thresholds, and displays real-time data to the user on an integrated display and through IoT (Blynk) connectivity for remote monitoring and control.

#### 6.2 Users

* Primary Users: Individuals looking to dry their shoes in a controlled environment, especially in regions with long rainy seasons or humid climates.
* System Administrators: Users responsible for setting up and maintaining the hardware and software, adjusting thresholds and monitoring performance.
* Remote Users: Individuals who want to monitor and control the drying process through the Blynk IoT platform via their mobile devices.

#### 6.3 Definitions, Abbreviations

* ATmega328pb: The microcontroller used to control output devices and read sensor data.
* ESP32: A microcontroller with built-in Wi-Fi for IoT capabilities, used for remote monitoring and control.
* Blynk IoT: A platform for remote device monitoring and control through mobile applications.
* SRS: Software Requirements Specification.
* PWM: Pulse Width Modulation used to control fan speed.

#### 6.4 Functionality

SRS 01 – Humidity and temperature sensors will continuously monitor the environment, sending data to the ATmega328pb every second and send heater temperature every second as well and its getting compared every 30 seconds.

SRS 02 – The weight sensor will measure and update the shoe weight with a precision of 20 grams, and values will be logged every 30 seconds.

SRS 03 – Relay switches will control the heater and fans based on pre-set temperature thresholds at 30°C , observed every 30 second.

SRS 04 – The display will update every second to show the current temperature, humidity, and weight, as well as the percentage of drying progress.

SRS 05 – The user can adjust the mode (Automatic, Manual, and Profile mode) via the buttons, with input processing every 30 seconds.
(However for the scope for the final demonstration we are focussing of the automatic mode only.)

### 7. Hardware Requirements Specification (HRS)

#### 7.1 Overview

System detects the weight of wet shoes placed inside a box and turns on the heating mechanism based on the weight, temperature, and humidity inside the box. The system uses a heating coil for drying, with fans circulating hot, dry air. Sensors continuously monitor the coil’s temperature to prevent overheating. A display shows the weight of the wet shoes and calculates the estimated time to dry the shoes completely, providing real-time feedback. 

#### 7.2 Definitions, Abbreviations

* ATmega328pb: A low-power microcontroller used to control relays, heater, and fans based on sensor inputs.
* ESP32: A Wi-Fi-enabled microcontroller responsible for wireless communication and remote control via Blynk IoT.
* LCD: Liquid Crystal Display used to show real-time stats (humidity, temperature, weight) to the user.
* Relay: An electrical switch used to control high-power devices like the heater and fans

#### 7.3 Functionality

* HRS 01 – The project shall be based on the ATmega328pb microcontroller to control relays, heating coil, fans, and process sensor data.
* HRS 02 – A sensor shall be used to detect the weight of the wet shoe placed in the box. The sensor shall measure weight with an accuracy of 20 grams and send data to the microcontroller.
* HRS 03 – A heater shall be used as the drying element. The coil’s temperature shall be continuously monitored by a temperature sensor to avoid overheating. The system shall shut down the coil if the temperature exceeds a preset limit that 30°C. 
* HRS 04 – Two 5V fans shall be used to ensure the circulation of hot air inside the box. The fans shall operate in conjunction with the heating coil to provide an even airflow.
* HRS 05 – An LCD display shall be used to show the real-time weight of the shoe and the estimated drying time. The drying time will be calculated based on the weight and environmental conditions (temperature and humidity).
* HRS 06 – A temperature and humidity sensor shall be used to monitor the humidity and temperature inside the box, ensuring optimal drying conditions are maintained.
* HRS 07 – Relays shall control the power supply to the heating coil and fans, turning them on or off based on the shoe weight, temperature, and humidity readings.
* HRS 08 – A 5V power supply block shall power the microcontrollers and input devices, while a 12V power supply shall be used for the relays and output devices (fans), AC supply for the Heater. 



### 8. Components

What major components do you need and why? Try to be as specific as possible. Your Hardware & Software Requirements Specifications should inform your component choices. Add links to components.

**ATatemga328pb**
https://www.digikey.com/en/products/detail/microchip-technology/ATMEGA328PB-XMINI/5338500

Serves as the main controller for the smart shoe dryer, managing core device functions like sensor readings, relay control for the heating element and fan, and display output.

**ESP32**
https://www.adafruit.com/product/5000

Provides Wi-Fi connectivity and enables remote control and monitoring through the Blynk IoT platform, allowing users to check and manage the dryer remotely.

**1.8" LCD Display**
https://www.adafruit.com/product/358

Used for user interface and interaction. Displays current humidity, temperature and allows for manaual control.

**Heater**
https://www.amazon.com/Amazon-Basics-Portable-Protection-Lightweight/dp/B074MXC3PN?source=ps-sl-shoppingads-lpcontext&ref_=fplfs&smid=ATVPDKIKX0DER&th=1

The main source of heat for the entire system, provides heat and warms up the incoming air.

**Fans**
https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/CFM-A225C-015-287-20/14557939

There are 2 fans, one for inlet and other as an exhaust. Both used strategically to control the inside humidity and temperature i.e improve ventilation.

**Load sensor**
https://www.adafruit.com/product/4541

Detects whether the shoes are kept in the rack or not and also measures the weight that is then considered as to how long will it take for the footwear to dry completely.

**24-bit ADC for Load Cells / Strain Gauges**

https://www.adafruit.com/product/5974

It provides a 24-bit differential ADC, which means it can detect very small changes in resistance, making it perfect for precise measurements

**Temperature and humidity sensor**

https://www.adafruit.com/product/5989

Detects the inside as well as outside temperature and humidity and helps determine how hot the heater must get and how fast the fans must spin to better dry the footwear quickly.

**Joystick and button**
https://www.adafruit.com/product/444
https://www.adafruit.com/product/1505

Used as means of input devices for the display.

**STEMMA QT / Qwiic JST SH 4-Pin Cable**

https://www.adafruit.com/product/5385

It is a versatile cable used primarily for connecting sensors and modules in a simple and efficient manner.It supports I2C communication, which is a common protocol for connecting multiple devices using just two wires (SDA for data and SCL for clock)

### 9. Final Demo

What do you expect to achieve by the final demonstration or after milestone 1?

* By Milestone 1, we expect to:
  
1. Have a finalized component list.
2. Place orders for all required parts (sensors, relays, microcontrollers, etc.).
3. Begin working on setting up basic components such as switches, clock settings, and initial coding for the microcontroller.

* By the Final Demonstration Day, we expect to:

1. Have a fully functional prototype.
2. Complete several successful test runs to demonstrate the system’s ability to dry shoes efficiently using humidity, temperature, and weight control.
3. Showcase the system’s display, user interface, and Blynk IoT integration for remote monitoring and control.

### 10. Methodology

What is your approach to the problem?
Our approach to designing a smart shoe dryer tackles the problem of wet and odorous shoes by combining efficient drying with hygiene management and user-friendly controls. Here’s the breakdown:

#### Core Functionality: 

- Moisture & Odor Control: We’re incorporating a heating element with a fan to circulate warm air, promoting quick drying while minimizing condensation. An odor and germ filter is included to reduce bacteria and odors, addressing the hygiene aspect effectively.

- Temperature and Humidity Monitoring: Sensors monitor real-time conditions inside the dryer to optimize heating intensity and ventilation based on moisture levels.

#### Automation & Safety: 

- Controlled by ATmega328PB: The ATmega328PB serves as the main controller, processing sensor inputs to dynamically adjust the heater and fan, maintaining safe and effective drying without overheating. 

- Relay and Safety Logic: The ATmega controls relays to manage high-power components, ensuring safe and responsive device operation.

#### User Experience & Remote Control: 

- Local Display for Status: A compact OLED or LCD display shows drying status, humidity, and temperature, giving users a clear, at-a-glance understanding of the device’s operation.

- Wi-Fi & Blynk IoT Integration: The ESP32 module connects the device to Wi-Fi and integrates with the Blynk IoT platform, allowing remote monitoring and control. Users can start, stop, or adjust settings via their smartphone, enhancing convenience and accessibility.

#### Design and Maintenance: 

- Modular & Lightweight Design: The dryer will have a modular, lightweight enclosure that is easy to disassemble for cleaning, ensuring that maintenance is minimal and user-friendly.

### 11. Evaluation
- Drying Time: One of the primary metrics is the time it takes to dry the shoes. The initial target is to dry the shoes within 6 hours. Future improvements will focus on reducing this drying time without increasing energy consumption or causing any damage to the shoes.
- Accuracy of Dryness Detection: The system will use both weight and humidity as measures to determine when the shoes are fully dry. The accuracy of these readings like the weight fluctuation within +/- 50 grams and relative humidity levels, will be key in ensuring the shoes are dried without being overexposed to heat, which can damage them.

### 12. Proposal Presentation
Add your slides to the Final Project Proposal slide deck in the Google Drive.

https://docs.google.com/presentation/d/1UlWTaDfhGs1sIeoClrVQAtH8inhLJokr/edit?usp=sharing&ouid=103026498329444088626&rtpof=true&sd=true 




## Final Project Report

Don't forget to make the GitHub pages public website!
If you’ve never made a Github pages website before, you can follow this webpage (though, substitute your final project repository for the Github username one in the quickstart guide):  <https://docs.github.com/en/pages/quickstart>

### 1. Video

Link to the video - <https://drive.google.com/file/d/1IilFWwbBmbQqKNDm-Jm01vqyb_RhfAGt/view?usp=sharing>

### 2. Images

![Final image](image-5.png)

### 3. Results

#### 3.1 Software Requirements Specification (SRS) Results

* SRS 01 – Humidity and temperature sensors will continuously monitor the environment, sending data to the ATmega328pb every second and sending heater temperature every second as well and it's getting compared every 30 seconds.
* SRS 02 – The weight sensor will measure and update the shoe weight with a precision of 20 grams, and values will be logged every 30 seconds.
* SRS 03 – Relay switches will control the heater and fans based on pre-set temperature thresholds at 30°C , observed every 30 seconds.
* SRS 04 – The display will update every second to show the current temperature, humidity, and weight, as well as the percentage of drying progress.
* SRS 05 – The user can adjust the mode (Automatic, Manual, and Profile mode) via the buttons, with input processing every 30 seconds. (However for the scope for the final demonstration we are focussing on the automatic mode only.)
**Did you achieve your requirements?**
Yes. The modes can be selected and the readings for both the sensors are accurate. 
**How did you test? Show proof of work (videos, images, collected data, etc.)**

(posted with the hardware)

#### 3.2 Hardware Requirements Specification (HRS) Results
* HRS 01 – The project shall be based on the ATmega328pb microcontroller to control relays, heating coil, fans, and process sensor data.
* HRS 02 – A sensor shall be used to detect the weight of the wet shoe placed in the box. The sensor shall measure weight with an accuracy of 20 grams and send data to the microcontroller.
* HRS 03 – A heater shall be used as the drying element. The coil’s temperature shall be continuously monitored by a temperature sensor to avoid overheating. The system shall shut down the coil if the temperature exceeds a preset limit that 30°C. 
* HRS 04 – Two 5V fans shall be used to ensure the circulation of hot air inside the box. The fans shall operate in conjunction with the heating coil to provide an even airflow.
* HRS 05 – An LCD display shall be used to show the real-time weight of the shoe and the estimated drying time. The drying time will be calculated based on the weight and environmental conditions (temperature and humidity).
* HRS 06 – A temperature and humidity sensor shall be used to monitor the humidity and temperature inside the box, ensuring optimal drying conditions are maintained.
* HRS 07 – Relays shall control the power supply to the heating coil and fans, turning them on or off based on the shoe weight, temperature, and humidity readings.
* HRS 08 – A 5V power supply block shall power the microcontrollers and input devices, while a 12V power supply shall be used for the relays and output devices (fans), AC supply for the Heater. 
**Did you achieve your requirements?**
Yes. 
How did you test? Show proof of work (videos, images, collected data, etc.)
We directly started to work with the components. For the relay we tested with the LEDs to see if the switches would get turned on or not.

We measure the readings every 30 secs but we compare them every 15 mins. After the two/ three consecutive readings are the same, the shoe gets dried and we turn off the heater and the fans. 

**Proof**
[To be noted that that the box wasnt covered so the readings for the temperature and humidity are not that different. Also to be noted that the upper limit for the temp sensor was set to be 40 degrees C]

* Readings before the drying of the shoe:
![wet shoe](image-3.png)


* Readings after the drying process is complete :
![dried shoe](image-4.png)

  **Three topics**
1. I2C with weight sensor 
2. I2C with Humidity and temperature sensor
3. Power management
4. Interrupts
5. Timers
  
  **Input devices**
  1. humidity and temperature sebnsor
  2. weight sensor
  
   
   **Output devices**
1. LCD
2. Heated chamber
3. fans
4. mobaexterm
  

### 4. Conclusion

Reflect on your project. Some questions to consider: What did you learn from it? What went well? What accomplishments are you proud of? What did you learn/gain from this experience? Did you have to change your approach? What could have been done differently? Did you encounter obstacles that you didn’t anticipate? What could be a next step for this project?

* This project has been filled with it's ups and downs. All in all it was fun, we all learnt a lot of new things while applying the concepts that were taught in class. The teaching team has been a massive help, Not just 5190 TAs but even Miles who is a TA for 5180, has to be thanked for all the times he has helped us. 

* Lesson learnt - 

1. Before finalising the components, read the datasheet, maybe check if its actually clear and helpful.
2. The Logic analyzer is your friend.
3. How to reverse engineer the code based on the Logic analyzer readings if the datasheet is not helpful. 
4. How to write I2C drivers, although it took a lot of time. 
5. We learnt about Finite State Machines for assembling the code together. 
6. Some new skills that were explored and learnt - Lazer cutting, 3-D printing. 
7. We used two different sensors on the same atmega board.
8. We learnt how to wrok as a team 
9. How to divide tasks amongst the team 
10. How to study concepts together. 
11. How to remain calm and positive when everything else suggests that we shouldn't. 
12. How to frame your code in a proper way.  

* Approach change
  - none
* design change
  - as suggested by the professor, the location of the fans has been changed to optimize the airflow within the box.

* what could have been diffrently?
  - We should have been more through while selecting the components and we should have checked the datasheets to see how detailed and easy to read they were. 
  - We would have chosen a different thing for weight sensing, the load sensor, even though it has a 0.1 grams effor factor, we could have used something else as the datasheet for NAU7802 was not readable for us, and hence we used up a lot of our time to write code using the datasheet.
*  Did you encounter obstacles that you didn’t anticipate?
  - yes. some datasheets aren't helpful for begginers
  - combining the codes together isn't as easy as it seems. 
* What could be a next step for this project?
  -  Building up the manual mode and the profile mode.

