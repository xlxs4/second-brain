# FDM 3D printers 101
## Physical architecture
![](https://i.imgur.com/Fnvry04.png)

## How to print in any machine
![](https://i.imgur.com/JwAWIa1.png)
#### Creating the 3d model
In order to print a 3D object, we must first have a 3D design in our hands. By the use of a CAD software, such as:
* Solidworks
* Inventor
* Fusion 360
* FreeCAD
* Many more

we can create a 3D design or simply open and save one already created by another user. The latter can happen either by importing a *native file* into the software (i.e. for solidworks it would be a .sldprt file. This can only be opened by solidworks or any software that indicates it has the capability to do so) or a step (.stp) file, which can be opened by any CAD software.

In order for a 3D design to end up translated into an STL (.stl) file first. This will be done by using an export option in a CAD software and saving an STL file to use later.
#### STL files
[Why](https://3faktur.com/en/the-file-format-stl-and-its-importance-for-3d-printing/) use STL files? 

This file form was firstly used for a stereolithography (SLA) printing CAD software and has since been established for most printers.

It describes only the surface geometry of a three-dimensional object without any representation of color, texture or other common CAD model attributes. This is done by interpeting the surfaces as simple triangles (the parameters for these triangles can be tapered with when exporting an STL file to have more or less detail).

More or less it is used because it is easier for the makers of slicing softwares & printing apps and it is simple to use it.

To view an STL file, one cannot use the same CAD software that creates 3D models. But there are other available STL viewers and editors to download and use.
#### Slicing
Short-said, "slicing" means turning data from the STL file into a language that the printer can understand and translate into all its movements (g-code). The reason it's called "slicing" comes from the fact that a 3D print is created layer-by-layer, so what the slicer software actually does (among other things) is slicing the 3D model into thin layers.

![](https://i.imgur.com/Je85sRX.png)

During slicing is when one can tamper with the way the final print will look. This is done through a very large amount of parameters that you can change to your liking. Usually it is better to keep the most parameters to the default settings, but there are some basic ones that you will usually want or have to edit.

#### 

## Printing parameters 
### *(This is a long detailed read, only if you care about quality and printing duration)*
Printing parameters are usually split into the below categories:
* Printer settings
* Fillament settings
* Print settings

#### Printer settings
Depending on the printer features, the printer settings must be set so the g-code created by the slicer is made for the printer you will use. This means that there is no way the printer will try to do something it can't or shouldn't do, like trying to move beyond its boundaries or hit its nozzle on an object.

The most important settings are:
* Printing bed size: Defining the bed dimensions (width, depth & height) so the software knows the maximum physical size of a model the printer can handle.
* Number of extruders: Most printers have a single extruder, but there are some that have two. If you use 2 extruders, you must define their relative position by giving an offset value from their center. (Dual extruders are out of the scope of this guide)
* Nozzle diameter: Usually by default the nozzle diameter is 0.4mm, but it is possible to use other sizes. Note that changing the nozzle diameter setting has to be done simultaneously with changing the physical printer nozzle.

#### Fillament settings
These settings apply to the fillament material of the user. So, every time you try to change printing material you must change fillament settings (you can save and name settings to use them again). This may even be needed for the same material, but different brand.

Typical settings to change are:
* Color
* Diameter: The diameter of the fillament before it enders the extruder. This typically is 1.75mm.
* Extruder temperature: 
The temperature of the extruder must be set so that the fillament is properly melted in order to take the shape the printer gives it. The recommended value is written on the fillament package, but this is one of the most common settings to check/change when a print fails, because it is usually affected by environmental conditions.
* Bed temperature:
The bed temperature is set so the first layers of the print are still soft enough (but not melted) so that the print is stuck on the bed until the process finishes. This means the print will not get itself unstuck due to motion and ruin the process. The recommended value is written on the fillament package, but this is one of the most common settings to check/change when a print fails, because it is usually affected by environmental conditions. 

Both bed and extruder temperature can be set differently for the first and the rest layers.

#### Print settings
These settings can change mostly depending on the model geometry in order to properly support it. Typical settings to change are:

* Layer height: 
The layer height defines the thickness of each layer and accordingly the number of layers for the same model. This can affect the final look of the print, as thinner layers mean less ridges on the outside. But, the downside is the more layers, the longer the print.(the first layer can have different height, usually bigger, so it can stick more to the bed)
* Vertical and horizontal shells: 
The printed model has an outer surface and a filling pattern. The outer surface (or shell) can have multiple layers so it is smoother and more rigid. 
* Infill: 
The infill is the way the printer completes the volume inside the outer surfaces. You can edit the *density*, *pattern* and *angle* of infill.
Infill density defines what percentage of the volume is filled. High infill gives more rigid structures but substancially higher print times.
Infill pattern controls the shape the infill has inside this volume. It can be a simple 2d pattern like squares or honeycombs same for each layer, or it can be a 3d pattern like waves or 3d honeycombs. This setting and the infill angle can affect the directional properties of a print. For instance to be able to handle more force in a certain direction.
![](https://i.imgur.com/rS1wYGg.jpg)

* Print speed: 
This setting can be changed manually during print or set as a parameter during slicing. The print speed setting is modular. There can be a different setting for seperate layers, for support material, for skirts, brims, etc. So depending on your level of understanding print fails, you can change speed to correct specific problems.
* Support material: 
Creates supports for overhanging geometries. Changing support material settings can control the pattern of printing supports, how dense the layers are (meaning how easy it is to remove), etc.
![](https://i.imgur.com/KyKIv7u.png)

* Skirt:
Skirt is a perimeter around the print that doesn't have contact with it. It is used to make sure that the fillament is flowing correctly before beginning the print.
* Brim: 
Brim is a surface added around the first layer of the print in order to provide bigger stability for the next layers.
* Raft: 
It has the same functionality with the brim, but it extends to several layers and goes under the print. This means the first layer has only raft layers and the model layers begin after the raft has been made.
![](https://i.imgur.com/cxsM1tL.png)

## Common materials
PLA: 
The most common material. Cheaper, easier to print, biodegradable (debatable, though), hard and brittle. Indicative nozzle temp 190°C~205°C, indicative bed temp 55°C~65°C.

ABS:
Second most common material. Almost as cheap as PLA, a lot harder to print than PLA (sensitive to temperature changes; Can warp easily), acetone corrodes it, so it can be left in an acetone vat to be smoothed, hard and kind of flexible. Indicative nozzle temp 240°C~270°C, indicative bed temp 100°C~110°C.

---

Thanks to [@sspikeo.](https://gitlab.com/acubesat/structural/3d-printing/-/blob/main/README.md)