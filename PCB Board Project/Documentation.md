## PCB Milling

In this project we milled copper PCB boards using the new milling machines in the fab lab. 

## Workflow (Design Phase)

Open new 3D project in MakeraCam

![screenshot](assets/css/ss_mkc.png)

Set material to PCB: Edit→Material→PCB

Set dimensions

X = 127mm

Y  = 101mm

Z = 1.7mm

Download files from Fab drive: (blue folder named Dubick)

Resistance1-F_Cu.gbr 

Resistance1-PTH.drl

Resistance1-Edge_Cuts.gbr

Import each of these files in MakeraCAM:

File→Import PCB→Downloads→Resistance1-Edge_Cuts.gbr→Open

File→Import PCB→Downloads→Resistance1-PTH.drl→Open

File→Import PCB→Downloads→Resistance1-F_Cu.gbr→Open

![screenshot](ss_files.png)

Anchor lower left corner:

Select whole design (highlight over everything)

Click “m” key

Select lower left corner in “Anchor” diagram at the top of new pop up (in top right corner of screen)

Under “Location” in pop up, set X to 6 and Y to 6 (offsets design from very edge of material)

Design should have moved to align with axes given

Path:

Under “2D Layers” menu, hide (eye with red cross through):

Resistance1-F_Cu.gbr_pad

Resistance1-PTH.drl_0.900 mm

Resistance1-PTH.drl_1.400 mm

Select 2D Path (in tool bar)→2D Pocket

Select whole (visible) design

Set “End Depth” to .05mm

Add tool x2

8mm Corn

.2mm*30Engraving(Metal)

Calculate

Drilling holes:

2D Path→2D drilling

Under “2D Layers” menu, hide (eye with red cross through) all but file with holes to drill (

End Depth: 1.7mm

Add tool: 8mm Corn

Calculate

Outside cut:

2D Path→2D Contour

Under “2D Layers” menu, hide (eye with red cross through) all but file with outside cut (Resistance1-Edge_Cuts.gbr)

End Depth: 1.7mm

Strategy: Outside

Tabs: Custom

Tab Shape: Triangle

Select “Add”

Click 3 places on outer edge (spaced fairly evenly apart)

Add tool: 8mm Corn

Calculate

Path→Export→Export OR if you want to edit file on milling machine’s computer, File→Save As, save file in downloads with .mkc format (file-type)

Upload file to your folder in Fab google drive

## Workflow (Milling Phase)

Installing material:

Slightly loosen (not remove) all bolts in machine bed except the 3 that are fully within the metal jig/holder (use screwdriver on right side of machine)

If copper board already on bed with design milled into bottom left corner, remove and reorient if possible or else replace

Orient PCB board on CNC machine so that your design will fit in bottom left corner (as it was displayed on Makera CAM)

Adjust rectangular metal holders near middle of bed (keep bolts where they are, slide and rotate rectangular piece) to be able to slide material under loosened bolts, and then do so

Move/rotate both rectangular metal back so that short end of rectangle with slot aligns with material (holding it down)

Screw all loosened bolts down fairly tightly (securing material, not overly tight)

Running file:

Download gcode.nc file from Fab google drive

Open Cavera Controller

Open file (top left corner) → Upload File → (should be in Downloads) select your gcode file (yourfilename.nc) → “Upload & Select” 

Idle (top left) → COM Port ___ (some number)

Additional settings (top right dropdown) → Display Manual Controls → Home

Tool status → ensure Voltage>3.6V

Second most right option on bottom bar → select (check) auto vacuum + select (check) auto-levelling; select Run

Machine should touch down at 25 points on material and then file should run (whole design should be automatically milled)

## Final Product

<img width="765" height="1020" alt="image" src="https://github.com/user-attachments/assets/815ddbf8-176c-4bd9-bd57-07fc9295ff81" />


## Reflection

After this process I realize that the majority of milling a PCB board is the design phase and ensuring everything is correct. The new milling machines have self-swapping tool abilities allowing the user to walk away from the machine once it is started. This accelerates the rate at which you can finish a project as you can now work on another component while your board is being milled. During this project many issues occured. First, during the design phase we were given incorrect dimensions for the copper board leading to setbacks when we tried to mill. When we realized that we needed to change the dimensions we tried to re open the file in the Makera cam software in order to edit the file. However, we kept recieving a "file opening error" message from the software. After sending the error code to AI we realized that we were not able to open the file due to the files format. In order to open and edit the file design in makera cam the file must be a .mks format. On the contrary, if you wish to open your file in the makera controller then the file must be in gcode.nc format.

 To access the links to the final product click here:

 https://github.com/JReng-cls/Rogers-Jake-portfolio/blob/main/PCB%20Board%20Project/Jaker_pcbtest.mkc

 https://github.com/JReng-cls/Rogers-Jake-portfolio/blob/main/PCB%20Board%20Project/RogersJ_gcode_pcdboardtest.nc
