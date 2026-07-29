

                                  Edge-detecting robot 2.0
                                          By Koray                                                                                                  
![image alt](https://github.com/koray9012/Edge-detecting-robot-2.0/blob/main/15409.jpg?raw=true)
An upgraded, multi-mode ESP32 rover that navigates high surfaces like tables without yeeting itself off the edge. 
You can let it drive around completely on its own, or take full control over Wi-Fi from your phone.

Key Upgrades & Features
  
 Dual-Laser Precision Guidance:

  • Uses two VL53L0X Time-of-Flight laser distance sensors to spot drop-offs and table edges instantly before the robot goes over.

 Low-Latency Wireless Web Interface:

  • Hosts its own ESP32 Wi-Fi Access Point running a custom touch web dashboard so you can drive it smoothly from your phone without the controls lagging or dropping out when you hold a button down.

 4 Dynamic Modes (One-Button Toggle):

  • Autonomous Mode: Fully self-driving fall-avoidance routine that automatically stops, backs up, tank-turns, and carries on whenever it spots a drop-off.

  • Manual + Safety Mode: Lets you drive manually from your phone, but automatically steps in and overrides your inputs if you're about to drive off an edge.

  • Suicide Mode: 100% raw manual control with all safety features turned off, letting you maneuver completely unrestricted.

  • Diagnostics Mode: Real-time debug mode showing live laser readouts in millimeters and Wi-Fi status on the SSD1306 OLED screen.

 Onboard Telemetry & Feedback:

  • Features a live digital speedometer, a visual PWM motor bar, and a buzzer for instant audio alerts whenever an edge is detected.

How to use: 

To use it first you need to connect the custom 2S battery pack to the battery connectors and then switch on the master power switch. After you switch it on you will instantly be in automatic mode. To change the you just press the red button and it cycles between the modes. If you want to control it with your phone you press the red button until you reach diagnostics mode where you can see if your phone has connected to the esp32 and to connect you open you wifi settings, choose "Robot-Control", write the pasword 12345678 and connect and then you wait for your phone to connect. When you connect to the esp32 you open google or any search engine and write 192.168.4.1 where it opens you the controller page where you have up, down, left, right and stop and then you just press the red button on the car until you are in manual + help or suicide mode and you are ready to control it. It has 10m of range which is plenty for most people.

Here is so clean instructions on how to do it step by step:

Operating Instructions
1. Power On
  1.Connect your custom 2S battery pack to the battery connectors.

  2.Flip the master power switch to turn on the robot.

  3.The robot defaults to Autonomous Mode on startup.

2. Mode Selection
  1.Press the red button to cycle through the 4 operational modes:

   • Autonomous Mode (Default)

   • Manual + Safety Mode

   • Suicide Mode

   • Diagnostics Mode

3. Connecting Your Phone (Wi-Fi Control)
  1.Cycle the red button until you enter Diagnostics Mode.

  2.On your phone, open Wi-Fi settings and connect to Robot-Control (Password: 12345678).

  3.Check the robot's OLED screen in Diagnostics Mode to confirm your phone connected (it will say CONNECTED).

  4.Open your phone's browser and go to 192.168.4.1 to load the control interface.

  5.Cycle the red button on the robot to Manual + Safety or Suicide Mode.

  6.Drive using the touch directional pad! (Effective Wi-Fi range is ~10 meters).

  Why I made it:

After building the first version, I realized that ultrasonic sensors on a fast-moving robot were kind of a mess for precision edge detection—they were too slow, had weird wide beam angles, and sometimes missed the table edge completely. Plus, only having autonomous mode got boring fast.

I wanted to take everything I learned from 1.0 and turn it into a legitimate, multi-mode rover. For 2.0, I ditched ultrasonic for twin Time-of-Flight laser sensors so it could measure distances instantly with millimeter accuracy. I also wanted complete control over the robot, so I built a custom ESP32 Wi-Fi web server that lets me drive it straight from my phone with real-time safety overrides, added an OLED dashboard with a live speedometer, and threw in "Suicide Mode" for when I just want raw, unrestricted driving. I hated needing 2 9V batteries bc they arent the cheapest and also are not very efficient and constantly need to be replaced so i decided to study a little more and make my first 2 cell 18650 battery pack which with its 2 3400mah 18650 batteries for 7.4V surpass the 9V in every way.

It started as a simple cliff-avoidance test, but turned into a full-on crash course in I2C multiplexing, web socket latency tuning, C++ state machines, and custom hardware integration and i plan to upgrade it constantly and one day to make it absolutely perfect.

### Wiring & Connections:

Below is the visual schematic diagram for Edge Detector 2.0.

![image](https://github.com/koray9012/Edge-detecting-robot-2.0/blob/main/%D0%95%D0%BA%D1%80%D0%B0%D0%BD%D0%BD%D0%B0%20%D1%81%D0%BD%D0%B8%D0%BC%D0%BA%D0%B0%202026-07-29%20005514.png?raw=true)

### Pinout Breakdown:

| ESP32 Pin | Component | Connected Pin / Note |
| :--- | :--- | :--- |
| **GPIO 14** | L298N Motor Driver | ENA+ENB (PWM Speed Control) |
| **GPIO 27** | L298N Motor Driver | IN1 (Right Motor) |
| **GPIO 26** | L298N Motor Driver | IN2 (Right Motor) |
| **GPIO 25** | L298N Motor Driver | IN3 (Left Motor) |
| **GPIO 33** | L298N Motor Driver | IN4 (Left Motor) |
| **GPIO 17** | Left VL53L0X Laser | XSHUT  |
| **GPIO 18** | Right VL53L0X Laser | XSHUT |
| **GPIO 21** | OLED + Both Lasers | Shared I2C SDA |
| **GPIO 22** | OLED + Both Lasers | Shared I2C SCL |
| **GPIO 4** | Mode Pushbutton | Button Pin (other pin to GND) |
| **GPIO 19** | Active Buzzer | Buzzer (+) Positive |
