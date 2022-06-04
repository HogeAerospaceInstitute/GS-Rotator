# Custom Parts for Ground Station Rotator
This folder contains the STL mesh files for fabrication of parts necessary to build an azimuth/elevation rotator for tracking objects in low earth orbit. The designs are taken and potentially modified from the SatNOGS Rotator v3 release https://gitlab.com/librespacefoundation/satnogs/satnogs-rotator/ and follow the licensing guidelines set there-in.

## 3D Printing Notes
This guide is written for 3D printing of the included parts with a **PLA** filament extrusion machine. It has been successfully completed with a base model Ender 3 and a 0.4mm nozzle with appropriate layer heights. Later that nozzle was upgraded to 0.6mm and the layer heights adjusted. The parts to be printed comprise a working gearbox and mounts for transferring power from a stepper motor to an aluminum tube. 

### Tolerances
Many of the parts are designed to press fit bearings or hexagonal nuts. The hexagonal nuts can be set with acrylic glue (super glue) if the recess is too large, or eased in with heating from a soldering iron if the recess is too small. The press-fit bearings are generally forgiving if the tolerance is within -0.20mm, +0.05mm. Recesess too large on the bearing fits is not ideal, and should be avoided. A cheap set of calipers can help you troubleshoot any problems.

The biggest determining tolerance is the 40mm diameter set by the aluminum tube. The parts **C1020-1, C1021-1, C1022-3, C1040-2** all fit directly onto the tube, and thus must slightly be larger than 40mm. Because these parts are locked in place by set screws, it was found that 40.5mm was an acceptable inner diameter for the parts, yielding a tolerance of +0.5mm.

General rule of thumb:
- Exact size or +1% scale on bearing parts
- +1.5% scaling on aluminum tube mounted parts

### Materials
ABS and PETG are generally considered to be more durable than PLA but have different shrinkage rates upon cooling. The notes below are set for PLA, you may need to adjust as necessary.

### Layer Heights & Overhangs
0.4mm or smaller is recommended for layer heights, and any gear mating surfaces should be free of defects and blemishes. After construction and operation, the mating surfaces will wear down, deburring each other. However the surfaces should not abrade completely if the machine is to continue operating reliably.

The helical gear **C1062-1** is by far the hardest piece to print, and contains either overhangs or support structures. I was able to print it without supports after adjusting the layer height (0.15mm on 0.4mm nozzle), retraction, cooling fan, and temperature to prevent the edges from curling. If you have severe difficulty with this part, consider printing on its side with support and using a file to smooth.

### Changes from SatNOGS Specs
**C1040-2 C1042-2** have been modified from the original SatNOGS specification. **C1040-2** contains a tongue that triggers an infrared optical switch for the end stop. This tongue will likely need some sanding for smooth operation. **C1042-2** is the mount for the optical switch.

## Bill of Materials - What to Print
The same information is contained in *Parts List.ods*.

You can use https://wiki.satnogs.org/SatNOGS_Rotator_v3 as a reference for what the parts will look like, although two of the parts (**C1040, C1042**) have changed.

| Part Number | Description | Quantity | Comments |
|-------------| :--------- | :------: |----------|
| `C1010-3_bearing_mount` | Deep groove ball bearing 6008zz mount | 4 | 101% scaling, 0.4mm layer height |
| `C1011-3_bearing_cover` | End cap bearing cover for `C1010-3` | 4 | 101% scaling, match `C1010-3` |
| `C1020-1_shaft_gear` | Worm wheel axis gear 30T | 2 | 101.5% scaling, 0.4mm layer height |
| `C1021-1_shaft_collar` | Locking collar for `C1020-1` | 2 | 101.5% scaling, 0.4mm layer height, match `C1020` |
| `C1022-3_shaft_spacer` | Shaft spacer for `C1020-1` | 2 | 101.5% scaling, match `C1020` |
| `C1030-1_motor_mount` | Stepper motor mount | 2 | 101% scaling, must press fit motor but match screw holes on NEMA17 motor. Print with support |
| `C1040-2_locking_collar` | Collar & Endstop tongue | 2 | 101.5% scaling, print with support for tongue but will need filing |
| `C1042-2_endstop_mount` | Mount for optical endstop sensor | 2 | Match `C1010-3` properties |
| `C1061-5_worm_mount` | Bearing press fit for mounting worm gear | 2 | Layer height 0.4mm, 100% scale was fine |
| `C1061-6_worm_mount_mirror` | Mirror part to `C1061-5` | 2 | Match `C1061-5` |
| `C1062-1_worm_gear` | Worm gear | 2 | Print as cleanly as possible, no defects, 100% scale |
| `C1083-1_shaft_seal` | Shaft seal | 3 | Layer height 0.4mm, 101.5% scale |
| `C1084-1_screw_spacer` | Spacer for screws on case | 4 | Layer height 0.4mm |
