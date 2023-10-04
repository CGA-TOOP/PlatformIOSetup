# PlatformIO nd Pololu3piplus32U4 Setup
Follow the steps below to install Platform IO, and program your robot for the first time.

## Configure Platform IO
1. Before we install the Platform IO extension, we need to ensure we have the python virtual environment module installed.  In order to do this we need to first add the universe apt repository.  Run the following command in a terminal window.  When prompted, select enter.
```
sudo add-apt-repository universe
```
3. Now run to following commands to update your package manager and install the python virutal environment module.
```
   sudo apt update
   sudo apt-get install python3-venv
```
4. Launch VSCode and install the PlatformIO IDE extension.
5. Now you can launch the platoform IO extension. If prompted, reload VSCode once Platform IO has completed the install.
6. A few more steps before we start programing our robot.  Open a terminal and run the following command.  This allows you to commute to the robot once connected.
```
sudo usermod -a -G dialout $USER
```
7. Restart your computer before continuing.

## Programming your Pololu3piplus32U4 robot
1. Open VSCode and then open the platform IO Extension.
2. Select New Project.
3. Fill in the next menu with the options indicated below:
 ![image](https://github.com/CGA-TOOP/PlatformIOSetup/assets/67393204/968c93b7-cc63-4253-b3a9-94b1440db1fd)
4. Once the project has been initialized copy and past the code below into the src/main.cpp file and save the file.
```
// This example shows how to blink the three user LEDs on the
// 3pi+ 32U4.

#include <Pololu3piPlus32U4.h>

using namespace Pololu3piPlus32U4;

void setup()
{

}

void loop()
{
  // Turn the LEDs on.
  ledRed(1);
  ledYellow(1);
  ledGreen(1);

  // Wait for a second.
  delay(1000);

  // Turn the LEDs off.
  ledRed(0);
  ledYellow(0);
  ledGreen(0);

  // Wait for a second.
  delay(1000);
}
```
5. Open the platformio.ini file and replace the contents with the code below and save the file:
```
[env:a-star32U4]
platform = atmelavr
board = a-star32U4
framework = arduino
lib_deps = pololu/Pololu3piPlus32U4@^1.1.3
```
6.  Ensure you robot is connected to your computer via USB.  Now you can selct the check mark icon at the top right and select upload.  If your upload was successfull you should now see the red, green, and yellow LED's on your robot blinking.






