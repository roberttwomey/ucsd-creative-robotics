# Week 1.1 - 2D Basics

## Agenda
- [Artist of the Day](#artist-of-the-day)
- [Hands On](#hands-on): Touch and Feel
- Rhino Troubleshooting
- [Rhino 2D Basics](#rhino-2d-basics)

## Artist of the Day

<img src="https://user-images.githubusercontent.com/1598545/186651503-cd6f4b1e-3caa-4558-bd56-8bebda4ab708.png" width=600>

[Gabriel Schama](https://www.gabrielschama.com/2016lasercuts/) _(pre-2016)_

<img src="https://images.squarespace-cdn.com/content/v1/53a5f24de4b075cc2d02a753/1403581457661-D5AJYL1GPB6EAUKFO4R1/MegaReef01.jpg?format=2500w" width=600>

[Joshua Barbanel](https://www.joshuaabarbanel.com/reefs) Reefs _(2014-present)_

## Hands On
Touch and Feel with a variety of digital fabrication examples.

## Rhino Troubleshooting

- 2d modeling (this week and next)
- 3d modeling (after that)

## Rhino 2D Basics
Let's work through Rhino 2d basics together. 
1. Create new file from template. Small objects inches.
2. User interface:
   - Switch between single and quad (four-up) display. 
   - Pan, tilt, zoom in display. 
   - Turning __Grid Snap__ on and off. (To create points that stick to origin, 0.25in, etc.) Try as a text command: Type _Snap_ once to turn it on. Once to turn it off.
3. 2D Primitives
   - [_Line_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/line.htm). 
     - Choose start of line, end of line. 
     - Hold __shift__ key while drawing to make the line orthogonal (Right Angle). [_Ortho_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/ortho.htm)
   - [_Rectangle_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/rectangle.htm)
   - [_Circle_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/circle.htm)
   - [_Polygon_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/polygon.htm)
4. 2D Operations
   - [_Trim_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/trim.htm) uses one object to cut and delete parts of another object.
   - [_Split_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/split.htm) uses one object to cut and split another object.
   - [_Join_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/join.htm) connects objects to form a single object
   - [_Extend_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/extend.htm) lengthens or shortens a curve
5. Organization
   - [Layers](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/layer.htm). [Using layers](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#seealso/sak_layer.htm).
   - [_Group_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/group.htm)
   - [_Ungroup_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/ungroup.htm)
   - [Selecting](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#popup_actions/select_objects.htm). How to Select things with the mouse.
   - Selection Menu
6. Transforms
   - [_Scale_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/scale.htm)
   - [_Rotate_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/rotate.htm)
   - [_Move_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/move.htm)
7. Direct Manipulation
   - Changing objects once you have drawn them. We are dealing with [NURBS](https://wiki.mcneel.com/rhino/nurbs)
   - [_PointsOn_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/pointson.htm)
     - Click and drag to move points. Use transforms (_Move_). 
   - [_PointsOff_](https://docs.mcneel.com/rhino/6/help/en-us/index.htm#commands/pointsoff.htm)

### Example File 2D Basics

<img width="600" alt="image" src="https://user-images.githubusercontent.com/1598545/189883552-117aa5e6-15f9-41ba-83cb-5f5bd18673de.png">

Rhino file: [basic_drawing](../examples/basic_drawing.3dm)

## References
2D Vector softwares:
- Adobe Illustrator - ucsd site license
- Inkscape - ([download](https://inkscape.org/release/)) - FOSS
- (others?)

3D Modeling Softwares:
- Rhino - $$$ and now really on top of their "one trial per person" policy.
- Blender - ([download](https://www.blender.org/download/))
- Shapr3d - ([download](https://www.shapr3d.com/download)) free parametric modeling across Mac/Windows/iPad
- Fusion360
- Solidworks - ucsd site license
- (others?)
