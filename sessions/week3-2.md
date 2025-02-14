# Week 3.2 - Unrolling Surfaces

## Agenda
3d Basics and Unrolling Surfaces
- Artist of the Day
- [Unrolling Surfaces](#unrolling-surfaces)
- Work Time (Ex 4, Proj 1)
- Individual Project 1 Check-Ins
- [Homework](#homework)

## Artist of the Day

<img src="https://www.lawrencemalstaf.com/media/contentblock-large/589-img_2827.jpeg" width=600>

Lawrence Malstaf
- [Folding](https://www.lawrencemalstaf.com/work/folding/)
- [Shrink](https://www.lawrencemalstaf.com/work/shrink/)
- [Portfolio website](https://www.lawrencemalstaf.com/work/)

## Unrolling Surfaces

### Example Unrolling Surfaces

<img width="600" alt="image" src="https://user-images.githubusercontent.com/1598545/189140440-1254ab04-b1e7-4424-adbb-2de3c9869f86.png">

Rhino file: [unroll.3dm](../examples/unroll.3dm)

## Mesh to Flat Surface

- Simplify the mesh first ([ReduceMesh](https://docs.mcneel.com/rhino/mac/help/en-us/commands/reducemesh.htm) command)

### Unroll Surface command
- Flattening with [UnrollSurf](https://docs.mcneel.com/rhino/8/help/en-us/commands/unrollsrf.htm)
  - works on "developable" surfaces, only curving in one direction: 
    - <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/unrollsrf-005.png"> vs. <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/unrollsrf-006.png">
  - Can you construct an approximate 3d shape from "developable" sections? see this sphere from strips: 
    - <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/unrollsrf-007.png">
- To specify where the unrolled polysurface will split
  - Use the [UnjoinEdge](https://docs.mcneel.com/rhino/8/help/en-us/commands/joinedge.htm#UnjoinEdge) command
  - Select the edges that should be open after unrolling.

### Other 3D -> 2D Commands
- [FlattenSrf](https://docs.mcneel.com/rhino/8/help/en-us/commands/flattensrf.htm) draws a 2d outline of the developable surface in the construction plane.
- [Smash](https://docs.mcneel.com/rhino/8/help/en-us/commands/smash.htm) flattens double curved surface.
- [Squish](https://docs.mcneel.com/rhino/8/help/en-us/commands/squish.htm) and [SquishBack](https://docs.mcneel.com/rhino/8/help/en-us/commands/squish.htm#SquishBack)
  - <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/squishback_3dshapebefore.png"> <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/squishback_2dshapebefore.png"> <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/squishback_2dshapeafter.png"> <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/squishback_3dshapeafter.png">

### Other Re-Meshing Commands
- [ShrinkWrap](https://docs.mcneel.com/rhino/8/help/en-us/commands/shrinkwrap.htm)
  - <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/shrinkwrap.gif">
- [QuadRemesh](https://docs.mcneel.com/rhino/8/help/en-us/commands/quadremesh.htm)
  - <img src="https://docs.mcneel.com/rhino/8/help/en-us/image/topic_illustrations/quadremesh_rabbit.png">

## Homework
- [Exercise 4: Papercraft](../exercises/ex4.md) DUE Tuesday 10/22 **Design and Fabricate**
- Work on Project 1

## Reference
- [https://www.polyhedra.net/en/](https://www.polyhedra.net/en/)
- [Exact Flat for Rhino](https://www.exactflat.com/exactflat-for-rhino)

### Other Software

**Free**
- Blender [https://www.blender.org/download/](https://www.blender.org/download/) (free)
  - Export Paper Model extension: [https://extensions.blender.org/add-ons/export-paper-model/](https://extensions.blender.org/add-ons/export-paper-model/) (free)
- Papercraft: [https://github.com/rodrigorc/papercraft](https://github.com/rodrigorc/papercraft) (free, open source Mac or Windows)
  - (you have to build it on Mac with rust/cargo)

**Paid**
- Pepakura Designer: [https://tamasoft.co.jp/pepakura-en/](https://tamasoft.co.jp/pepakura-en/) (Windows $$)
- Unfolder: [https://www.unfolder.app/](https://www.unfolder.app/) (Mac $$, free trial)
- Papermaker: [https://papercraft-maker.com/](https://papercraft-maker.com/) (online, $$ to export) 
  
### Video Tutorials

#### Rhino Unroll Surfaces
- Rhino 3d unfolding: [https://www.youtube.com/watch?v=uhpe1p03Av0](https://www.youtube.com/watch?v=uhpe1p03Av0)
- Becky Chierichetti round complex curve organic shape to papercraft with Rhino: [https://www.youtube.com/watch?v=f27CniZ5ErA](https://www.youtube.com/watch?v=f27CniZ5ErA)
- RhinoGuide 3D to 2D to 3D: [https://www.youtube.com/watch?v=xhmDp1_rXGk](https://www.youtube.com/watch?v=xhmDp1_rXGk)
- Unfold polysurface unroll surface and labels: [https://www.youtube.com/watch?v=I2A0Mme6by4](https://www.youtube.com/watch?v=I2A0Mme6by4)
- [Digital Design Unit - TU Darmstadt](https://www.youtube.com/@digitaldesignunit) Curved folding with Rhino [https://www.youtube.com/watch?v=du2VN2rhNgM](https://www.youtube.com/watch?v=du2VN2rhNgM) - simulation and unrolling
- Origami folding with Rhino and Kangaroo [https://www.youtube.com/watch?v=htxKMyhoe5k](https://www.youtube.com/watch?v=htxKMyhoe5k)

#### Rhino to Pepakure
- Unfold a Rhino model using Pepakura software [https://www.youtube.com/watch?v=PnO7Ebl5yb0](https://www.youtube.com/watch?v=PnO7Ebl5yb0])

### Blender for Papercraft
- Blender for Papercraft [https://www.youtube.com/watch?v=2qwZGWjhtcM](https://www.youtube.com/watch?v=2qwZGWjhtcM)
- Export blender as paper model [https://www.youtube.com/watch?v=2_RSrkYBcUI](https://www.youtube.com/watch?v=2_RSrkYBcUI)

