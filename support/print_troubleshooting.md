# Introduction

This is a guide designed to identify and assist with resolution of printing issues.  This guide is specifically designed for adjustments and tuning for the Voron line of printers.  Some of the tuning suggestions may apply to other printers but that responsibility is on the reader.

## Print Artifacts

#### Z Banding

If the banding occurs at a consistent interval, check to see if your Z belts are tensioned properly, Z idlers rotate correctly and are perfectly circular, and Z idler brackets are square to the frame.

#### Layer Shifts

Make sure AB belts are properly tensioned, all idlers spin properly, and all of the non-idler pulleys have a set screw registered against the ground part of the shaft. Make sure to use a thread locker.

#### Print lifts from bed

Make sure your Z_ENDSTOP_CALIBRATE has been performed and that you get a good result with the "paper test" or a 0.1mm feeler gauge. If the filament can be moved easily by hand when it has been laid down during a print, redo this process and move the Z down by ~0.01mm until the issue goes away. If your prints have the "elephant foot" effect (lowest layer sticks out further than the rest) you likely need to clean or replace your PEI as it shouldn't have to be squished that far to have good adhesion.

#### Print warps or has one area of the print lift from the bed

Use the same process as the "Print lifts from bed" issue, and make sure your cooling fans are only running at or below 25% during prints. Ideally you want to start them at a later layer, but even with ABS you want a little bit of cooling during prints due to the Voron having a stationary bed.

#### Parts are incorrectly dimensioned after print

Chances are it's due to belt tension and/or pulleys in some way. Verify that nothing has come loose, make sure your AB belts are evenly tensioned, etc.