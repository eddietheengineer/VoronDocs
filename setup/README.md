# Introduction

This setup guide containes all the the steps to go from an assembled printer into a functioning printer with a known working configuration.

Please read the guide carefully, there are many details that seem trivial but are included because of one or more people got stuck at these points. We as a community want to make sure that everyone has the best experience possible and learn from our mistakes. If you find a something confusing and would like clarification, that likely means someone else in the past or future will also find it difficult. Please reach out and we will gladly update the document.

It is designed to be a "universal" setup guide that can be used across all printers in the Voron lineup.  There are some items that are specific to a given printer(s), so those sections are specifically marked to be included.  If building a printer and a section is marked for a printer not being built, that section can be skipped.

If you need help and are not there already, please join the [Discord](https://discord.gg/voron)!

---
# [Wiring Information](./wiring/README.md)

---
# [Software Installation](./software.md)

---
# [Initial Startup Checks](./startup.md)

___
# [Slicer Setup](./slicer.md)

## First Print

Download the “voron\_design\_cube\_v6.stl” from the [Voron Github page](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/STLs/TEST_PRINTS), and open the file in the chosen slicer. Use the default slicer settings, but make sure the hotend temperature and bed temperature is correct for the filament you are using. A good starting point is 240C hotend temperature, 100C heated bed temperature, and 92% flow for ABS.

Slice the file and save the .gcode file to your desktop (if you haven’t set up the Octoprint Plugin or your slicer). Navigate to Octoprint in your web browser, and upload the file to Octoprint. Press “Print” and closely watch the beginning of the print. If your nozzle is too far or close to the bed, on your printer display press the knob, navigate to “Tune”, and adjust the Z offset distance (+ is further from the bed, - is closer).

Once you are printing (with your printer fully assembled), take a quick video, upload it to the Voron subreddit and eat a well deserved bowl of cereal!

![](./images/voron_cereal.png)

## Print Troubleshooting

Please refer to the [print troubleshooting](../support/print_troubleshooting) guide for more detailed coverage of diagnosing print issues.

---
# [Additional Docs / Advanced Tuning](./additional/README.md)

---
# Credits

These guides would not exist without contributions from the following people:

* eddie V2.058
* chron V2.226
* Iakabos V2.067
* fermion V2.202
* Timmitt V2.003
* insurgus V2.278
* Defib V2.213
* newb
* mjoaris