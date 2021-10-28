<img src="MiniHawkIso.png" width="400" />

# MiniHawk-VTOL <a name="head-brief"></a>
The MiniHawk VTOL is a 3D-Printed Tricopter/Fixed-wing hybrid aircraft, capable of Vertical Take-off and Landing. As with its predecessor, the [OrangeHawk VTOL](https://diydrones.com/profiles/blogs/the-orange-hawk-tricopter-flying-wing-vtol-uav), the MiniHawk is intended for R/C, FPV and UAV experimentation.  Mechanical artwork, build instructions, and configuration settings are provided in this repository.  

**Milestones**
| Date         | Event                         |
|--------------|-------------------------------|
| 15 Oct 2020  | Initial Release (v1.0)        |
| 2 Oct 2021   | Version 2 (v2.0, MH7_ prefix) |

Project Page at Hackaday: [HACKADAY.IO Page](https://hackaday.io/project/175286-minihawk-vtol)  

RCGroups VTOLs Thread: [RCGroups VTOLs Forum](https://www.rcgroups.com/forums/showthread.php?3986653-MiniHawk-VTOL-A-3D-Printed-Tricopter-Tilt-Rotor-Fixed-Wing-Plank)  

Accompanying Build Video Series: [YouTube Playlist](https://www.youtube.com/playlist?list=PLEMjH2uELUcYI_DS1zthgjE4Su79LeA_G)  

Betaflight VTOL Firmware Build: [vtol-motor-mix](https://github.com/StephenCarlson/betaflight/tree/vtol-motor-mix)  

# Table of Contents
1. [Introduction](#head-brief)  
  1.1 [Description](#head-description)  
  1.2 [Remarks / FAQs](#head-faqs)  
  1.3 [Metrics](#head-metrics)  
2. [Build Information](#build-brief)  
  2.1 [Recommended Tools](#build-tools)  
  2.2 [Components and Electronics](#build-components)  
  2.3 [Airframe Parts Listing](#build-airframeparts)  
3. [Build Steps](#buildseq-brief)  
  3.1 [Part 1 - Airframe Structures](#buildseq-part1)  
  3.2 [Part 2 - Linkages and Servos](#buildseq-part2)  
  3.3 [Part 3 - Electronics and Finishing](#buildseq-part3)  
4. [Flight Testing](#flight-brief)  
5. [3D Printing Guidelines](#3dprinting-brief)  
6. [ArduPlane](#arduplane-brief)  
  6.1 [R/C Controls Configuration](#arduplane-controlsconfig)  
  6.2 [Flight Controller Connections](#arduplane-connections)  
  6.3 [Parameters](#arduplane-parameters)  
  6.4 [Remarks](#arduplane-remarks)  
8. [License](#license-brief)  

## Description <a name="head-description"></a>
The MiniHawk is a 3D-Printed VTOL aircraft. It was designed with printability in mind, and is intended to provide the community with a common and accessible VTOL testbed for experimentation and tinkering. The vehicle uses three (3) brushless DC motors for propulsion, with the forward pair tilting for forward flight and yaw control, and the rear motor fixed for hover only. Four (4) servos are used to tilt the forward motors and to control the elevon control surfaces of the wing. The airframe is a "plank"-style wing with a center body containing avionics and battery, and internal conduits routing to the nacelles and servos. Twin vertical stabilizer fins provide mild directional stability.  

## Remarks / FAQs <a name="head-faqs"></a>
- As this is a totally 3D-printed airframe, the fully-finished vehicle is moderately heavy, which is a handicap, especially in the hovering mode of flight. As such, be gentle and cautious in adding any additional weight. For the recommended print settings with a 0.4mm nozzle, the airframe alone weights a bit over ~~300g,~~ and the all-up-weight of the finished vehicle is between ~~700g and 800g~~ 1000g to 1200g.  
- The parts used in this project are commonly available in the drone racing and R/C plane market(s). Standard 22xx- or 23xx-sized motors can be used, but the nacelle design dictates an absolute maximum motor bell diameter of 29mm. Previous motor size limitations are solved in the v2.0 prerelease. Dubro #181 and Dubro #190 are acceptable substitutions to the GPMQ3843, which is apperently discontinued in 2021.
- The aerodynamics and stability of the vehicle are still under analysis and subject to revision. The CFD poses/cases used for aerodynamics analysis are included for independent study.  
- As of Version 2 of this design, project files are prefixed with "MH7", as this is the 7th internal revision of the design of the MiniHawk VTOL. __(Version 2 is "MH7", some of the old MH5 parts are retained in the repo for the moment.)__ The "MH#" prefix is incidental and not to be confused with the MH airfoil series, of which the MH45 is used for this vehicle. Generally, "MiniHawk-VTOL" is the correct name for this design and any revisions to be released.
- This vehicle was designed in Autodesk Inventor Professional 2019. While compiled STLs are provided, the Solid Model and Assembly files for this vehicle are withheld at the time of this writing; contact me for inquires on obtaining a copy or further development. __(UPDATE: A STEP/STP versions of some parts such as the Hatch/Lid are included for community derivations. Otherwise, source files are retained but STLs are open-access as usual.)__
- There are some variants to each part, such as versions of the nose with and without NACA vents. The Winglet is available as "normal" or with an excavation for a GPS or other devices. The Hatch/Lid has a FPV Variant, which supports the Foxeer -Nano camera formfactor (15mm width) and has a 30.5mm grid for a video transmitter, such as the AKK Infinite DVR.

## Metrics <a name="head-metrics"></a>
| Description              | Value                     |
|--------------------------|---------------------------|
| Wing Span                | 800mm                     |
| Wing Area                | 15.6dm^2                  |
| Aspect Ratio             | 4.1                       |
| Airfoil (Root and Tip)   | [MH45][1]                 |
| Length                   | 520mm                     |
| Rotor Spacing            | 315mm Circle              |
| Lipoly Battery           | 4s, 1300-1500mAh (~160g)  |
| Motors (front)           | 22xx or 23xx 2300-2600kV  |
| Motor (rear)             | 22xx or 23xx ~2000kV      |
| Servos                   | HS-65HB/MG or eqv.        |
| Flight Controller (size) | 30.50mm to 16.0mm Grid    |
| Propellers (front)       | 5050 to ~5249             |
| Propeller (rear)         | 6030 to ~5249             |

[1]: <https://www.mh-aerotools.de/airfoils/mh45koo.htm> "MH45 Airfoil by Martin Hepperle"

# MiniHawk Build Parts List and Tools: <a name="build-brief"></a>
## Recommended Tools and Equipment <a name="build-tools"></a>
 - FDM/FFF 3D Printer with build volume greater than 23.1x210.7x330.0mm (Dimensions of largest part, which is Left/Right Wing. Adventurous builders might try printing on smaller printers by sectioning larger parts.)
 - Soldering Station and associated tools and materials
 - Handcrafting Tools
 - Adhesives: Cyanoacrylate Glue, Epoxy, Hot-Melt Adhesive Gun, Tape

## Components and Electronics: <a name="build-components"></a>
| Qty | Item Description                                     | Notes                                              |
|-----|------------------------------------------------------|----------------------------------------------------|
| 1   | Flight Controller (3 Motor, 4 Servo Outputs)         | mRo PixRacer Pro, Matek F4xx-WING or F7xx-WING     |
| -   | Pitot Probe, GPS, Telem. Radios, FPV Cam+VTx, etc    | Additional Essential Avionics                      |
| 1   | UBEC for servo power if not built into Flight Ctrlr. | Castle Creations 10 Amp Adjustable BEC             |
| 1   | R/C Receiver, 8+ Channel, SBUS or PPM Output         |                                                    |
| 3   | ESC (4s, 40A or better)                              | EMAX Formula Series 32Bit 45A ESC                  |
| 2   | 22xx or 23xx ~2500KV BLDC Motor (Out.Dia. < 29mm)    | T-Motor VELOX V2 2207 2550Kv (Note 1)              |
| 1   | 22xx or 23xx ~2000KV BLDC Motor                      | T-Motor VELOX V2 2306 1950Kv (Note 2)              |
| 1   | 4s1300 Lipoly (60C or better)                        | RDQ 14.8V 4S 1300mAh 100C                          |
| 1   | XT60 Pigtail or equiv.                               |                                                    |
| 2   | HS-65HB Servo (or equiv.)                            | Elevon Servos, see (Note 3).                       |
| 2   | HS-5065MG Servo (or equiv.)                          | Motor Tilt Servos, see (Note 4).                   |
| 6   | (opt) Du-Bro SKU#118 Small Nylon Hinge               | Elevon Reinforcement, see (Note 5).                |
| -   | M2 or M3 Mounting Hardware (Nuts, Bolts, Standoffs)  | For mounting Flight Controller, trays.             |
| 4   | 6-Inch Servo Extension Cable                         | (Note 6)                                           |
| 1   | Male-to-Male Servo Extension Cable                   | Flight Controller to Receiver PPM/SBUS connection. |
| 4   | 2-56 Link Clevis (Note 7)                            | Four (4) servo arm connections.                    |
| 2   | 2-56 Threaded Linkage Rod, Length>=52mm              | Elevon pushrods, L-bend at 45mm from threaded tip. |
| 2   | (opt) Du-Bro SKU#855 E/Z Links 0.72 (2-56) Clip      | For securing L-Bends, can replace with Z-bend.     |
| 2   | 1/16-inch 2-56 Ball Link and Coupler Pair            | Dubro #181 or Dubro #190, see (Note 8).            |
| 2   | 2-56 Fully-Threaded Rod, Length=60mm                 | End1=(Link 2-56 Clevis), End2=(2-56 Ball Coupler)  |
| 2   | 2-56 Smooth Rod, Length=24mm                         | (Note 9)                                           |
| 2   | (opt) WS2812 5050 SMD (or equiv. Addressable LED)    | Soldered with magnet wire, mounted in wingtips.    |
| -   | M4 and M5 Prop Nuts                                  | Replace default prop nuts if needed                |
| 1   | 50xx Propeller, Clockwise Rotation                   | Left/Port-side Propeller, 5-inch                   |
| 1   | 50xx Propeller, Counterclockwise Rotation            | Right/Starboard-side Propeller, 5-inch             |
| 1   | 50xx or 60xx Propeller, Counterclockwise Rotation    | Tail Propeller, 5- or 6-inch                       |
| 1   | Velcro Battery Strap                                 |                                                    |
| 1   | (opt) Battery Voltage Monitor / Alarm Buzzer         | For Flight Controller if not included.             |

> Note 1: Front motors must be no larger than OutsideDiameter=29mm, able to produce between 500g to 800g static thrust (@full-throttle), and pitch speed of ~20m/s (@half-throttle) with 5-inch prop.  
> Note 2: Tail motor may be up to OutsideDiameter=30mm or more, able to produce between 700g to 1000g static thrust (@full-throttle) with up to a 6-inch prop.  
> Note 3: Servo bays are designed for up to 26mm wide servos, 17.5mm from bottom of mounting tabs to bottom of servo, 32mm from top of output shaft to bottom of servo, 12mm thick. Should fit most "Sub-Micro" Servos.  
> Note 4: Same pocket dimensions as above, but these are going to be fantastically abused and must be fairly tough. Or just count on stripping your non-metal-gear servos a lot.  
> Note 5: Can be omitted, but 3D-printed living-hinge on elevons will eventually fail, mend appropriately. SKU#118 is 6 per package, SKU#119 for 15/pkg.  
> Note 6: Alternatively, cut the servo cables and solder in-line extensions for the cables to reach to the flight controller, plus some slack.  
> Note 7: The clevises and rods can be purchased as a set, such as Du-Bro SKU#185, which is a set of 5 rods with clevises already attached.  
> Note 8: **CRITICAL!!!** The Ball Link thread must be "116", 1/16-inch, 62.5mil, or 1.59mm. The more popular variant of this type of part has a 2-56 thread size ball, which is too big for the nacelle motor tilt attachment. Note that this is the ball-link thread size; the coupler that captures the ball is 2-56 threaded. This ball-link set attaches from the motor tilt servo linkage to the motor tilt mount, which holds the front left/right motor. The previous suggestion for this part was GreatPlanes GPMQ3843, but it has been discontinued.
> Note 9: Diameter=[1.83mm to 1.87mm], formed from spare pieces of 2-56 Servo Pushrod. Use non-threaded smooth rod, roughen/knurl only one end slightly for press-fitting to nacelle.  

## Airframe Parts: <a name="build-airframeparts"></a>
| Part                     | Source File                                                                        |
|--------------------------|------------------------------------------------------------------------------------|
| Fuselage Nose            | [MH7_Nose.stl](/stl-SourceFiles/MH7_Nose.stl)                                      |
| Empennage Left Half      | [MH7_Empennage.stl](/stl-SourceFiles/MH7_Empennage.stl)                            |
| Empennage Right Half     | [MH7_Empennage.stl](/stl-SourceFiles/MH7_Empennage.stl) *Mirrored*                 |
| Lid Left Half            | [MH7_Hatch.stl](/stl-SourceFiles/MH7_Hatch.stl)                                    |
| Lid Right Half           | [MH7_Hatch.stl](/stl-SourceFiles/MH7_Hatch.stl) *Mirrored*                         |
| Fin Lower (2)            | [MH7_FinLeft_Lower.stl](/stl-SourceFiles/MH7_FinLeft_Lower.stl) *One is Mirrored*  |
| Fin Upper (2)            | [MH7_FinLeft_Upper.stl](/stl-SourceFiles/MH7_FinLeft_Upper.stl) *One is Mirrored*  |
| Left Wing                | [MH7_WingLeft.stl](/stl-SourceFiles/MH7_WingLeft.stl)                              |
| Right Wing               | [MH7_WingLeft.stl](/stl-SourceFiles/MH7_WingLeft.stl) *Mirrored*                   |
| Elevon Control Horn (2)  | [MH7_ControlHorn.stl](/stl-SourceFiles/MH7_ControlHorn.stl)                        |
| Left Nacelle Right Half  | [MH7_Nacelle_SideA.stl](/stl-SourceFiles/MH7_Nacelle_SideA.stl)                    |
| Left Nacelle Left Half   | [MH7_Nacelle_SideB.stl](/stl-SourceFiles/MH7_Nacelle_SideB.stl)                    |
| Left Motor Mount         | [MH7_TiltMount.stl](/stl-SourceFiles/MH7_TiltMount.stl)                            |
| Right Nacelle Left Half  | [MH7_Nacelle_SideA.stl](/stl-SourceFiles/MH7_Nacelle_SideA.stl) *Mirrored*         |
| Right Nacelle Right Half | [MH7_Nacelle_SideB.stl](/stl-SourceFiles/MH7_Nacelle_SideB.stl) *Mirrored*         |
| Right Motor Mount        | [MH7_TiltMount.stl](/stl-SourceFiles/MH7_TiltMount.stl) *Mirrored*                 |
| Flight Controller Tray   | [MH7_ControllerTray.stl](/stl-SourceFiles/MH7_ControllerTray2.stl)                 |
| Battery Tray             | [MH7_BatteryTray.stl](/stl-SourceFiles/MH7_BatteryTray.stl)                        |

# Build Sequence <a name="buildseq-brief"></a>
The following instructions assume that a full set of airframe parts have been printed, as enumerated above.

[Figure-1]: </doc-Documentation/Figure-1.png> "Figure 1 - Hinge Pin Clearance" 
[Figure-2]: </doc-Documentation/Figure-2.png> "Figure 2 - Elevon Movement Cuts"
[Figure-3]: </doc-Documentation/Figure-3.png> "Figure 3 - Hatch/Lid Bonding"
[Figure-4]: </doc-Documentation/Figure-4.png> "Figure 4 - Empennage Halves Bonding"
[Figure-5]: </doc-Documentation/Figure-5.png> "Figure 5 - Elevon Control Horn Install"
[Figure-6]: </doc-Documentation/Figure-6.png> "Figure 6 - Empennage/Tail Attachment"
[Figure-7]: </doc-Documentation/Figure-7.png> "Figure 7 - Nacelle Halves Bonding"
[Figure-8]: </doc-Documentation/Figure-8.png> "Figure 8 - Wing Attachment"
[Figure-9]: </doc-Documentation/Figure-9.png> "Figure 9 - Nacelle Pocket Finishing"
[Figure-10]: </doc-Documentation/Figure-10.png> "Figure 10 - Shaft and Bolt Hole Reaming"
[Figure-11]: </doc-Documentation/Figure-11.png> "Figure 11 - Nacelle Attachment"
[Figure-12]: </doc-Documentation/Figure-12.png> "Figure 12 - Vertical Stabilizer Attachment"
[Figure-13]: </doc-Documentation/Figure-13.png> "Figure 13 - Strake Attachment"
[Figure-14]: </doc-Documentation/Figure-14.png> "Figure 14 - Linkages and Movements"
[Figure-15]: </doc-Documentation/Figure-15.png> "Figure 15 - Propeller Rotation Directions"
[Figure-16]: </doc-Documentation/Figure-16.png> "Figure 16 - Center of Mass"

## Part 1 - Airframe Structures and Motor Mount/Tilt Attachment <a name="buildseq-part1"></a>
1. Clean all 3D-Printed parts, remove all brim/support material. For each wing, carefully carve away any stringing or over-extrusion in the hinge reinforcement wells such that the hinge pin will fit. [Figure-1] Carefully cut the elevons free if needed (**WARNING!** Only cut slots on either end to allow for surface deflection, DO NOT cut the entire elevon out), and gently exercise each surface up and down until the living hinge is established. [Figure-2] Bond the Canopy/Hatch-Lid pieces together using Thin/Medium Cyanoacrylate or Epoxy, and set aside to cure. [Figure-3]
2. Bond the Empennage Halves together. Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. Set aside to cure. [Figure-4]
3. Bond the Control Horn pieces (2) into each Elevon (Left Wing and Right Wing). Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. The Control Horn should be fairly flush on the Elevon Top Surface, approximately 0.5mm extending above the surface. Fit should be tight; carefully carve away any burrs or over-extrusion from the slot in the elevon if needed. [Figure-5]
4. Glue the Du-Bro Nylon Mini-Hinge pieces (3 per wing, Du-Bro SKU#118) into the recesses along each elevon hinge. Hot-Melt-Adhesive, CA, or Epoxy should work.
5. Lightly sand the bonded empennage/tail interface surface until smooth and planar/flush. Test-fit to the Fuselage/Nose to confirm a proper flush joint, and then bond to the Fuselage/Nose using Thin or Medium Cyanoacrylate, or Epoxy. Set aside to cure. [Figure-6]
6. Bond the Nacelle Pair Halves together. Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. Proper alignment is critical, be careful and precise. Set aside to cure. [Figure-7]
7. Lightly sand both wing root interface surfaces on the completed fuselage/body until flush and smooth. Test-fit both wings to each respective surface to confirm a proper flush joint. Bond either the left or right wing to the fuselage (not recommended to attach both at once) using Epoxy. (Cyanoacrylate may not have the strength needed.) Set aside to cure. When the first wing is cured, bond the second wing and set aside to cure. [Figure-8]
8. Test-fit each Motor Mount (Tilt Mount/Pod) with its respective completed nacelle. Sand or trim as needed such that the Motor Mount is able to tilt fully flush forward, and able to tilt up past 90 degrees of rotation. [Figure-9]
9. For each Nacelle with its respective Motor Mount aligned and present, Ream (Drill to size) using a 1.58mm (1/16 Inch, 62.5mil) drill bit. (Should be 85% to 90% of diameter of hinge rod to be fitted. Hinge Rod diameter is 1.84mm or 72mil for this case.) Keep the Motor Mount and Nacelle together. Adapt a section of hinge rod to be used as a final precision reaming tool by sharpening the tip using a grinder or emery wheel. Use this improvised reaming tool to ream the hole in each nacelle-mount pair to the final diameter of 1.84mm (72mil). [Figure-10]
10. Remove each Motor Mount from its respective Nacelle and ream only the Motor Mount hole to the next higher drill bit size, not to exceed 107% of diameter of the the hinge rod. Too large will allow for excessive play and possible rattling; too small will result in binding. 1.95mm (77mil, 5/64 Inch) is acceptable for hinge rod diameter of 1.84mm.
11. Cut the hinge rod pieces, not to exceed 24mm length. Roughen/knurl one or both ends if desired. Press-fit each hinge rod to each Nacelle through the respective Motor Mount. Verify that each Motor Mount can rotate freely and with minimal play in the hinge.
12. For each Motor Mount, ream the Motor Mount linkage mount hole to 1.19mm (3/64 Inch, 47mil). This should be about 80% of the major diameter of the threaded ball link to be mounted. (Great Planes Threaded Ball Link Set 1/16", GPMQ3843; ball-link is 1.50mm major diameter.) Mount the threaded ball-link to the linkage mount hole. The Motor Mount can sustain up to 3.3mm threaded bolt depth, verify that the bolt does not extend too far into the well, such that it will not make contact with the motor.
13. Bond each Nacelle to its respective wing; note that the ball-link should align with the respective servo linkage slot/well. Epoxy is recommended, as this is a significant load-bearing structure. Verify alignment and tweak/tune while the glue cures. [Figure-11]
14. Bond both vertical fins to the wing(s). [Figure-12] Medium Cyanoacrylate should be sufficient. Bond the Rear Strakes to the bottom of the wing(s) and bottom edge of the vertical fins. [Figure-13]

## Part 2 - Linkages and Component Mounting <a name="buildseq-part2"></a>
1. Mount the front two motors in their respective Motor Mounts. The motor leads may have heatshrink that may interfere or bind the wires; rework this if needed. Mount the motors using the M2 threaded bolt kit that should be included with each motor. Be careful not to have any mounting bolt over-extend into the motor armature/stator. Verify that each motor turns freely and is well secured. Route the wires through the wing and into the main bay, and test the extension-retraction behavior of the wires as the motor mount pitches between forward and hover tilt positions. For each motor, attach the propeller hub hardware kit that should be included with each, such that it can drive a standard 5-Inch propeller.
2. The Rear motor should mount to the tail using M3 threaded bolts that were included with the motor. Route the motors wires through either wire duct channel to the main bay as desired. Verify that the motor rotates freely and is well secured. Attach the propeller hub hardware kit that should be included with the motor, such that it can drive a standard 5-Inch propeller.
3. The Motor Mount Tilt servos should be tested and centered on a standard RC PWM signal, visiting 1000us, 1500us, and 2000us pulse-widths. Attach a servo arm with a 19.3mm (0.76 Inch) hole-to-center spacing. This value is critical, as the linkage behavior of the tilting front motor mounts cannot be easily modified and any length short of this will result in the motor tilt not reaching the needed angle for hover and anti-torque (yaw) control. An arm any longer than this will not fit in the linkage well/slot. With whatever arm fitted as similar to 19.3mm as possible, test fit the servo into the servo well and verify that between 1000us and 2000us pulse widths, the arm comfortably retracts into the well/slot, and fully sweeps about 90 to 95 degrees from that point. Verify the best servo arm spline position and bolt/secure the arm in place. [Figure-14]
4. For each of the Elevon servos, repeat the same procedure as above, but with a servo arm approximately 9.5mm hole-to-center (3/8 Inch). This length can be a bit longer or shorter, the effect is increasing or decreasing elevon control throw. For servos that have an odd-number spline tooth count (such as the Hitec HS-65HB's B1 spline with 25 teeth), to get the most well-centered and symmetric solution, center the servo on a 1500us pulse width and alternate attaching a 4-arm output horn between each 90-degree position to find the most orthogonal/centered position, and then cut off the 3 unneeded arms.
5. Verify that the Link Clevises that attach to the servo arms are able to couple and rotate freely. Reaming each servo arm may be necessary, a value of 1.59mm (1/16 Inch, 62mil) is common.
6. Route the servo wires through the conduit tunnels in the wing to the main bay. ~~Be advised that this is somewhat irreversible, depending on the quality of the 3D print, any glue protrusions in the tunnel, and weaving/tangling of the pigtails after routing.~~ **No longer an issue with Version 2** The pins in the 3-pin header on the pigtail can be carefully removed to allow the wires to pass back out if needed later. Assuming all servos have a 6-inch (~150mm) pigtail, the Elevon servos will have some slack, but the Tilt servos will arrive just barely at the main bay. Servo Extensions can be added, or the servo pigtail can be extended with a section of 3-wire servo lead/cable, or the 3-pin servo connectors can be discarded in favor of direct soldering later if desired.
7. With servo harnessing finished in one form or another, bond the servos to the airframe using Hot-Melt-Adhesive. Note that the airframe may exhibit deformation or melting at the bonding locations, depending on print material used. Verify that the servos can produce full torque without becoming detached from the airframe. Also note that alternatives may be explored in servo mounting, such as double-sided adhesive tape, but it is not advised to use cyanoacrylate or epoxy.
8. Form the elevon control rods by creating an L-bend 45mm from the threaded tip of the pair of 2-56 link rods used. Test fit the retaining Du-Bro E/Z Links 0.72 (2-56) Retainer Clip for each bend, and modify the bend as needed and cut flush. Alternatively, a traditional Z-bend can be formed to dismiss the Retain Clips as a requirement. For each Elevon, attach its control rod to the elevon control horn, and attach the clevis to the corresponding servo arm. Detach, turn the clevis, and reattach as needed until the elevon is flush while the servo is centered on 1500us.
9. Cut two (2) 60mm long pieces from a fully-threaded 2-56 rod to form the tilt control rod pair. (DO NOT L-bend or Z-bend these rods.) Soften the cut ends with a grinder or emery wheel such that they will easily thread into the Nylon Ball-Link couplers. Thread on the ball-link couplers and link clevises, and attach each to its respective servo arm or ball-link head. Detach-turn-reattach as needed, such at the servo approaches as close to top-dead-centre (arm retracted into well/slot) as possible, without binding or interference, while the tilting motor mount is firmly forward and pressed against the nacelle. As noted earlier, the clevis should attach to the highest hole in the servo arm, at 19.3mm arm distance. It may be required to bend this rod slightly to allow for the servo arm to fully retract without the clevis impacting the arm. If the servo is straining excessively when the motor mount is retracted, adjust accordingly. **WARNING!** If the servo is allowed to strain with the clevis binding against the servo arm, the servo will likely fail via burnt-out H-bridge driver or motor.
10. The above steps assumed that the servos were powered and commanded during final installation, but for completeness, this step verifies that the servos are able to actuate, and are not being stressed. For each servo, visit 1000us-1500us-2000us and observe deflection on Elevons or Motor Mount and verify that there is no excessive binding or stress. For each motor mount, simulate the load exhibited during forward flight by gently pulling on the motor in the forward direction (about 300 grams force), while the servo is actively commanded to retain the forward condition, and verify that the motor is retained/held in the forward flight position with minimal creepage. Elevons should actuate the full range with light loading on the control surface.

## Part 3 - Electronics and Final Configuration <a name="buildseq-part3"></a>
1. Solder the Flight Controller as desired. This usually means soldering pin headers to attach the 3-pin servo connectors from the servos and ESCs. Solder a battery connection lead (XT60 or as desired). Power the Flight Controller and verify that it is booting and communicating correctly. Default (likely multicopter) firmware will be fine for the next few steps; be advised that servos **SHOULD NOT** be connected to the flight controller until the flight controller outputs are configured.
2. Bond the Battery and Flight Controller Trays into the main bay. This can be accomplished using M2 or M3 hardware and ample Hot-Melt-Adhesive and some reaming if necessary. The Battery Tray can be permanently mounted, but retain some ability to remove the Flight Controller Tray, as mounting/removing the flight controller requires access to the bottom of that tray. 
3. Solder the BLDC Motor leads to each respective ESC, or use bullet-connectors or otherwise as desired. Solder the ESC power connections directly to the Flight Controller's Power-Distribution region, or to intermediate connections as desired. Power on the Flight Controller carefully, such as with a "Smoke Stopper" or a current-limited power supply, and verify that the power system is wired correctly. Program the ESCs for proper rotation direction: Port/Left Motor is Clockwise (CW), Starboard/Right Motor is Counterclockwise (CCW). (If using a BLHeli Passthru mode to program ESCs, the ESCs may be connected to any output(s) on the flight controller.) The Rear Motor may technically be either direction, but I **strongly** recommend Counterclockwise (CCW). This is a self-tightening configuration, so it is unlikely to unscrew itself in normal operation. This also allows for most non-multicopter propeller options (most propellers are CCW), and to force a consistent tradition that allows for future sharing of PID profiles and control schemes symmetrically. [Figure-15]
 > A brief note on prop rotation directions: The reason for the front motors having the Clockwise and Counterclockwise directions as stated is such that when the vehicle is flying in forward flight, and then immediately commanded to hover, the advancing blade(s) are placed as far abeam (toward the wingtip) as possible, while the retreating blade is closer to the main body. This should allow for better roll control through the transition, and by placing the effective centeres of lift for each rotor slightly wider in this condition, any PID control effort is more likely to remain bounded and slightly attenuated by the slightly longer moment-arm. This also follows the typical configuration for quadrotors, which also have the front advancing blades placed on the outside of the arc.
4. At this point, configure the Flight Controller with any specific firmware or settings relevant to controlling a Tricopter VTOL Fixed-Wing vehicle, if not already. Attach the servo and ESC headers to their required pins. Install the R/C receiver and connect to the Flight Controller as required. Mount the Flight Controller to its tray, and secure the tray inside the main bay. Power the vehicle and verify Flight Controller orientation is correct, servos are properly commanded, and that control surface efforts are in the correct direction. Reverse and trim servo outputs as necessary in the Flight Controller configurator.
> Note for the Matek F722-WING: Configuration and assignments are documented in *Betaflight Settings* below.
5. (Optional) WS2812 LEDs may be mounted in each wingtip, provided each is a SMD5050 or smaller package, with wires directly soldered to the package pads, and then mounted in the light well on each tip.
6. Stow the ESCs to the side-walls of the main bay using tape or double-sided adhesive pads. Stow any excess wires, and generally clean up the inside of the main bay. Secure the battery using Velcro straps, Tape, or other measures.
7. Mount the propellers to their respective motors. For initial flight testing, it is recommended to use the same propeller for all three motors, a 5030 to 5040 three-blade prop is recommended. Later on, the rear propeller may be swapped with a 5535 or 6030 three-blade, and the front two may be swapped with a 5050 or similar.
8. ~~The Center-of-Mass for the aircraft is intended to be at 165mm back from the tip of the nose, or 40mm back from the leading edge of the wing. This is exactly along the middle pair of mounting holes for the Battery Tray. This is an initial value, and the Center-of-Mass may be shifted back by around 8mm to 10mm from this point, but with increasing risk to stability.~~ **No, that was really bad, and is totally wrong! The aircraft will NOT fly with the CG aft of ~32mm. In Version 2, the Center-of-Mass should be between 26mm and 30mm back from the wing leading edge, and typically I can get it exactly on 28mm using the Weight-and-Balance Stand and a digital scale, STLs included in the repo. See the Issue #12 comment here: [https://github.com/StephenCarlson/MiniHawk-VTOL/issues/12#issuecomment-828814266](https://github.com/StephenCarlson/MiniHawk-VTOL/issues/12#issuecomment-828814266)** As this vehicle is both a fixed-wing and multicopter, the Center-of-Mass stated here is for the fixed-wing condition, and any measurement of Center-of-Mass should be performed with the motors tilted into the forward-flight condition, propellers attached, and the lid secured. Shift the battery fore or aft to achieve proper balance, or add ballast if merited. [Figure-16]
9. Perform any other measures necessary to get the vehicle ready for flight. Decals, paint, or heat-activated covering are possibilities. Vehicle mass should come to an All-Up-Weight around ~~700 grams to 800 grams, with the 3D-printed airframe alone measuring around 300 grams.~~

# Flight Testing <a name="flight-brief"></a>
The clean-sheet approach to tuning this vehicle for flight roughly follows this sequence of steps:
1. Discover the hovering-flight PIDs. This can be done using a test-stand setup and axis-isolation of roll, pitch and yaw. Gain Scheduling for hover-to-forward-flight and reverse transitions can also be performed with a pitch-isolated configuration, but relevance diminishes for angles approaching forward-flight without equivalent relative wind generation. (ArduPlane does this calculation intrinsicly, implementing VTOL to other flight-stacks may require developing the Gain Schedule Table.)
2. Continue PID tuning until free hovering hops and static hovering are demonstrated. Tune the position-hold behaviors and demonstrate autonomous Return-to-Land functionality. Demonstrate robust upset recovery and stability. Tune the weathervane behavior until satisfactory.
3. Confirm Weight-and-Balance of the aircraft (26mm to 30mm from the wing leading edge). Verify that pitch is statically stable at cruising speed (19 m/s). Also verify that the aircraft is directionally stable (static weathervaning). Trim the pitch on the elevons to produce a level glide at 19 m/s. 
4. Confirm that the control surface deflections are correct for both pilot inputs and autopilot stabilization responses to aircraft movement and pose. Reduce forward-flight PIDs substantially if merited. Hand-launch the aircraft into forward-flight and confirm that it is controllable and stable. Beware that if control throws are too large, the controls can be very responsive and fast. Exit from fixed-wing flight to hover and land safely.
5. If the aircraft is still intact and functional from the previous step, perform AUTOTUNE or equivalent to arrive at sensible PIDs for forward-flight. Tune the waypoint following behaviors and demonstrate consistent navigation. If applicable, demonstrate autonomous landing starting from fixed-wing flight.
6. Hover-climb to at least 50 meters and attempt forward-flight VTOL transitions. Tune the transition behavior until the vehicle consistently enters forward-flight. Transitions should look the same for both human-piloted and autonomous cases.
> The vehicle is designed to hover with a nose-high attitude (positive Angle-of-Attack). The reason for this is so that as the nose is dropped to level, the thrust vector brings the vehicle to an initial forward drift. Having established a forward trajectory, the motors are tilted to the 50/50 intermediate point and the vehicle is allowed to accelerate. The motors are then dropped to full forward-flight position.
8. Demonstrate full autonomous missions from launch to landing with forward- and reverse-transition behaviors.

# 3D Printing Guidelines <a name="3dprinting-brief"></a>
Unlike other 3D-printed R/C aircraft, the MiniHawk does not have any internal structures explicitly specified, such as ribs or stringers; only the outer-mold-line of the aircraft and the bays, wiring conduits, and mounting points are defined. The internal structure is yielded to whatever infill pattern is selected in the slicing software used to convert the volume definition for 3D-Printing. The internal structures may be explicitly defined in a future revision, but otherwise it is up to the builder to define the infill pattern used. The following sections provide recommended settings for each airframe part set (matching the settings in the 3MF files).

| Parameter                 | Left and Right Wings           | Nose                    | Empennage               | Hatch/Lid               | Nacelles                  | Motor Tilt Mounts         |
|---------------------------|--------------------------------|-------------------------|-------------------------|-------------------------|---------------------------|---------------------------|
| LayerHeight               | 0.2mm                          | 0.2mm                   | 0.2mm                   | 0.2mm                   | 0.2mm                     | 0.2mm                     |
| WallThickness             | 0.4mm                          | 0.4mm                   | 0.4mm                   | 0.4mm                   | 0.8mm                     | 0.8mm                     |
| TopThickness              | 0.2mm                          | 0.2mm                   | 0.2mm                   | 0.2mm                   | 0.6mm                     | 0.6mm                     |
| BottomThickness           | 0.2mm                          | 0.2mm                   | 0.2mm                   | 0.2mm                   | 0.6mm                     | 0.6mm                     |
| TopBottomMainPattern      | Lines                          | Concentric              | Lines                   | Lines                   | Lines                     | Lines                     |
| InitialBottomLayerPattern | Concentric                     | Concentric              | Concentric              | Concentric              | Lines                     | Lines                     |
| FillGapsBetweenWalls      | Nowhere                        | Nowhere                 | Nowhere                 | Nowhere                 | Everywhere                | Everywhere                |
| Z-SeamAlignment           | UserSpecified (Note 1)         | SharpestCorner,HideSeam | SharpestCorner,HideSeam | SharpestCorner,HideSeam | SharpestCorner,ExposeSeam | SharpestCorner,ExposeSeam |
| InfillDensity             | 5.00%                          | 10.00%                  | 10.00%                  | 10.00%                  | 20.00%                    | 30.00%                    |
| InfillPattern             | Cubic                          | Cubic                   | Cubic                   | Cubic                   | Cubic                     | Cubic                     |
| InfillLineDirections      | 90deg                          | 0deg                    | 0deg (Note 2)           | 90deg                   | 0deg                      | 0deg                      |
| GenerateSupport           | Nowhere                        | Nowhere                 | Nowhere                 | Nowhere                 | Yes                       | Nowhere                   |
| SupportPlacement          |                                |                         |                         |                         | TouchingBuildPlate        |                           |
| SupportOverhangAngle      |                                |                         |                         |                         | 70deg                     |                           |
> Note 1: Forced to occur on trailing edge of wing.  
> Note 2: Is slightly offset in X-direction for best structure.  

For the MH7_ControlHornSet and MH7_TraySet, print 100% Solid or as desired. These pieces may be laser-cut if possible.


# ArduPlane Settings <a name="arduplane-brief"></a>
While the MiniHawk-VTOL initially was developed using the BetaFlight avionics ecosystem, ArduPilot is the reccomended ecosystem for the current design. This text section replaces the original Betaflight setup instructions which existed in this section prior to v2.0.0. The old Betaflight setup instructions can be found in the README.md file revision history.

## R/C Controller Configuration (Mode 2 Controller) <a name="arduplane-controlsconfig"></a>
| R/C Channel | Description         | 1000us         | 1500us     | 2000us                  | Notes                                                          |
|-------------|---------------------|----------------|------------|-------------------------|----------------------------------------------------------------|
| CH 1        | Roll                | Roll Left      | Centered   | Roll Right              |                                                                |
| CH 2        | Pitch               | Nose Up        | Neutral    | Nose Down               |                                                                |
| CH 3        | Throttle/Collective | Idle           | 50% Thrust | 100% Thrust             | Be careful switching between QSTABILIZE and QLOITER/QHOVER     |
| CH 4        | Rudder              | Yaw Left       | Neutral    | Yaw Right               |                                                                |
| CH 5        | Flight Mode Select  | FBWA           | QSTABILIZE | AUTO/RTL/AUTOTUNE       | 3-Position Switch, 2000us is formed by mixing a 2nd R/C switch |
| CH 6        | MANUAL Override     | Disabled       | ---        | MANUAL Mode ACTIVE!     | RC6_OPTION=51, useful for hand-launching into forward-flight   |
| CH 7        | Arming Switch       | Disabled       | ---        | ARMED!                  | RC7_OPTION=41, ArduPilot Arming/Disarming Switch               |
| CH 8        | Momentary Switch    | Disabled       | ---        | OSD, Inverted Mode, etc | OSD Screen Cycling, Inverted (RC8_OPTION=43), other misc uses  |

Note that MANUAL Mode is a real handful, and should only be used rarely. It is included above as a kind of "cheat" to force the ArduPlane VTOL state-machine to stay in Forward-Flight when Arming, such as when you want to hand-launch the aircraft to skip the VTOL hover and forward transition. First set the aircraft to FBWA using the CH 5 Flight Mode Select Switch, and then turn on the MANUAL Override switch only for a moment and then back to disabled (Flight mode returns to FBWA as set by the Flight Mode switch). Otherwise, if you only select FBWA and then arm, the aircraft immediately reverts to the ArduPlane VTOL forward transition behavior with all three motors spinning in the hover condition.

## Flight Controller Connections <a name="arduplane-connections"></a>
The following table works on the mRobotics PixRacer Pro. This should be adapted to whatever ArduPlane-compatible flight controller is otherwise used.

| Pin # | Control Endpoint    |
|-------|---------------------|
| S1    | Right Motor ESC     |
| S2    | Left Motor ESC      |
| S3    | NO CONNECTION (BEC) |
| S4    | Rear/Tail Motor ESC |
| S5    | Left Tilt Servo     |
| S6    | Right Tilt Servo    |
| S7    | Left Elevon Servo   |
| S8    | Right Elevon Servo  |

## ArduPlane Parameters <a name="arduplane-parameters"></a>
The parameters file below represents the settings used on a typical MiniHawk-VTOL utilizing a mRo PixRacer Pro flight controller. The essential settings should be applicable to whatever ArduPlane-compatible flight controller is used, such as the Matek F405-WING or similar, but some adaptation will be required. **WARNING!** Modern ESC protocols (such as OneShot or DShot) do not play well with servos if accidentally connected. At best, the servo will filter out the packet, but in some cases the servo will burn out. Don't plug servos into the ESC outputs!

mRo PixRacer Pro: [ArduPlane_MiniHawk_mRo_PixRacerPro.param](/cfg-Config/ArduPlane_MiniHawk_mRo_PixRacerPro.param)

While the parameters file above has over 1100 parameters, some essential parameters are examined below:
```
| Parameter,Value        | Notes                                                      |
| ---------------------- | ---------------------------------------------------------- |
| ARSPD_FBW_MAX,32       | Full-Throttle produces around 32 to 34 m/s sprint velocity |
| ARSPD_FBW_MIN,17       | Stall is near 15 m/s for a typical MiniHawk-VTOL           |
| ARSPD_RATIO,1.9936     | Make sure this is calibrated for your aircraft             |
| ARSPD_TUBE_ORDER,0     | While this can be automatic (3), manually set is better    |
| ARSPD_TYPE,1           | MS4525D0 Pressure Sensor, adjust as needed                 |
| ARSPD_USE,1            | Force the aircraft to use the pitot probe, no synthetic    |
| AUTOTUNE_LEVEL,7       | 7 or 8 works best for the MiniHawk-VTOL                    |
| EK2_ENABLE,0           | EKF2 is Disabled, in favor of EKF3                         |
| EK3_ENABLE,1           | EKF3 was used for most flight testing of the design        |
| FLTMODE_CH,5           | Flight Mode Channel                                        |
| FLTMODE1,5             | FBWA, 3-position switch "Down" detent                      |
| FLTMODE2,19            | QLOITER, 3-position switch "Middle" detent                 |
| FLTMODE3,17            | QSTABILIZE, 3-position switch "Up" detent                  |
| FLTMODE4,17            |                                                            |
| FLTMODE5,17            |                                                            |
| FLTMODE6,10            | AUTO, 2nd R/C switch that overrides the 3-position switch  |
| FS_LONG_ACTN,1         | Failsafe Settings used in development                      |
| FS_LONG_TIMEOUT,3      |                                                            |
| FS_SHORT_ACTN,1        |                                                            |
| FS_SHORT_TIMEOUT,1     |                                                            |
| KFF_RDDRMIX,0          | Remove any possible rudder mixing                          |
| LIM_PITCH_MAX,2000     | Pitch and Roll Angle Limits                                |
| LIM_PITCH_MIN,-2500    |                                                            |
| LIM_ROLL_CD,5500       |                                                            |
| MIXING_GAIN,0.5        | Elevon Stick Mixing, value here should be default          |
| NAVL1_PERIOD,11        | More aggressive navigation is possible, 11 to 14 tested    |
| PTCH_RATE_D,0          | Pitch PIDs, these values are mild, AUTOTUNE will increase  |
| PTCH_RATE_FF,0.345     |                                                            |
| PTCH_RATE_FLTD,4       |                                                            |
| PTCH_RATE_FLTE,7       |                                                            |
| PTCH_RATE_FLTT,1.5     |                                                            |
| PTCH_RATE_I,0.15       |                                                            |
| PTCH_RATE_IMAX,0.666   |                                                            |
| PTCH_RATE_P,0.04       |                                                            |
| PTCH_RATE_SMAX,150     |                                                            |
| PTCH2SRV_RLL,1         |                                                            |
| PTCH2SRV_RMAX_DN,90    |                                                            |
| PTCH2SRV_RMAX_UP,90    |                                                            |
| PTCH2SRV_TCONST,0.4    |                                                            |
| Q_A_ACCEL_P_MAX,110000 | VTOL R/P/Y Angular accelerations used in development       |
| Q_A_ACCEL_R_MAX,110000 |                                                            |
| Q_A_ACCEL_Y_MAX,27000  |                                                            |
| Q_A_RAT_PIT_D,0.0005   | VTOL Pitch PIDs                                            |
| Q_A_RAT_PIT_FF,0       |                                                            |
| Q_A_RAT_PIT_FLTD,15    |                                                            |
| Q_A_RAT_PIT_FLTE,0     |                                                            |
| Q_A_RAT_PIT_FLTT,20    |                                                            |
| Q_A_RAT_PIT_I,0.15     |                                                            |
| Q_A_RAT_PIT_IMAX,0.5   |                                                            |
| Q_A_RAT_PIT_P,0.15     |                                                            |
| Q_A_RAT_PIT_SMAX,0     |                                                            |
| Q_A_RAT_RLL_D,0.003    | VTOL Roll PIDs                                             |
| Q_A_RAT_RLL_FF,0       |                                                            |
| Q_A_RAT_RLL_FLTD,15    |                                                            |
| Q_A_RAT_RLL_FLTE,0     |                                                            |
| Q_A_RAT_RLL_FLTT,20    |                                                            |
| Q_A_RAT_RLL_I,0.25     |                                                            |
| Q_A_RAT_RLL_IMAX,0.5   |                                                            |
| Q_A_RAT_RLL_P,0.45     |                                                            |
| Q_A_RAT_RLL_SMAX,0     |                                                            |
| Q_A_RAT_YAW_D,0.02     | VTOL Yaw PIDs                                              |
| Q_A_RAT_YAW_FF,0.1     |                                                            |
| Q_A_RAT_YAW_FLTD,0     |                                                            |
| Q_A_RAT_YAW_FLTE,10    |                                                            |
| Q_A_RAT_YAW_FLTT,20    |                                                            |
| Q_A_RAT_YAW_I,0.1      |                                                            |
| Q_A_RAT_YAW_IMAX,0.5   |                                                            |
| Q_A_RAT_YAW_P,0.6      |                                                            |
| Q_A_RAT_YAW_SMAX,0     |                                                            |
| Q_ANGLE_MAX,3000       | VTOL Pitch and Roll Angle Limits                           |
| Q_ASSIST_ALT,0         | Disable VTOL Assist where possible                         |
| Q_ASSIST_ANGLE,0       |                                                            |
| Q_ASSIST_DELAY,0.5     |                                                            |
| Q_ASSIST_SPEED,0       |                                                            |
| Q_AUTOTUNE_AGGR,0.1    | VTOL Autotune settings used in development                 |
| Q_AUTOTUNE_AXES,2      |                                                            |
| Q_AUTOTUNE_MIN_D,0.001 |                                                            |
| Q_ENABLE,1             | VTOL obviously is enabled for the MiniHawk-VTOL            |
| Q_FRAME_CLASS,7        | Tricopter Configuration                                    |
| Q_FW_LND_APR_RAD,85    | 85 meters for Fixed-wing to VTOL threshold                 |
| Q_M_HOVER_LEARN,2      | Hover throttle setpoint learning                           |
| Q_M_PWM_TYPE,4         | DShot 150 is sufficient and noise-resistant                |
| Q_M_SPIN_ARM,0.05      | 5% Throttle when armed                                     |
| Q_M_SPIN_MAX,1         | 100% Throttle max ESC RPM command                          |
| Q_M_SPIN_MIN,0.1       | 10% Throttle for lowest ESC RPM                            |
| Q_M_SPOOL_TIME,0.5     | 500ms spool time                                           |
| Q_M_THST_EXPO,0.25     | Throttle Expo                                              |
| Q_M_YAW_HEADROOM,50    | 50us Yaw Headroom                                          |
| Q_M_YAW_SV_ANGLE,12    | "12" Degrees for Yaw lean angle                            |
| Q_OPTIONS,1056         | Allow yaw actuation when disarmed, QRTL behavior           |
| Q_RC_SPEED,490         | 490 Hz Motor Updates                                       |
| Q_RTL_ALT,40           | RTL Behaviors in VTOL                                      |
| Q_RTL_MODE,1           |                                                            |
| Q_TILT_MASK,3          | Which motors are being tilted                              |
| Q_TILT_MAX,55          | Transition angle while AirspeedWait is active              |
| Q_TILT_RATE_DN,15      | Tilt Up/Down rates                                         |
| Q_TILT_RATE_UP,75      |                                                            |
| Q_TILT_TYPE,2          | Vectored Yaw Tilt Type                                     |
| Q_TILT_YAW_ANGLE,14    | "14" degrees VTOL hover position                           |
| Q_TRANS_FAIL,0         | Transition Timeout is disabled                             |
| Q_TRANSITION_MS,1000   | Post-transition wait period                                |
| Q_TRIM_PITCH,9         | Pitch offset between forward-flight and hover stance       |
| Q_WVANE_GAIN,0.4       | 0.4 is a good value for this design                        |
| RC7_OPTION,41          | Arming Switch, will disable motors if in flight/hover!     |
| RCMAP_PITCH,2          | Roll/Pitch/Throttle/Yaw (AETR) controls ordering           |
| RCMAP_ROLL,1           |                                                            |
| RCMAP_THROTTLE,3       |                                                            |
| RCMAP_YAW,4            |                                                            |
| RLL_RATE_D,0           | Roll PIDs, these values are mild, AUTOTUNE will increase   |
| RLL_RATE_FF,0.345      |                                                            |
| RLL_RATE_FLTD,4        |                                                            |
| RLL_RATE_FLTE,7        |                                                            |
| RLL_RATE_FLTT,3        |                                                            |
| RLL_RATE_I,0.15        |                                                            |
| RLL_RATE_IMAX,0.666    |                                                            |
| RLL_RATE_P,0.08        |                                                            |
| RLL_RATE_SMAX,150      |                                                            |
| RLL2SRV_RMAX,90        |                                                            |
| RLL2SRV_TCONST,0.4     |                                                            |
| RTL_AUTOLAND,2         | Fixed-wing to VTOL landing behavior in RTL                 |
| RUDD_DT_GAIN,3         | Very mild differential thrust mixing on forward motors     |
| SCALING_SPEED,15       | 15 m/s should be default                                   |
| SCHED_LOOP_RATE,300    | 300 Hz was used in development                             |
| SERVO1_FUNCTION,33     | Right BLDC Motor                                           |
| SERVO2_FUNCTION,34     | Left BLCD Motor                                            |
| SERVO3_FUNCTION,0      | No Connection, 5V BEC connected here for mRo PixRacer Pro  |
| SERVO4_FUNCTION,36     | Rear BLCD Motor                                            |
| SERVO5_FUNCTION,75     | Left Tilt Servo                                            |
| SERVO5_MAX,1800        | MAX and MIN values are hand calibrated, close to 1920/1080 |
| SERVO5_MIN,1200        | Values of 1200/1800 here to prevent damage on new builds   |
| SERVO5_REVERSED,0      | Left Tilt is normal rotation direction                     |
| SERVO6_FUNCTION,76     | Right Tilt Servo                                           |
| SERVO6_MAX,1800        |                                                            |
| SERVO6_MIN,1200        |                                                            |
| SERVO6_REVERSED,1      | Right Tilt is reversed rotation direction                  |
| SERVO7_FUNCTION,77     | Left Elevon Servo                                          |
| SERVO7_REVERSED,1      | Left Elevon is reverse rotation direction                  |
| SERVO8_FUNCTION,78     | Right Elevon Servo                                         |
| SERVO8_REVERSED,0      | Right Elevon is normal rotation direction                  |
| STAB_PITCH_DOWN,2      | 2 should be default, pitch behavior on zero-throttle       |
| STALL_PREVENTION,0     | May be enabled, was disabled for development               |
| STICK_MIXING,1         | How pilot inputs are fused in autonomous modes             |
| TECS_PTCH_FF_V0,19     | 19 m/s cruise                                              |
| TRIM_ARSPD_CM,1900     | 19 m/s cruise                                              |
| TRIM_PITCH_CD,350      | Offset between level-flight pitch angle and tray angle     |
| TRIM_THROTTLE,55       | Typical 19 m/s cruise throttle                             |
| WP_LOITER_RAD,60       | 60 meter radius for loiter typical                         |
| WP_RADIUS,40           | 40 meter waypoint radius typical                           |
```


## Remarks: <a name="arduplane-remarks"></a>
ArduPlane v4.1.0 and v4.2.0dev were used in the development of the Version 2 MiniHawk-VTOL. "Out-of-the-box", ArduPlane has support for a Tricopter Tiltrotor such as this design, and only the parameters need to be set for enabling the VTOL behaviors. 

At this firmware version, there are some aspects of how VTOL flight behaviors are handled which are somewhat counter-intuitive. The most annoying of these is that for both piloted and autonomous flying, there is no direct control of the VTOL flight state. Instead of being able to directly command the Forward-Flight condition, the VTOL state-machine requires an airspeed estimate (either synthetic or measured from a pitot probe) to drive the forward VTOL transition to fixed-wing flight. This makes the human pilot merely a voting member in the transition process, with accumulated airspeed determining when the tilting rotors are allowed to fully tilt forward and the rear motor to halt. The developers' mentality treats the hover condition as the default fallback, and any failure to accumulate airspeed in a certain amount of time will have the process revert to hover as a failsafe via `Q_TRANS_FAIL`. If this transition failure timeout is disabled, the AirspeedWait state will persist and the vehicle will fly in a half-way blend between tricopter and fixed-wing flight indefinitely. For a vehicle design such the MiniHawk-VTOL, over-powered and very fast, it would make more sense for a timeout to result in forcing forward-flight rather than to place the vehicle in this blended behavior, or if using the transition failure timer, to place the vehicle into hover with limited battery at extreme range and altitude, but that is a pull request for another day. And thus, for the current firmware state, it is necessary to be aware of this behavior and to know why it gets stuck in the blended mode.

Another consequence of the forward-transition VTOL behavior is that while disarmed, even though a forward-flight mode selection (such as FBWA) will result in the rotors tilting to the forward position, upon arming, the vehicle will immediately assume the AirspeedWait state, with the front rotors tilting up and the rear rotor spinning up. The throttle setting apparently determines the mix between hovering and forward-flight airspeed wait, but a better solution if you are trying to hand-launch like a traditional fixed-wing is to "bump" into MANUAL mode for a moment. This forces the VTOL state-machine past the AirspeedWait state and allows you to Arm in FWBA mode and have the forward rotors remain in the forward position and also enjoy elevon stabilization and leveling while hand-launching. Just be sure to flip out of MANUAL mode back to FBWA, unless you intend a fully MANUAL hand-launch with no stabilization or leveling.

Transitions from Fixed-Wing flight to hover are typically smooth when being human-piloted, but in autonomous modes, there is a known issue in which the vehicle will nose-dip and then pull up hard when making the reverse VTOL transition to hover. This can be hazardous to the vehicle if negative gee-loading or sudden jerk movement will cause parts to separate. The issue is likely in the TECS tuning parameters, or is an issue local to firmware 4.1 or 4.2.


# License <a name="license-brief"></a>
This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/ or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.  

The software configuration text files provided here likely fall under the same license as Betaflight, GPL-3.0 at the time of this writing.  

MiniHawk VTOL - Design, Documentation, Images and all other Artwork; by Steve Carlson  
[https://github.com/StephenCarlson/MiniHawk-VTOL](https://github.com/StephenCarlson/MiniHawk-VTOL)
