# Voron Documentation Style and Layout Guide

## File Locations

Every major section is under a different subdirectory.  The main page is README.md, the other sub-pages are named appropriately.  For every subdirectory there will be an 'images' directory where all of the images for content on that level will be stored.

## Content

The headers should be used appropriately, with H1 defining the major sections, and H2 through H4 defining sub-sections.  If a sub-section is specific one or more printers, put the short name of the printer(s) in the header.

* Mini12864 Display (V1, V2, Switchwire)

Inline links should avoid the use of the the link word here' (e.g. "to see the content go <here>").  Instead use the name of the target (e.g. "to see the content please go to the <target page>").

## Formatting

All of GitHub documentation content uses a variant of the [Markdown syntax](https://www.markdownguide.org/cheat-sheet/).

### Inline Code

Any commands (command line, gocde) or single line configuration examples should use the backtick (\`) to make the content appear as inline code.  Gcode commands should be all upper case.

* `nano ~/printer.cfg`
* `serial: /dev/serial/by-id/usb-Klipper_lpc1768_0650000AA39C48AFABD4395DC22000F5-if00`
* `FIRMWARE_RESTART`

### Code Blocks

Inline configuration file examples or large code examples should use the triple backtick (\`\`\`) to make the content appear as a code block.

```
[printer]
kinematics: corexy
max_velocity: 350
max_accel: 3000
max_z_velocity: 50
max_z_accel: 350
square_corner_velocity: 10.0
```

### File Names

All file names should be italicized.

* *filename.txt*

### Inline Configuration References

All inline configuration references, especially configuration file section headers, should be in bold.  Spcific confguration items under a header should be italicized.

* Under **[quad\_gantry\_level]**, uncomment the *gantry_corners* and *points* sections appropriate to the printer size.

### Notes or Warnings

Items of note should be italicized and should prefaced with the text 'NOTE:' (but isn't mandatory).  Items of warning should be in bold and should be prefaced with the text 'IMPORTANT:' or 'WARNING:'.

* **IMPORTANT: Never plug or unplug any device while the printer is powered.**
* *This section may need an update*

### Lists

List follow the Markdown standard, both ordered and unordered.

## Open items

* Github markdown does not appear to support underline.  The underscore creates what appears to be a comment block.  May be useful.
* Suggestions for extension or modification of this style guide are welcome.  Please submit a github issue.





