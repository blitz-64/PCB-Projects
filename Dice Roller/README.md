This project was a KiCad PCB design created to function as a dice roller circuit. The PCB uses 7 Charlieplexed LEDs to use minimal pins on the microcontroller (ATtiny85-20P), allowing for the button, power switch, and reset to be connected as well. This board simply works by turning it on using the power switch and pressing the button to "Roll" the dice. Pressing the button would cycle through different LED patterns until it is let go, where the LED cycling would slow down until reaching a final random pattern that showed the number rolled (1-6). The PCB functioned using a coin battery on the back, seen below, although there was no 3D model for a coin battery footprint since it was a custom made footprint made in KiCad. 
This PCB was printed and the components were soldered on physically. The microcontroller was soldered on the board after programming it. A simple plastic case was modelled using SolidWorks (and KiCad for the PCB 3D model) and 3D printed. Unfortunately, I do not have the files for the 3D assembly and the program compiled onto the ATtiny84-20P, however a basic explanation for the idea behind the code is below.

## Code/Program Explanation:
The code to make this work was written in C++ using the Arduino IDE. 
It worked by setting up all the required components (LEDs, button, etc.) for I/O use. For the LEDs, 6 functions were made to light them up to visualize the patterns on a dice for each number. In a continuous loop, it would check if the button was pressed. When the button was pressed, it would cycle through these patterns with an exponential-like increasing delay between them, until it finally ended on a random number/pattern. With the LEDs being charlieplexed, some patterns had to flicker separate LEDs on/off with little delay to give the illusion to the eye that multiple were on at the same time although they physically could not be.
 
## Circuit Schematic
<img width="1350" height="592" alt="dangle die circuit schematic" src="https://github.com/user-attachments/assets/41ffab54-9707-45c8-b4e7-dd51e058e129" />

## PCB Layout Views

<img width="960" height="942" alt="front view dangel die" src="https://github.com/user-attachments/assets/c64de263-2bb3-44f8-8d6a-5dff457ba56f" />
(Front)

<img width="931" height="935" alt="back view dangle die" src="https://github.com/user-attachments/assets/ebf3e0a3-9ee0-43d5-907e-1d2789634c19" />
(Back)
