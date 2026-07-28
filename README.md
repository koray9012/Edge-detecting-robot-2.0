

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
