# Week 4.1 - Intro to 3D Printing

## Agenda
- Review Papercut exercise.
- [Artist of the Day](#artist-of-the-day)
- Introduction to 3D Printing
  - [Importing Models](#importing-models)
  - [Prepping for 3DP](#prepping-for-3dp)
  - [Slicing for 3DP](#slicing-for-3dp)
  - [Printing](#print)
- Intro to the 3d Printer
- [Homework](#homework)

## Artist of the Day

<img src="https://user-images.githubusercontent.com/1598545/193049455-8f5a7e69-7534-4ca8-9eb5-44157fa4aa76.png" width=400>

**Urs Fischer** ([website](https://ursfischer.com/))

```
Untitled (Lamp / Bear)
2005-2006
Cast bronze, epoxy primer, urethane paint, acrylic polyurethane topcoat, acrylic glass, gas discharge lamp, stainless-steel framework
275 5/8 x 255 7/8 x 295 1/4 inches
(700 x 650 x 750 cm)
```
([link](https://ursfischer.com/searches/bear))


## Importing Models

- Create a new file in Rhino and import a 3d scan 
  - [bunny.ply](../examples/bunny.ply) (3MB)
- Find the bunny and scale to an appropriate size. 
  - Locate (Zoom eXtents), Rotate, Scale
  - Simplify Mesh (MeshReduce) if necessary

## Prepping for 3DP
- Add a base to your object
  - (use your solid tools—extrusion, cylinder, cube, etc. to construct a base)
  - [MeshBooleanUnion](https://docs.mcneel.com/rhino/8/help/en-us/commands/meshboolean_commands.htm#MeshBooleanUnion) to join the parts
- Add a label (text objects as solids)
  - Create [TextObject](https://docs.mcneel.com/rhino/8/help/en-us/commands/meshboolean_commands.htm#MeshBooleanUnion) 
  - be sure to select "Solids"
  - "Group Output"
  - [MeshBooleanUnion](https://docs.mcneel.com/rhino/8/help/en-us/commands/meshboolean_commands.htm#MeshBooleanUnion) to join the text to the model
- Check that it is a closed object? 
  - Look at the object properties (click on propertiese sidebar and then select the object)
  - If not, use **Mesh -> Repair Tools -> [Fill All Holes](https://docs.mcneel.com/rhino/7/help/en-us/commands/fillmeshhole.htm#FillMeshHoles)**
- Save as STL
  - Select your object. 
  - In **File -> Export** select STL file (Stereolithography). Answer yes to most questions.

### Example
<img width="600" alt="image" src="https://user-images.githubusercontent.com/1598545/191771117-8152421f-1818-4d31-8464-bcbce680bcfb.png">

Rhino file: [../examples/venus_sculpture.3dm](../examples/venus_sculpture.3dm)



## Slicing for 3DP

__At Envision__

- Printers:
  - Prusa Mini (preferred)
  - Prusa Mk4s (for a slightly larger print)
  - Bambu labs
  - [Lulzbot Taz 5](https://lulzbot.com/learn/introducing-the-lulzbot-taz-5) (very large prints)
- Slicers:
  - [Prusa Slicer](https://www.prusa3d.com/page/prusaslicer_424/) (installed on 3d printer computers)
  - only for the Lulzbot [Cura Lulzbot Edition](https://lulzbot.com/support/cura)
  - NOTE: you can also run these locally, and export your GCODE file to a USB stick.

See the Envision 3d printing tutorial: [https://youtube.com/@envisionucsd?si=rCXeHmcu7rI46E-M](https://youtube.com/@envisionucsd?si=rCXeHmcu7rI46E-M)

Process:
1. Open your slicer software and load the STL file from the previous steps
2. Check scale, positioning. 
3. Select print parameters.
  - Material (PLA most likely)
  - Slicing
  - Support
4. Export GCODE and save to USB to use with the printer. 
  - (note the print duration/time)
5. Pay at the kiosk to activate your printer.

NOTE: You need to complete the Envision 3d pringing training to activate your account for the 3d printers [https://envision-maker.ucsd.edu/access/training_videos.php?training_id=11](https://envision-maker.ucsd.edu/access/training_videos.php?training_id=11)

__At DIB Makerspace__

Makerspace FDM printing video: [https://www.youtube.com/watch?v=TDqjAnIWnAs](https://www.youtube.com/watch?v=TDqjAnIWnAs)
- Printers:
  - Prusa Mini 3D
  - Prusa Mk4s
  - Prusa XL
- Slicer: [Prusa Slicer](https://www.prusa3d.com/page/prusaslicer_424/)

Follow the process from above.

## Print

Print your file on the printers!

## Homework
- Finish [Project 1](../projects/project1.md) for Tuesday 10/29 critique.
- [Exercise 5 - Trophy](../exercises/ex5.md) DUE Thursday 10/31 11:59pm

## Reference

### Slicer Software

__Envision__
- Slicer software at Envision: [CURA Lulzbot Edition](https://lulzbot.com/support/cura)
  - you can install on your computer, to learn, but you will do actual slicing, etc., on Envision machines.

__Makerspace__

- Slicer software for Makerspace: [Prusa Slicer](https://www.prusa3d.com/page/prusaslicer_424/)

- First Print with Prusa Slicer [https://help.prusa3d.com/article/first-print-with-prusaslicer_1753](https://help.prusa3d.com/article/first-print-with-prusaslicer_1753)
- See the complete First Print with Prusa Slicer article from Prusa: [https://help.prusa3d.com/article/first-print-with-prusaslicer_1753](https://help.prusa3d.com/article/first-print-with-prusaslicer_1753)

### Places to get 3d models
- [https://www.printables.com/](https://www.printables.com/)
- [https://www.myminifactory.com/](https://www.myminifactory.com/)
- [https://www.thingiverse.com/](https://www.thingiverse.com/)
- [https://3d.csm.ai/](https://3d.csm.ai/)
- Search for **.STL** files on google. If you find a good source, plese share it with the class.

### Meshmixer
- [Meshmixer](https://www.meshmixer.com/) has been integrated into [Fusion 360](https://www.autodesk.com/products/fusion-360/free-trial)
- Hacking things together with meshmixer.
- Exporting for 3DP (.STL)