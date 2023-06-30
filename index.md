# Solar Tracker
Building upon the foundation of the Solar Tracker, I set out to enhance its functionalities by converting it into a joystick-controlled camera. While my modifications presented some challenges, particularly in terms of debugging the code and resolving wiring issues, I remained dedicated to the project. After several days of diligent troubleshooting and meticulous adjustments, I successfully transformed the Solar Tracker into a fully operational camera that responds seamlessly to joystick commands.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Edward D | Cleveland Charter High School | Electrical Engineering | Incoming Senior

<!--**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**-->

![Headstone Image](logo.svg)
  
# Final Milestone
As I approached the final milestone of my project, I focused on writing the code that would enable the joystick to control the movement of the servos. I started watching YouTube videos and searching up guides to learn how to integrate the joystick with the two servo motors, but eventually was able to succesfully integrate it with the help of my instructor. Additionally, I replaced the solar panel with an old phone case, which served as a convenient housing for my phone. This allowed me to capture photos and videos using a Bluetooth shutter.

<!-- Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below. -->

<!-- <iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>-->

# Second Milestone
The second milestone of this project was to successfully get the base project fully functional. To achieve this, I had to familiarize myself with the Arduino IDE, an integrated development environment used for programming Arduino microcontrollers. This software tool provided a user-friendly interface for writing, compiling, and uploading code to Arduino boards, allowing me to effectively develop and bring the project to fruition. I initially learned the basics of Arduino IDE before implementing the complete led code so I was able to read and tweak the code in the future.

<!-- Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below. -->

<!-- <iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>-->

# First Milestone
The first milestone of this project was to successfully assemble the Solar Tracker. After I had assembled it and run the code, I realized that the servos were not moving correctly. It took me a couple of days to realize that the problem was not the code, but an error I had made in zeroing the servos. Once all the wires and connections were properly established, the physical build of the Solar Tracker was complete. The Solar Tracker had a unique way of utilizing bolts and screws for all the connections, despite there being pieces that were connected both vertically and horizontally to each other.

<!-- Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below. -->

<!-- <iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>-->


# Schematics 
![Untitled Sketch_bb](https://github.com/EdwardDan1/EdwardD-Solar-Tracker/assets/113312727/111a033a-178a-4883-b26a-b55b3d5e6e1d)

# Code
Here is the code for my project:

```
#include <Servo.h>

Servo servo1;
Servo servo2;
const int joyX = A1;
const int joyY = A0;

int servoValX;
int servoValY;

void setup() 
{
  servo1.attach(6);
  servo2.attach(5);
  pinMode(joyX, INPUT);
  pinMode(joyY, INPUT);
}

void loop()
{
  servoValX = analogRead(joyX);
  servoValX = map(servoValX, 0, 1023, 0, 360);
  servo1.write(servoValX);

  servoValY = analogRead(joyY);
  servoValY = map(servoValY, 0, 1023, 0, 180);
  servo2.write(servoValY);


}
```

# Bill of Materials
Here is the parts list for my project:

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Initial Kit | The base Solar Tracker kit | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|
| Joystick | The joystick is used to move the servos | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|
| Remote Bluetooth Shutter | To take pictures and videos from my phone without touching my phone  | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|
| AAA Batteries  | To power the servos in the base project and the modified build | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|
| Phone Case | Mount my phone to the solar tracker | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|
| Velcro | Used to mount the phone case to the solar tracker | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|

<!--# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.-->
