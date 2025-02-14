# Week 3.1 - Solid Operations in Rhino

## Agenda
- [Artist of the Day](#artist-of-the-day)
- [Solid Operations in Rhino](#solid-operations-in-rhino)
- Homework

## Artist of the Day

<img src="https://user-images.githubusercontent.com/1598545/189138511-e74e66cf-12dc-4b3c-b372-a6196d3ee79a.png" height=400>

[**Joseph Delappe**](http://www.delappe.net)

- [Low Polygon Sculptures](https://www.delappe.net/low-polygon-sculptures)
- [The Drone Project](https://www.delappe.net/drones)

## Solid Operations in Rhino

In rhino we can either natively author 3d shapes (create boxes, spheres, pyramids, etc.), or we can extrude/loft/revolve 2D drawings into 3d shapes. These two methods are typical for CAD softwares. There is one additional distinction between meshes, polysurfaces, solids, but we do not need to deal with that now.

1. 3D Viewports
   - When we are drawing in 3d, we are going to want to switch back to the 4-up view (top, front, right, perspective)
   - [4View](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/4view.htm) four views at once
   - [MaxViewport](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/maxviewport.htm) single view
   - The 4-up viewport lets us see things from the sides to draw in 3d.
2. 3D Primitives (Solids)
   - [_Box_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/box.htm)
   - [_Sphere_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/sphere.htm)
   - [_Cylinder_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/cylinder.htm)
   - What are Solids? ([solid](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#seealso/sak_solid.htm))
3. Solids from Curves
   - [_ExtrudeCrv_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/extrudecrv.htm) **<--- THIS IS OUR GOTO**
   - [_Revolve_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/revolve.htm)
   - [_Loft_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/loft.htm)
4. Boolean Operations (math with objects)
   - [_BooleanUnion_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/booleanunion.htm) join two objects together
   - [_BooleanDifference_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/booleandifference.htm) subtract one object from another
   - [_BooleanIntersection_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/booleanintersection.htm) create a new object from intersection of two objects
   - [_BooleanSplit_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/booleansplit.htm) split and make new objects at every intersection
   - Sometimes these operations may fail. Pay attention to error messages.
5. Exporting solids
   - ```STL files describe only the surface geometry of a three dimensional object without any representation of color, texture or other common CAD model attributes.```
   - [Exporting STL files](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#fileio/stereolithography_stl_import_export.htm)
   - We can open 3D files in programs like [Meshmixer](https://www.meshmixer.com/) (for mesh manipulations), [Cura Lulzbot Edition](https://lulzbot.com/support/cura) and [PrusaSlicer](https://www.prusa3d.com/prusaslicer/) (which slices files for 3d printing)

### Example 3D Basics

<img width="600" alt="image" src="https://user-images.githubusercontent.com/1598545/189884167-b5e94bb4-daca-4e90-a400-5ef851a55a75.png">

Rhino file: [basic_3d.3dm](../examples/basic_3d.3dm)

### Video Tutorial: 3d Basics
- Solids and Booleans (2024) [https://drive.google.com/file/d/1wmTymZ2-1NXu-gK_yVYPjY2buT-iyK77/view?usp=drive_link](https://drive.google.com/file/d/1wmTymZ2-1NXu-gK_yVYPjY2buT-iyK77/view?usp=drive_link)
- 3D Basics (2022) [https://drive.google.com/file/d/1pZno_b3Mrto5c5CASgu2xXLYR8rOhJnm/view?usp=drive_link](https://drive.google.com/file/d/1pZno_b3Mrto5c5CASgu2xXLYR8rOhJnm/view?usp=drive_link)


## Homework
- Ideas for [Project 1](../projects/project1.md) (Project is DUE Tuesday ~~10/22~~ 10/29)