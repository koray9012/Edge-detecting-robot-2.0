

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
