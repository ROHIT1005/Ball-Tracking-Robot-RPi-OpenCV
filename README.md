<!--
*** Thanks for checking out this README Template. If you have a suggestion that would
*** make this better, please fork the repo and create a pull request or simply open
*** an issue with the tag "enhancement".
*** Thanks again! Now go create something AMAZING! :D
-->

<h1>Red Ball Follower Robot<h1>


<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
    * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [License](#license)




<!-- ABOUT THE PROJECT -->
## About The Project


I made this project in order to build a basic ball tracking car. Here, my bot uses camera to take frames and do image processing to track down the ball. The features of the ball such as color, shape, size can be used.I have chosen raspberry pi as micro-controller for this project as it gives great flexibility to use Raspberry Pi camera module and allows to code in Python which is very user friendly and OpenCV library, for image analysis.

For controlling the motors, I have used an H-Bridge to switch from clockwise to counter-clockwise or to stop the motors. This I have integrated via code when direction and speed has to be controlled in different obstacle situations.

Crucial thing while detecting images frame by frame was to avoid any frame drops as then the bot can go into a limbo state if the bot is unable to predict direction of ball after few frame drops. Even if it manage the frame drops then also if the ball goes out of scope of the camera, it will go into a limbo state, in that case, then I have made my bot take a 360 degree view of it's environment till the ball comes back in the scope of the camera and then start moving in it's direction.

For the image analysis, I am taking each frame and then masking it with the color needed. Then for noise reduction, I am eroding the noise and dilating the major blobs. Then I find all the contours and find the largest among them and bound it in a rectangle. And show the rectangle on the main image and find the coordinates of the center of the rectangle.I have attached the algorithm (pseudo-code) of the image analysis part and demonstrated this part in the video also. 

Finally my bot tries to bring the coordinates of the ball to the center of its imaginary coordinate axis. This is how my robo works. I enjoy a lot working on this project and its a nice experience.

### Built With
1. Raspberry pi (any version) with raspbian os installed
2. 3 Ultrasonic sensors 
3. Motor driver (LM298 , L293D module)
4. Power supply
5. Jumper cambles (Feamle-female)
6. Camera module(use module over usb camera for better camera)
7. Red ball for testing 

### Prerequisites


1. Python2
2. opencv -3.10
3. picamera
4. Raspberry-pi with raspbian os installed


### Installation

1. Create a python file in raspberry pi
```sh
 sudo nano filename.py
 ```
2. Paste the code in file & Save 
```sh
cltrl+o & then cltrl+x
```
3. Connect the motor driver with raspberry pi (Refer : https://github.com/AmeyaUpalanchi/Interfacing-motor_driver-with-raspberry_pi/)

4. Connect the ultransonic sensors to the raspberry pi by refering diagram

5. Run the program 
```sh
python2 filename.py
```

<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.


