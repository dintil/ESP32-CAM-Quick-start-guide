# ESP32-CAM-Quick-start-guide
A guide on how ESP32-CAM can be used.
All credit goes to "IoT Bhai", who made this video: https://www.youtube.com/watch?v=duUngvvYNPE

This guide explains how to configure the ESP32 within Arduino IDE v2.
The ESP32-CAM this guide is for, is not an ESP32-S2 or ESP32-S3, so if you have any other version, your experience may differ.

The program starts a web server in the ESP32, which connects to a WiFi signal.
The ESP32 then displays it's Local IP in the terminal.

After downloading and unzipping the .zip file, open the file called "CameraWebServer01.ino".
On line 36 and 37, WiFi SSID and Password respectively should be filled in. The program will not work without it.
The program is designed with face recognition and detection.
However, there are some problems, if the board package for ESP32 boards is newer than version 3.0.0, it won't compile because of some missing headers.
I have not been able to find these headers seperately, however I am sure it is possible to do so.
It can be solved in two different ways however:
1. Disable face recognition and detection.
   In the tab called "app_httpd.cpp", go to lines 33 and 37, and make sure they are set to 0.
   This disables face recognition and detection, and if you've chosen the right board, it should compile correctly.
2. Downgrade the ESP32 board package to a version older than 3.0.0.
   In the arduino board manager, search for ESP32, find the one by Espressif Systems, and choose a version older than 3.0.0.
   Click the 'Upgrade' button, and after a while, you can verify the code to see if there are any further issues.
   It did not work for me at first, because of some python processes that wouldn't run.
   I installed a package called 'python-pyserial' from AUR, and it worked after that, though I suspect most systems already have some similar package installed.


