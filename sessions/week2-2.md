# Week 2.2 - Laser to 3D: Stacked Contours

## Agenda

- [Artist of the Day](#artist-of-the-day)
- Hands-On
- Homework

## Artist of the Day

<img src="https://www.inmilee.com/img/Un_001.jpg" height=500>

Inmi Lee. [_I will not dance_](https://www.inmilee.com/un.html) (2016)

Also:
- [d  i  s p lace](https://www.inmilee.com/displace.html) 2005
- [complete projects](https://www.inmilee.com/index.html)

## Handson

Continuing with extracted contours. 

### 1. Download a Mesh

From the internet. Where to get 3d meshes?
- Printables: [https://www.printables.com/](https://www.printables.com/)
- Thingiverse: [https://www.thingiverse.com/](https://www.thingiverse.com/)
- Sketchfab: [https://sketchfab.com/features/free-3d-models](https://sketchfab.com/features/free-3d-models)
- Thangs: [https://thangs.com/](https://thangs.com/) (have to register I believe)

### 2. Extracting Contours from a Mesh

__Clean up the Mesh__

- Importing and slicing a complex mesh
  - Finding a mesh (thingiverse.com)
  - Importing a mesh into rhino
  - Slicing a mesh with the contour command
  - slicing/design for digital fabrication (material thickness considerations)
- Simplifying mesh
  - [ReduceMesh](http://docs.mcneel.com/rhino/7/help/en-us/commands/reducemesh.htm)
- Go from mesh to unrollable surface: 
  - [MeshToNURB](http://docs.mcneel.com/rhino/7/help/en-us/commands/meshtonurb.htm)

__the NEW way__ (Rhino 8)

<img src="media/nested-clipping-sections.png" width=600>

  - In the top view, select your object and create a [ClippingSection](https://docs.mcneel.com/rhino/8/help/en-us/commands/clippingplane.htm#ClippingSections) centered on the origin. 
  - In the front view, use [Array](https://docs.mcneel.com/rhino/8/help/en-us/commands/array.htm) to copy the sections. Try 1 for X, 24 for Y, 1 for Z. 
  - Select your stack of ClippingSections, and use [NestedClippingDrawing](https://docs.mcneel.com/rhino/8/help/en-us/commands/clippingplane.htm#NestedClippingDrawing) to create a flat layout of those clipped sections.

 Reference: see Sectioning for Fabrication [https://www.rhino3d.com/stories/fabrication/sectioning-for-fabrication/](https://www.rhino3d.com/stories/fabrication/sectioning-for-fabrication/)


#### Example File: Buffalo Contours

<img width="600" alt="image" src="https://user-images.githubusercontent.com/1598545/189891871-067e9994-7137-4afd-b115-b3f5a529326b.png">

Rhino file: [buffalo_contours.3dm](../examples/buffalo_contours.3dm)

#### Example File: Sliced Pikachu

<img width="600" alt="image" src="https://user-images.githubusercontent.com/1598545/189891434-480d9b21-ffcf-4623-ae8a-09f4dcfb078f.png">

Rhino file: [sliced_pikachu.3dm](../examples/sliced_pikachu.3dm)

### 3. Fabricate 

Fabricate out of flat material with the laser cutter.

## Video Demo: Extracting Contours from Mesh

Video Demo [Meshes and extracting contours](https://drive.google.com/file/d/1X88VT5_L5-1gZ7oKHOcodeJW6JrbHYpH/view?usp=drive_link) (google drive video)

## Homework
- [HW3 Stacked Contours](../exercises/ex3.md) Design Only NO FABRICATION (Due Tuesday 10/15)
- Start ideating for [Project 1](../projects/project1.md) (DUE Tuesday 10/22)

## References
[TK]
