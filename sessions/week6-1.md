# Week 6.1 - 3d Scanning, and Photogrammetry

## Agenda

- [Artist of the Day](#artist-of-the-day)
- Check in / get help on Small Object / Digital Double
- [3D Scanning](#3d-scanning)
  - Intro
  - [3D Scanning Hands-On](#3d-scanning-hands-on)
- [3D Scans in Rhino](#3d-scans-in-rhino)
- [Homework](#homework)

## Artist of the Day
<img src="media/white-snow.jpg" width=600>

Paul McCarthy
 
- [White Snow](https://henryart.org/exhibitions/paul-mccarthy)
- [Heigh-Ho, Heigh-Ho, I Mistrust Paul McCarthy's Snow White Sculptures (But I'm Not Saying Don't Go)](https://www.thestranger.com/visual-art/2016/03/23/23828114/heigh-ho-heigh-ho-i-mistrust-paul-mccarthys-snow-white-sculptures-but-im-not-saying-dont-go), The Stranger, Seattle, WA 2016.

## 3d Scanning

### Intro 
- Two main techniques: photogrammetry and LIDAR
  - Photogrammetry
  - LIDAR / 3d scanning (with laser)
    - Handheld scanner at Envision
- Examples of room scans (Twomey)
- Simple solution, phone/tablet apps.
  - Kiri, Polycam, Widar, etc. See **Other scanning apps** in [References](#references) below.
  - Other approaches?
- Strengths and limitations of various approaches. 

### 3d Scanning Hands-on
- Install Scaniverse [https://scaniverse.com/](https://scaniverse.com/)
  - [ten scanning tips for scaniverse](https://scaniverse.com/support)
- Take turns with your neighbor scanning portraits. 
- Use the tools in the app to crop the scan to an appropriate size/shape. 
- Export to a file format and import into Rhinio. 
  - Exports to Sketchfab, or to zip file. 
  - Sketchfab [https://sketchfab.com/](https://sketchfab.com/)

## 3D Scans in Rhino
Really just working with Meshes. Export from the scanning app as OBJ, PLY, or similar format.

### Fixing Meshes

**Mesh Repair**
Follow the detailed Scan, Cleanup, Remodel workflow described in the Rhino Whitepaper below [ScanCleanupRemodel.pdf](media/ScanCleanupRemodel.pdf)

Rhino Mesh Commands:
- **[MeshRepair](https://docs.mcneel.com/rhino/8/help/en-us/commands/meshrepair.htm)** contains many mesh repair tools in a single dialog.
- **[FillMeshHole](https://docs.mcneel.com/rhino/8/help/en-us/commands/fillmeshhole.htm#FillMeshHoles)** attempts to fill all open holes in the mesh. To make it watertight. 

### Editing Meshes
- **[ReduceMesh](https://docs.mcneel.com/rhino/8/help/en-us/commands/reducemesh.htm)** simplifies the mesh. Reduces number of vertices and faces. 
- Mesh Trim (**Mesh -> Edit Tools -> Trim**)
- Mesh Split (**Mesh -> Edit Tools -> Split**)
- Combine with other parts (solids, meshes, using extrude, boolean)

## Homework
- **HW** Finish [Exercise 6: Digital Double](exercises/ex6) (DUE Thursday 11/7 End of Day) **design and Fabricate**
- **HW** Submit your [Digital Sketchbook - Midterm Check In](https://canvas.ucsd.edu/courses/60628/assignments/856561) (DUE 11/12 end of day)

## References
- Other Scanning Apps
  - [Kiri Engine](https://www.kiriengine.app/) (iOS, Android and Web) three free exports per week
  - Polycam [https://poly.cam](https://poly.cam/) - does both photogrammetry and LIDAR (iOS and Android)
  - Widar [https://www.widar.io/](https://www.widar.io/) (iOS and Android) 5 scans per day
  - MagiScan [https://magiscan.app/](https://magiscan.app/) (iOS and Android)
  - Scandy Pro [https://www.scandy.co/apps/scandy-pro](https://www.scandy.co/apps/scandy-pro) - can use the front facing LIDAR
  - Objy.app [https://www.objy.app/](https://www.objy.app/) can use LIDAR (iOS only)
- Rhino Whitepaper on Scan, Cleanup, Remodel: [ScanCleanupRemodel.pdf](media/ScanCleanupRemodel.pdf)
  - [ScanCleanupRemodel.zip](media/ScanCleanupRemodel.zip)
- [Mesh Lab](https://www.meshlab.net/) research grade mesh software. Implements many state of the art softwares. 
