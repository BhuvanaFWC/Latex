# Vaman WiFi Code Uploading with Arduino

This repository contains code for utilizing Vaman by uploading WiFi credentials into it using an Arduino. Follow the steps below for setup and usage.

## Installation Steps

1. Follow all the steps as given in [vaman/installation/termuxdebian/termuxubuntu_esp32.txt](vaman/installation/termuxdebian/termuxubuntu_esp32.txt).
   OR
   Download all the provided files and follow the installations in point 3.

2. Install necessary dependencies:

   ```bash
   apt update && apt upgrade
   apt install python3-pip
   pip3 install platformio
   pio lib --global install "stempedia/DabbleESP32"
   ```

3. After performing the first step, a setup file will be created. Alternatively, if you perform step 2 and 3, you can skip the 4th step.

4. In the setup file, you will find 4 files inside it, namely: `src`, `.pio`, `platformio.ini`, and `README.md`.

5. Remember to change the `main.cpp` file in the `src` folder:

   ```cpp
   #define STASSID "Salient" // Add your network username
   #define STAPSK "12345678" // Add your network password
   ```

## Uploading WiFi Code to Vaman

1. Connect the Arduino and Vaman together.

2. Connect Arduino to the phone via OTG and then connect Vaman to Arduino following the instructions in the installation PDF.

3. Navigate to the setup directory and run:

   ```bash
   pio run
   ```

4. Remove the enable pin (`EN`) as soon as it displays "Connecting...". Then, remove pin `0` when it displays "Writing 100%" and before "Leaving...".

5. Once successfully uploading the code, you can upload new code using:

   ```bash
   pio run -t nobuild -t upload --upload-port 192.168.210.X
   ```

Replace `192.168.210.X` with the appropriate IP address.

Remember to refer to the `README.md` file for additional information and updates.

