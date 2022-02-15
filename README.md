# Ground Station Rotator Build
This page outlines the build process for a do-it-yourself rotator that comprises one of the hardware components of a groundstation for tracking objects in Low Earth Orbit. If you do not need to track orbital objects, you may consider going with a stationary design (e.g. geostationary weather satellites).

## Credit & Attribution
The rotator design is not a custom design, it follows the open-source plans provided by SATNOGS, specifically the SatNOGS Rotator v3 https://wiki.satnogs.org/SatNOGS_Rotator_v3. The main divergence, which will be discussed later, is the decision not to incorporate the SATNOGS circuit board and instead opting for a CNC board option, which drastically simplifies the electronics.

## Before Beginning
Right off the bat, this may seem like a large-scale project. In some ways, yes, it is...but that’s OK! I’ve done my best to try to break this project down into smaller pieces, i.e. rotator, antenna, final assembly, and getting telemetry data. The rotator alone cost ~300 USD. If in your situation, this feels like a little much for what you’re getting, consider constructing this with a group to split up costs. Trust me in that this is a perfect project for groups. This is not a 1-day project! Parts take time to procure, 3D printing takes time, and even the final assembly has a few pitfalls. You'll want to budget an ample amount of time and space to complete this project.

## Construction Order
Recommended Steps:
- Read through all the instructions
- Source the 3D parts first, these take the longest to fulfill & order. 
-- The Bill of Materials contains the quantity and parts you will need printed: https://gitlab.com/librespacefoundation/satnogs/satnogs-rotator/-/tree/master see `part-number-list.ods` and match it with the parts in `/rotator_parts`
- Purchase as many components as you can up front, you'll need them all eventually.
- Begin the Assemblies, and follow up with Control Hardware

## Reference Literature
Below is a list of URLs that were used in the construction of the antenna. This section will be updated as we progress through our project update installments. Spend some time browsing through these websites...you’ll be using them a lot as you build your groundstation. 
- Rotator design and instructions: https://wiki.satnogs.org/SatNOGS_Rotator_v3 
- Rotator repository (Contains the Bill of Materials or BOM as well as the CAD files necessary to 3D print components): https://gitlab.com/librespacefoundation/satnogs/satnogs-rotator 
- Controller board design and instructions: https://wiki.satnogs.org/SatNOGS_Arduino_Uno/CNC_Shield_Based_Rotator_Controller 
- Controller board repository (Files needed to flash the Arduino): https://gitlab.com/Quartapound/satnogs-rotator-firmware

## Design Choices
First, there are several options in the building of the rotator assembly. We recommend pursuing a build that incorporates stepper motors over dc motors as well as the CNC board over the SATNOGS custom circuit board for simplicity. The last decision is whether you wish to 3D print components yourself or send the CAD files to a company like Shapeways that will produce them for you. I utilized an Ender 3 3D printer. Another option is inquiring with a “Fab Lab” https://www.fablabs.io/labs/map, which typically have 3D printers, so all you would need to do is bring your CAD files with you and pay for cost of materials.

## Tools
I built my rotator assembly while keeping in mind to use as few exotic tools as possible. Inevitably, there are sometimes no substitutions for certain things, so I’ve listed what you’ll need below:
- Set of Metric hex wrenches
  - (If you end up purchasing a 3D printer, you might get these)
- Screwdriver set
- Voltmeter
  - (This is used to set the correct voltage on the stepper motor drivers)
- Wire Crimps
  - We’ll be splicing wires, so this allows us to connect wires to male pins on the CNC board. You specifically need ones that are for 2.54 pitch. We used these: https://www.amazon.com/gp/product/B06VWLW11G/ref=ppx_yo_dt_b_asin_titl e_o04_s00?ie=UTF8&psc=1
- A DC power supply
  - This allows you power the controller board with the necessary Voltage. We used this: https://www.amazon.com/gp/product/B08W293MJM/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1
- Soldering Iron
  - In addition to soldering wire connectors, this can be used to “heat press” nuts into some of the plastic 3D printed parts that came out slightly warped.
- Socket Wrench with metric 6 and 7
  - Makes life a bit easier with fastening bolts to nuts in some harder to reach areas (endstops)
- Wire strippers
  - You need ones that can strip 24-gauge wire that’s found in CAT 5 cable

## 3D Printing Notes
Here, I’ll highlight each 3D printed component, provide any overall notes for the part, and then speak to assembly of the rotator itself. I utilized Cura’s highest print settings and then modified them based on SATNOGs recommendations found in the reference material.

### Worm Wheel - Qty 2
- Notes: N/A

### Motor Mount - Qty 2
- Notes: Some post processing needed to removed excess ABS from the under hang of the circular cutout. Fan cooling may have helped mitigate this, however fixing this blemish took roughly 5 minutes per part.

### Worm gear - Qty 2

### Homing pin - Qty 2

### Shaft Collar - Qty 2

### Shaft Washer - Qty 2

### Endstop Mount - Qty 2

### Encoder Gear - Qty 2
- Notes: Some post processing needed to removed excess ABS from the under hang for the recess of the homing pin. Fan cooling may have helped mitigate this, but again, only about 5 minutes of trimming strands of ABS fixed the aesthetics of the print.

### Worm Mount - Qty 4

## Assembly Info

### Shaft Side Assemblies - Qty 4
- Reference: https://wiki.satnogs.org/File:A1031-1.png, https://wiki.satnogs.org/File:A1032-1.png.
- Notes: You will need to construct 2 of A1031-1 and 2 of A1032-1. 
  - For A1032-1, simply omit the encoder mount as this is for the DC motor design. The pictures below are the fully constructed shaft side assemblies (A1031-1), which is a combination of two different 3D printed parts. The deep groove bearing can be press fit into the side shaft easily. The 3D printed recessions for the nuts can be difficult to press fit, and I found success using a soldering iron to heat up the nut which remelt the plastic recess in order to achieve a snug fit. If you find that a nut has too loose a fitting, utilizing Loctite can help secure the nut in place.

### Worm Gear Assembly - Qty 2
- Reference: https://wiki.satnogs.org/File:A1010-1.png
- Notes: Following the measurements is key here, otherwise this component may be misaligned with the worm wheel and cause degradation of components.

### Shaft Collar, Encoder Mount, Motor Mount, and Worm Gear Mount Assemblies
- Shaft Collar Reference: https://wiki.satnogs.org/File:A1020-1.png
- Encoder Mount Reference: https://wiki.satnogs.org/File:A1033-1.png
- Motor Mount Reference: https://wiki.satnogs.org/File:A1070-1.png
- Worm Gear Reference: https://wiki.satnogs.org/File:A1011.png
- Notes: I did not include individual photos of these assemblies, as the references are extremely straight forward with attaching bolts and press-fitting nuts and deep groove ball bearings into the various recesses in the 3D prints.

### Initial Frame and Attaching Worm Gear Mount
- Reference: https://wiki.satnogs.org/File:A1001-3.png

### Axis Pipe Assembly
- Reference: https://wiki.satnogs.org/File:A1030.png

### Lower Axis Pipe Assembly into Frame
- Reference: https://wiki.satnogs.org/File:A1040.png
- Notes: This is your opportunity to lubricate the worm wheel and worm gear components
with silicone grease to provide better rotation of the components.

### Joining the two frame assemblies together
- Reference: https://wiki.satnogs.org/File:A1050-1.png

# Control Hardware

### Wiring
With the assembled rotator, we next move to wiring. Here, we can cut off the ends of the CAT5 cable, cut the wire to desired length (I used roughly 2-3 feet), and strip 2 individual 24 guage wires that reside in the CAT5 cable. One end we leave the exposed stripped wire to be soldered on the endstops, and the other end we use a pair of crimps to attach female pin connectors and insert the pin connectors into 2 row connectors. Now we can solder the wires to the endstops. Below is an image of the type of mechanical endstop used:A few things to note here. You can see the body of the endstop 3 pins which are labeled “C” for common, “NO” for normally open, and “NC” for normally closed. When soldering we are looking to feed individual wires through the C and NO pins. Normally open means that we want to send a signal back to the controller board when the switch is depressed. Normally closed works opposite to that. These are probably the most finnicky components of the project. Initially, I had issues with the endstops not depressing enough to send a signal. My fix to this to glue a small a small shim of aluminum to the back to the endstop arm to along for better actuation.

### Power Supply
The controller board runs on 12-36V DC, so I elected to use a variable DC power supply and set voltage to 12V and amperage to 1A. There are a variety of ways to connect power to the controller board. I chose to take a pair of the bullclips that typically come with a variable power supply, cut off the clip, and use twist style wire connectors to join additional cable. This additional cable was then stripped and can simply be inserted directly into the screwdriver cable clamps on the controller board.

### Flashing the Arduino
We now need to load the libraries and code necessary to allow the rotator to respond to commands. This is the point where we need to download the SATNOGs firmware. Download as a zip file and unzip it. Here, we open the Arduino IDE and we are opening up a file called “stepper_motor_controller.ino” in the stepper motor controller folder. Once open, connect your Arduino board to your computer with the USB cable. You can notice that on the bottom right corner of the IDE window a statement that reads “Arduino Uno on COMX”, where X is some number. In my case it was 3, but this may differ for you. We now need to include an additional library called AccelStepper. Under Sketch, select “Include Library”, and select “Manage Libaries”. Type in AccelStepper in the search bar and select install. Now, with the .ino file open, hit the checkmark icon on the top of the tool bar to verify. After verifying, hit the right arrow button to upload the firmware to the Arduino. After successfully uploading, we can now disconnect the Arduino from the computer. Assembling rotator controller From here, we can attach the stepper motor drivers to the CNC board, and from here, attach the CNC board on top of the Arduino. Reference: https://wiki.satnogs.org/images/a/a4/Assembled_CNC_Shield.png

### Crazy CNC board pin configurations and wiring everything else up
If you purchase the exact same CNC board as I included in a URL, the pin configuration numbers do not match the .ino file we just uploaded to the Arduino. In order to complete this project with minimal programming and we can naively connect the wires to the header pins. To do this, connect the azimuth (vertical pipe) stepper motor wiring to the X stepper motor driver and its associated endstop wiring to either Z+ or Z-. Next connect the elevation (horizontal pipe)stepper motor wiring to the Y stepper motor driver and its associated endstop wiring to either X+ or X-. Yes, I know it’s silly, but it’s probably an easier solution that drilling down in a header file and making the correction...
