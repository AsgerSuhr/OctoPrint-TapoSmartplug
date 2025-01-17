# OctoPrint-TapoSmartplug

This is a fork of https://github.com/TyFy/OctoPrint-TPLinkSmartplug, I've fixed a typeError in __init__.py

### 3 nov. 2023
updated to support new firmware update for tapo, please use this PyP100 library https://github.com/almottier/TapoP100 instead of the standard one.

##  How to install an off button for the Raspberry Pi
- https://embeddedcomputing.com/technology/open-source/development-kits/raspberry-pi-power-up-and-shutdown-with-a-physical-button
## Setup

Install manually using this URL:

    https://github.com/AsgerSuhr/OctoPrint-TapoSmartplug/archive/master.zip


## Configuration

Once installed go into settings and enter the ip address, username and password for your Tapo Smartplug device. Adjust additional settings as needed.

## Settings Explained
- **IP**
  - IP or hostname of plug to control. For strip devices use the format `<ip>/<0 based socket index>`, ie 192.168.0.2/0 would control the first socket in the strip.
- **Label**
  - Label to use for title attribute on hover over button in navbar. IMPORTANT! has to be the same as the name of the smartplug you are connecting to
- **Icon Class**
  - Class name from [fontawesome](https://fontawesome.com/v3.2.1/icons/) to use for icon on button.
- **Username**
  - email that you use to connect to the smart plug.
- **Password**
  - Password you use to connect to the smart plug.
- **Warning Prompt**
  - Always warn when checked.
- **Warn While Printing**
  - Will only warn when printer is printing.
- **On with Upload**
  - When checked, this will allow connected slicers to power on the device when uploading a file.  This requires OctoPrint 1.4.1rc or higher, and does not currently support uploading through the web browser.
- **GCODE Trigger**
  - When checked this will enable the processing of M80 and M81 commands from gcode to power on/off plug.  Syntax for gcode command is M80/M81 followed by hostname/ip.  For example if your plug is 192.168.1.2 your gcode command would be **M80 192.168.1.2**
  - Added with version 0.9.5 you can now use the custom gcode commands `@TAPOON` and `@TAPOOFF` followed by the IP address of the plug.  This option will only work for plugs with GCODE processing enabled.  For example if your plug is 192.168.1.2 your gcode command would be **@TAPOON 192.168.1.2**
- **Auto Connect**
  - Automatically connect to printer after plug is powered on.
  - Will wait for number of seconds configured in **Auto Connect Delay** setting prior to attempting connection to printer.
- **Auto Disconnect**
  - Automatically disconnect printer prior to powering off the plug.
  - Will wait for number of seconds configured in **Auto Disconnect Delay** prior to powering off the plug.
- **Run System Command After On**
  - When checked will run system command configured in **System Command On** setting after a delay in seconds configured in **System Command On Delay**.
- **Run System Command Before Off**
  - When checked will run system command configured in **System Command Off** setting after a delay in seconds configured in **System Command Off Delay**.
  
