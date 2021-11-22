# Raise3D
My notes on the Raise3D priniter and filaments

## PVA setup:
https://www.raise3d.com/academy/how-to-set-up-raise3d-pva-to-print/

## Nozzle Height calibration:
https://support.raise3d.com/Pro2-Series/how-to-calibrate-the-nozzle-height-4-223.html

## Nozzle Offset calibration:
https://support.raise3d.com/Pro2-Series/how-to-calibrate-the-nozzle-offsets-4-1332.html

EXCEPT EVERYTHING BELOW HAS OPPOSITE SIGN!!!!  FIGURE OUT WHY!
X "smaller" is if the R extrude is towards the material.
Y "bigger" is if the R extrude is towards the door.

My super-quick version:  (USE THIS!!!)
* For x, if the top block is too far to the right (towards the spools), increase the offset.   
* For y, if the top block is too far towards the door, decrease the offset.

Older analysis below...

Reading the model here is a little tricky.   Notes to help:
* Make sure when you print the model that you have X and Y oriented correctly.  Ideamaker puts down an X/Y/Z origin when you are "moving" the model to use as reference.  On the model:
  * the notch on "X" should be facing the door (x positve goes towards the material spools)
  * the notch on "Y" should be facing the spools (y positive goes AWAY from the door)
* The tower itself is comprised of squares of decreasing size:
  * The bottom square (I'll call it square 1) is from the left extruder and is 15 mm
  * The next one up (square 2) is from the right extruder and is 14.8 mm...meaning that there's a .1 mm gap on either side
  * Square 3 is from the left extruder and is 14.4 mm...meaning there's a .2 mm gap on either side
  * Etc...

So, if you do a print and you are *not* aligned between L and R extruder, the blocks from the right extruder will have "shifted" relative to the blocks fron the L extruder.

Deriving the shift and sign:
  * Start by looking with x towards you.
  * Check the layers from the top down, looking for a case where the two layers are lined up, either on the L or R side.
    * Those two layers will then indicate the magnitude of the offset in x...and the top block of the two tells you that offset.
    * now, imaging what needs to happen to shift the layer from the r extruder back to center.  If you are looking from the notch (like it was the door), then a shift to your left is negagive (reduce the offset) and a shift to the right is positive (increase the offset).
  * Repeat for the Y notch.
    * if they're lined up on the left, you need to reduce the y offset.
    * if they're lined up on the right, you need to increase the y offset.

Alternative (more brain-dead) method:
* Start with the x notch towards you.  Do any of the layers line up on the right side?
* If not, flip 180.  Now do any layers line up on the right side?
* The top layer of whichever layer lined up best has the offset printed on it!
* Repeat for y
