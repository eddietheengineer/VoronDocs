
# Software Installation

## OctoPrint

Install OctoPrint on the Raspberry Pi by following the instructions found at [OctoPrint Download](https://octoprint.org/download/)

Once installed, ssh to your Raspberry Pi (_Using PuTTY on Windows or the terminal on MacOS) at the address `pi@octopi.local`.  The default password is 'raspberry'.  It is highly recommended to change the default password using the following process:

* Login to Raspberry Pi
* `sudo raspi-config` (password may be requested again)
* Select "Change User Password" to change the password

## Klipper

_External References:_

* [Klipper Installation Instructions](https://github.com/KevinOConnor/klipper/blob/master/docs/Installation.md)
* [SKR Installation Instructions](https://3dprintbeginner.com/install-klipper-on-skr-1-3-speed-up-your-prints/)

### Installation

Once at the command line of the Raspberry Pi, run the following commands to download and install the latest version of Klipper:

```
cd
git clone https://github.com/KevinOConnor/klipper
./klipper/scripts/install-octopi.sh
```

### Firmware Flashing

* [SKR 1.3](./klipper/v2_skr13_klipper.md)
* [SKR 1.4](./klipper/v2_skr13_klipper.md)
* SKR mini e3 V1.2 (_coming soon_)
* SKR mini e3 V2.0 (_coming soon_)
* FYSETC S6 (_coming soon_)
* FLY (_coming soon_)

### Klipper Octoprint Configuration

The OctoPrint web server needs to be configured to communicate with the Klipper host software. Using a web browser, login to the OctoPrint web page and then configure the following items:

1. Navigate to the Settings tab (the wrench icon at the top of the page)
2. Under "Serial Connection" in "Additional serial ports" add "/tmp/printer" then click "Save"
3. Open Settings tab and under "Serial Connection" change the "Serial Port" setting to "/tmp/printer"
4. In the Settings tab, navigate to the "Behavior" sub-tab and select the "Cancel any ongoing prints but stay connected to the printer" option, then click “Save”
5. From the main page, under the "Connection" section (at the top left of the page) make sure the "Serial Port" is set to "/tmp/printer" and click "Connect". (If "/tmp/printer" is not an available selection then try reloading the page)
6. Once connected, navigate to the "Terminal" tab and type "status" (without the quotes) into the command entry box and click "Send". The terminal window will likely report there is an error opening the config file - that means OctoPrint is successfully communicating with Klipper.

## Initial Voron Printer Configuration

Download the respective Voron base configuration file from the following links:

* [V0 SKR mini e3](https://raw.githubusercontent.com/VoronDesign/Voron-0/master/VORON-0/Firmware/printer.cfg)
* [V1 SKR 1.4](https://raw.githubusercontent.com/VoronDesign/Voron-1/Voron1.8/Firmware/klipper_configurations/SKR_1.4/Voron_1_SKR_14_Config.cfg)
* [V2 SKR 1.3](https://raw.githubusercontent.com/VoronDesign/Voron-2/Voron2.4/firmware/klipper_configurations/SKR_1.3/Voron2_SKR_13_Config.cfg)
* [V2 SKR 1.4](https://raw.githubusercontent.com/VoronDesign/Voron-2/Voron2.4/firmware/klipper_configurations/SKR_1.4/Voron2_SKR_14_Config.cfg)
* [VSW SKR mini e3 V2.0](https://raw.githubusercontent.com/VoronDesign/Voron-Switchwire/master/Firmware/skr_mini_e3_v2_config.cfg)
* [VSW Einsy Rambo](https://raw.githubusercontent.com/VoronDesign/Voron-Switchwire/master/Firmware/einsy_config.cfg)

Using a secure file transfer program (WinSCP, Cyberduck, Notepad++, NppFT, BBEdit, scp), transfer the downloaded file to your Raspberry Pi into the folder `~/klipper/config`.

Copy the downloaded file into place with `cp ~/klipper/config/FILENAME_OF_VORON_CONFIG.cfg ~/printer.cfg`

**Note:** There are many ways of editing the config file that vary by personal preference.  Using Nano editor through SSH is simple but not always user friendly.  Notepad++ with the NppFTP plugin (Windows) or bbEdit (macOS) are user friendlier alternatives.  Instructions are found in the appendix.

Review the configuration file by running `nano ~/printer.cfg`

### Update Controller Path

Locate the section starting with [mcu].  The V2 will have an additional section starting with [mcu z] as it has two controllers.  These sections are where the controllers are defined and identifying them so that Klipper which which components are connected (and to which controller if there is more than one).

* Begin with all controllers disconnected from the Raspberry Pi.
* For printers with just one controller, connect that controller to the Raspberry Pi.  For printers with two controllers, connect the X/Y/E controller.
* On the Raspberry Pi, run `ls -l /dev/serial-by-id/`.  This is a slight difference from previous instructions as the USB ID never changes even if the USB cables are switched.
* The listing should look similar to this:

![](.images/file.png)

**Note:** If the device identifier has the word 'marlin' in it, the Klipper firmware is not loaded properly.  Go back and re-load the Klipper firmware before continuing.

* Copy the device ID (e.g. _asdkjfhasdkfjhaskdjfahs_) from the terminal window and paste into a temporary text file.
*  Open the configurtion file with `nano ~/printer.cfg` and navigate to the **[mcu]** section.  Modiffy the "serial: /dev/serial" line and paste in the controller path so that is looks like the following: `serial: /dev/serial/by-id/asdhsdafhshfgsdh`
*  Exit the text editor with CTRL-X  and save when prompted.

### Update Second Controller Path (V2)

This section only applies to printers with more than one controller.

* Connect the Z controller to the Raspberry Pi.
* On the Raspberry Pi, re-run `ls -l /dev/serial-by-id/`.
* The listing should look similar to this:

![](.images/file2.png)

**Note:** If the device identifier has the word 'marlin' in it, the Klipper firmware is not loaded properly.  Go back and re-load the Klipper firmware before continuing.

* Identify the new device ID (e.g. _asdkjfhasdkfjhaskdjfahs_) and copy from the terminal window and paste into a temporary text file.
*  Open the configurtion file with `nano ~/printer.cfg` and navigate to the **[mcu z]** section.  Modiffy the "serial: /dev/serial" line and paste in the controller path so that is looks like the following: `serial: /dev/serial/by-id/asdhsdafhshfgsdh`
*  Exit the text editor with CTRL-X  and save when prompted.

### Updating Printer Specific Settings

1. Open ~/printer.cfg file again and scan through the file.
2. Locate **[stepper_x]**.  Uncomment the _position\_endstop_ and _position\_max_ that corresponds to your printer's size and delete the other options to prevent confusion.
3. Under **[tmcXXXX stepper_x]**, replace XXXX with either 2208 or 2209 to match the type of TMC drivers that are installed.  For example, _[tmc2209_ _stepper\_x]_ for TMC 2209 drivers.
4. Repeat steps 2 & 3 for the **[stepper_y]** section.
5. Under **[stepper_z]**, uncomment _position\_max_ for your printer size and delete the other options to prevent confusion.  Also in the same method as step 3, update the **[tmcXXXX_stepper]** for configuration with the installed stepper type for all four Z motoros (Z, Z1, Z2, Z3).
6. Under **[extruder]** verify that the _sensor\_type_ is correct.  Do not worry about _step\_distance_ or PID values for now, they will be updated later in the setup process.  Update **[tmcXXXX extruder]** in the same fashion as step 3 to match the installed stepper driver for the extruder.
7. Under **[heater_bed]**, verify the temperature sensor type is correct.
8. Under **[display]**, uncomment the display section that matches the installed display.  Delete the others to prevent confusion.
9. **If printer is a V1**, Under **[z\_tilt]** and **[screws\_tilt\_adjust]**, uncomment the sections appropriate to the printer size.  Delete the other options to prevent confusion.
10. **If printer is a V2**, Under **[quad\_gantry\_level]**, uncomment the _gantry\_corners_ and _points_ sections appropriate to the printer size.  Delete the other options to prevent confusion.
11. Exit the text editor with CTRL-X  and save when prompted.

Under Octoprint's terminal tab type `FIRMWARE_RESTART` and press enter to send the command to restart Klipper.

The terminal window should show the following:

```
Recv: // Klipper state: Disconnect
[...]
Recv: // Klipper state: Ready
```

If after 30-60 seconds there is no Ready message, then run `STATUS` in the terminal window.  If Klipper comes back _Not Ready_ it will notify if there is a configuration issue that needs to be corrected.

### Klipper Troubleshooting and Common Errors

#### Retrieve Log File

The Klippy log file (/tmp/klippy.log) contains debugging information.
M112 command in the OctoPrint terminal window immediately after the undesirable event.

There is a logextract.py script that may be useful when analyzing a micro-controller shutdown or similar problem.

```
mkdir work_directory
cd work_directory
cp /tmp/klippy.log .
~/klipper/scripts/logextract.py ./klippy.log
```

The script will extract the printer config file and MCU shutdown information to work_directory.

#### TMC UART Error

This appears when the communication between the TMC drivers and the MCU is not working. Typically this means that you have not powered the SKR board with 12-24V (TMC drivers didn’t boot), you haven’t plugged in the TMC steppers to the correct spots, or you forgot to add or remove a jumper as detailed above.

#### ADC Error

ADC stands for “Analog to Digital Converter” and is what is used to convert thermistor readings to temperatures for your hotend and heated bed. As a safety precaution, if Klipper is expecting a thermistor to be plugged in but it is reading an invalid reading (no thermistor = open, or 0 ohms for a shorted wire as closed), it will go in to this shut down mode. Double check to make sure your thermistors are plugged in to the correct boards and plugs.

#### Unable to Connect

Once the underlying issue is corrected, use the `FIRMWARE_RESTART` command to reset the firmware, reload the config, and restart the host software. Check MCU IDs match your printer.cfg.  _Make sure you get the paths right!_


## Recommended OctoPrint Plugins
* OctoKlipper
* Themeify
* TerminalCommands
* Bed Level Visualizer
* Print Time Genius


## Mainsail

___Coming Soon___

