# Dual Extruding with 2 spools PLA

First, use Raise3d filament!  Don't use matterhackers....it'll end up jamming the machine.  I still need to test the 3dfuel and maybe kexelled.

Next, make sure your nozzle offsets are good!  

You want to export the different colors as different parts from onshape.

Once you get these into ideamaker, you can "align" (from the move tab) to combine them back into the original shape.  

Then, select each part, and choose left vs right extruder.  (left is default).

## Slicing settings:
Make sure both extruders are set to PLA.

I was having problems with an upside-down filet on my case...I started with the "speed" template, but then made the following tweaks:
* Layer tab:  
  * slice height to .2 (from .25)
  * shells  to 3 (from 1)
* Support tab:
  * use left extruder...this is different from when you have PVA in the right extruder!
  * Grid infill type
  * Max overhang angle to 30 degrees
  * reduce horizontal offset to 0.1mm  <- This may be too close.  Fillet looked great, but had trouble getting "ghost inset" support out and I needed to drill out the jack hole supports.  Doing 0.2mm with the ghost lip worked great...trying the case!
* temperature tab:
  * check cool down inactive extruder
* ooze tab:
  *  I just did a wipe wall.  (no wipe tower)
  *  Wipe wall mode  was interlaced
  *  Vertical wall (rather than waterfall)
  *  See notes below...

Then, after I sliced, I took a close look at the support.   Okay, actually, I was doing this all the way whilst experimenting with settings...which is how I
got to the above.

I printed with lid *OFF*.   When doing lid on, I had some melt in the fillet section.

## Wipe Wall vs Wipe Tower
Raise3D recommends doing both.

Wipe Towers help with a purge....means material is primed.  Go nested rather than interlaced when using 2 types of materials.

Wipe Walls are more for catching ooze.  I've been doing interlaced, vertical, but I think I'll go nested next time I do PVA.




