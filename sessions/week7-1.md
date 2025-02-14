# Week 7.1 - Detailed Mesh Editing

## Agenda
- [Artist of the Day](#artist-of-the-day)
- Conclude Mesh Repair Demo (self-portrait)
- Introduce [Project 2 - Hybrid Object](../projects/project2)
- Work Time
  - Questions about Digital Sketchbook?
  - Ideas for Project 2

## Artist of the Day

<img src="https://whitneymedia.org/assets/artwork/66072/2022_118_vw2_cropped.jpeg" width=600>

Artie Vierkant _[Image Object Thursday 4 June 2015 12:53PM](https://whitney.org/collection/works/66072)_ 2015

- Other Hybrid Object Examples

## Activities
Detailed mesh repair demo:
1. Scale and orient to fit using [Gumball](https://docs.mcneel.com/rhino/8/help/en-us/commands/gumball.htm?Highlight=gumball) or Move/Rotate.
2. [MeshTrim](https://docs.mcneel.com/rhino/8/help/en-us/commands/meshtrim.htm?Highlight=MeshTrim). Draw 2d lines from Top, Front, Side perspective, then use MeshTrim to cut the mesh down to size.
3. [PatchSingleFace](https://docs.mcneel.com/rhino/8/help/en-us/commands/patchsingleface.htm?Highlight=patchsingleface) select two open edges and add a face to fill mesh.
4. [AppendFace](https://docs.mcneel.com/rhino/8/help/en-us/commands/3dface.htm#Append) select points to add a new triangel to "close off" an open side of a mesh. This allows you to then fill the hole.
5. [FillMeshHole](https://docs.mcneel.com/rhino/8/help/en-us/commands/fillmeshhole.htm?Highlight=fillmeshhole) to fill in more faces to cover the hole. Hole needs to be well-bounded, enclosed (so do the append face first if you need to)

Check your Object Properties to see if you have successfully "closed" your mesh.

When your face object is closed, you can MeshBooleanUnion with the base object.

## Homework
- **HW** [In Class: 3d Scan for Class Portrait](https://canvas.ucsd.edu/courses/60628/assignments/872324) DUE Friday Nov 15 end of day (EOD)
- **HW** [Project 2 Proposal](../projects/project2.md#proposal) DUE Friday Nov 15 end of day (EOD)
- **HW** [Exercise 7: Scan Big Print Small](../exercises/ex7.md) (DUE Friday 11/22 end of day) **design and fabricate**

## Reference
- [MeshLab](https://www.meshlab.net/) - research grade / industrial strength mesh editing (Free and Open Source FOSS).
