# MiniHawk-artwork
Mechanical artwork for the MiniHawk VTOL, the successor to the OrangeHawk VTOL.

Accompanying Build Video Series: [YouTube Playlist](https://www.youtube.com/playlist?list=PLEMjH2uELUcYI_DS1zthgjE4Su79LeA_G)

# MiniHawk Build Parts List and Tools:
## Recommended Tools and Equipment
 - FDM/FFF 3D Printer with build volume greater than 23.1x210.7x330.0mm (Dimensions of largest part, which is Left/Right Wing. Adventurous builders might try printing larger parts in sections)
 - Soldering Station and associated tools and materials
 - Handcrafting Tools
 - Adhesives: Cyanoacrylate Glue, Epoxy, Hot-Melt Adhesive Gun, Tape
   
## Components and Electronics:
 - qty:1 Flight Controller (3 Motor, 4 Servo Outputs)(Matek Systems F722-WING)
 - qty:3 ESCs (3s, 20A or better)(Spedix ES20 Lite)
 - qty:2 BE1806 2300KV BLCD Motors (or equivalent, must be no larger than OutsideDiameter=24mm, able to produce between 350g to 500g static thrust and pitch speed of ~20m/s with 5in prop)
 - qty:1 BE2206 2000KV (or equivalent, may be up to OutsideDiameter=30mm, between 700g to 1000g static thrust)
 - qty:1 3s1300 Lipoly (better than 40C)
 - qty:2 HS-65HB Servos (Servo pockets designed for up to 26mm wide, 17.5mm from bottom of mounting tabs to bottom of servo, 32mm from top of output shaft to bottom of servo, 12mm thick. Should fit most "Sub-Micro" Servos)
 - qty:2 HS-65MG Servos (Same pocket dimensions as above, but these are going to be fantastically abused and must be really tough. Or just count on stripping your non-metal-gear servos a lot.)
 - qty:6 Du-Bro Small Nylon Hinges (Can be omitted but 3D-printed living-hinge on elevons will eventually fail, mend appropriately)
 - Either M2 or M3 Nylon Standoff and Spacer hardware for mounting Flight Controller.
 - qty:4 6-Inch Servo Extension Cables. Alternatively, cut the servo cables and solder in-line extensions for the cables to reach to the flight controller, plus some slack.
 - qty:4 Du-Bro Kwik Link Clevis for 0.72-inch (2-56) threaded rod/wire. Two of these for the Elevon Servos, two for the motor tilt servos.
 - qty:2 2-56 Threaded Linkage Rods with L-bend at 45mm from threaded tip. These connect from the Elevon Servos to the Elevon Control Horns. 
 > (Note that the above clevises and rods can be purchased as a set, such as Du-Bro Item #185, which is a set of 5 rods with clevises already attached)
 - qty:2 Du-Bro E/Z Links 0.72 (2-56) Retainer Clips. These secure the L-Bend at the Elevon Control Horns.
 - qty:2 1/16 2-56 Threaded Ball Link, such as GreatPlanes GPMQ3843. **CRITICAL!!! The Ball Link thread must be "116", 1/16-inch, 62.5mil, or 1.59mm.** The more popular variant is the 2-56 thread size ball, which is too big for the nacelle motor tilt attachment. Note that this is the ball-link thread size; the coupler that captures the ball is 2-56 threaded. This ball-link set attaches from the motor tilt servo linkage to the motor tilt mount, which holds the front left/right motor.
 - qty:2 2-56 Fully-Threaded Rods, straight, 60mm long. One end threads to Du-Bro Kwik Link 2-56 Clevis, other end threads to a 2-56 Ball Link coupler.
 - qty:2 Length=24mm, Diameter=[1.83mm to 1.87mm] Steel Rod (Formed from spare pieces of 2-56 Servo Pushrod. Use non-threaded smooth rod, roughen/knurl only one end slightly for press-fitting to nacelle)
 - (optional) qty:2 WS2812 or equivalent Addressable LED, 5050 SMD or smaller raw device. These are soldered with magnet wire and mounted in the wingtips.
   
 
## Airframe Parts:
 - Fuselage Nose - *MH5_Nose.stl*
 - Empennage Left Half - *MH5_Empennage.stl*
 - Empennage Right Half - *MH5_Empennage.stl Mirrored*
 - Lid Left Half - *MH5_Lid.stl*
 - Lid Right Half - *MH5_Lid.stl Mirrored*
 - Fin (2) - *MH5_FinLeft.stl*
 - Left Wing - *MH5_WingLeft_NoSolar.stl*
 - Right Wing - *MH5_WingLeft_NoSolar.stl Mirrored*
 - Elevon Control Horn (2) - *MH5_ControlHorn.stl*
 - Left Nacelle Left Half - *MH5_NacelleB.stl*
 - Left Nacelle Right Half - *MH5_NacelleA.stl*
 - Left Motor Mount - *MH5_TiltMount.stl*
 - Right Nacelle Left Half - *MH5_NacelleA.stl Mirrored*
 - Right Nacelle Right Half - *MH5_NacelleB.stl Mirrored*
 - Right Motor Mount  - *MH5_TiltMount.stl Mirrored*
 - Flight Controller Tray - *MH5_ControllerTray.stl*
 - Battery Tray - *MH5_BatteryTray.stl* 
 
# Build Sequence

## Part 1 - Airframe Structures and Motor Mount/Tilt Attachment
1. Clean all 3D-Printed parts, remove all brim/support material. For each wing, carefully carve away any stringing or over-extrusion in the hinge reinforcement wells such that the hinge pin will fit. Carefully cut the elevons free if needed (WARNING! Only cut slots on either end to allow for surface deflection, DO NOT cut the entire elevon out), and gently exercise each surface up and down until the living hinge is established. Bond the Canopy/Hatch-Lid pieces together using Thin/Medium Cyanoacrylate or Epoxy, and set aside to cure.
2. Bond the Empennage Halves together. Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. Set aside to cure.
3. Bond the Control Horn pieces (2) into each Elevon (Left Wing and Right Wing). Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. The Control Horn should be fairly flush on the Elevon Top Surface, approximately 0.5mm extending above the surface. Fit should be tight; carefully carve away any burrs or over-extrusion from the slot in the elevon if needed.
4. Glue the Du-Bro Nylon Mini-Hinge pieces (3 per wing, Du-Bro SKU#118) into the recesses along each elevon hinge. Hot-Melt-Adhesive, CA, or Epoxy should work.
3. Lightly sand the bonded empennage/tail interface surface until smooth and planar/flush. Test-fit to the Fuselage/Nose to confirm a proper flush joint, and then bond to the Fuselage/Nose using Thin or Medium Cyanoacrylate, or Epoxy. Set aside to cure.
4. Bond the Nacelle Pair Halves together. Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. Proper alignment is critical, be careful and precise. Set aside to cure.
5. Lightly sand both wing root interface surfaces on the completed fuselage/body until flush and smooth. Test-fit both wings to each respective surface to confirm a proper flush joint. Bond either the left or right wing to the fuselage (not recommended to attach both at once) using Epoxy. (Cyanoacrylate may not have the strength needed.) Set aside to cure. When the first wing is cured, bond the second wing and set aside to cure.
6. Test-fit each Motor Mount (Tilt Mount/Pod) with its respective completed nacelle. Sand or trim as needed such that the Motor Mount is able to tilt fully flush forward, and able to tilt up past 90 degrees of rotation.
7. For each Nacelle with its respective Motor Mount aligned and present, Ream (Drill to size) using a 1.58mm (1/16 Inch, 62.5mil) drill bit. (Should be 85% to 90% of diameter of hinge rod to be fitted. Hinge Rod diameter is 1.84mm or 72mil for this case.) Keep the Motor Mount and Nacelle together. Adapt a section of hinge rod to be used as a final precision reaming tool by sharpening the tip using a grinder or emery wheel. Use this improvised reaming tool to ream the hole in each nacelle-mount pair to the final diameter of 1.84mm (72mil).
8. Remove each Motor Mount from its respective Nacelle and ream only the Motor Mount hole to the next higher drill bit size, not to exceed 107% of diameter of the the hinge rod. Too large will allow for excessive play and possible rattling; too small will result in binding. 1.95mm (77mil, 5/64 Inch) is acceptable for hinge rod diameter of 1.84mm.
9. Cut the hinge rod pieces, not to exceed 24mm length. Roughen/knurl one or both ends if desired. Press-fit each hinge rod to each Nacelle through the respective Motor Mount. Verify that each Motor Mount can rotate freely and with minimal play in the hinge.
10. For each Motor Mount, ream the Motor Mount linkage mount hole to 1.19mm (3/64 Inch, 47mil). This should be about 80% of the major diameter of the threaded ball link to be mounted. (Great Planes Threaded Ball Link Set 1/16", GPMQ3843; ball-link is 1.50mm major diameter.) Mount the threaded ball-link to the linkage mount hole. The Motor Mount can sustain up to 3.3mm threaded bolt depth, verify that the bolt does not extend too far into the well, such that it will not make contact with the motor.
11. Bond each Nacelle to its respective wing; note that the ball-link should align with the respective servo linkage slot/well. Epoxy is recommended, as this is a significant load-bearing structure. Verify alignment and tweak/tune while the glue cures.
12. Bond both vertical fins to the wing(s). Medium Cyanoacrylate should be sufficient.

## Part 2 - Linkages and Component Mounting
1. Mount the front two motors in their respective Motor Mounts. The motor leads may have heatshrink that may interfere or bind the wires; rework this if needed. Mount the motors using the M2 threaded bolt kit that should be included with each motor. Be careful not to have any mounting bolt over-extend into the motor armature/stator. Verify that each motor turns freely and is well secured. Route the wires through the wing and into the main bay, and test the extension-retraction behavior of the wires as the motor mount pitches between forward and hover tilt positions. For each motor, attach the propeller hub hardware kit that should be included with each, such that it can drive a standard 5-Inch propeller.
2. The Rear motor should mount to the tail using M3 threaded bolts that were included with the motor. Route the motors wires through either wire duct channel to the main bay as desired. Verify that the motor rotates freely and is well secured. Attach the propeller hub hardware kit that should be included with the motor, such that it can drive a standard 5-Inch propeller.
3. The Motor Mount Tilt servos should be tested and centered on a standard RC PWM signal, visiting 1000us, 1500us, and 2000us pulse-widths. Attach a servo arm with a 19.3mm (0.76 Inch) hole-to-center spacing. This value is critical, as the linkage behavior of the tilting front motor mounts cannot be easily modified and any length short of this will result in the motor tilt not reaching the needed angle for hover and anti-torque (yaw) control. An arm any longer than this will not fit in the linkage well/slot. With whatever arm fitted as similar to 19.3mm as possible, test fit the servo into the servo well and verify that between 1000us and 2000us pulse widths, the arm comfortably retracts into the well/slot, and fully sweeps about 90 to 95 degrees from that point. Verify the best servo arm spline position and secure the arm with threaded bolt.
4. For each of the Elevon servos, repeat the same procedure as above, but with a servo arm approximately 9.5mm hole-to-center (3/8 Inch). This length can be a bit longer or shorter, the effect is increasing or decreasing elevon control throw. For servos that have an odd-number spline tooth count (such as the Hitec HS-65HB's B1 spline with 25 teeth), to get the most well-centered and symmetric solution, center the servo on a 1500us pulse width and alternate attaching a 4-arm output horn between each 90-degree position to find the most orthogonal/centered position, and then cut off the 3 unneeded arms.
5. Verify that the Link Clevises that attach to the servo arms are able to couple and rotate freely. Reaming the servo arm may be necessary, a value of 1.59mm (1/16 Inch, 62mil) is common.
6. Route the servo wires through the conduit tunnels in the wing to the main bay. Be advised that this is somewhat irreversible, depending on the quality of the 3D print, any glue protrusions in the tunnel, and weaving/tangling of the pigtails after routing. The 3-pin connectors on the pigtail can be carefully removed to allow the wires to pass back out if needed later. Assuming all servos have a 6-inch (~150mm) servo pigtail, the Elevon servos will have some slack, but the Tilt servos will arrive just barely at the main bay. Servo Extensions can be added, or the servo pigtail can be extended with a section of 3-wire servo lead/cable, or the 3-pin servo connectors can be discarded in favor of direct soldering later if desired.
7. With servo harnessing finished in one form or another, bond the servos to the airframe using Hot-Melt-Adhesive. Note that the airframe may exhibit deformation or melting at the bonding locations, depending on print material used. Verify that the servos can produce full torque without becoming detached from the airframe. Also note that alternatives may be explored in servo mounting, such as double-sided adhesive tape, but it is not advised to use cyanoacrylate or epoxy.
8. Form the elevon control rods by creating an L-bend 45mm from the threaded tip of the pair of 2-56 link rods used. Test fit the retaining Du-Bro E/Z Links 0.72 (2-56) Retainer Clip for each bend, and modify the bend as needed and cut flush. Alternatively, a traditional Z-bend can be formed to dismiss the Retain Clips as a requirement. For each Elevon, attach its control rod to the elevon control horn, and attach the clevis to the corresponding servo arm. Detach, turn the clevis, and reattach as needed until the elevon is flush while the servo is centered on 1500us.
9. Cut two (2) 60mm long pieces from a fully-threaded 2-56 rod to form the tilt control rod pair. (Do NOT bend these rods.) Soften the cut ends with a grinder or emery wheel such that they will easily thread into the Nylon Ball-Link couplers. Thread on the ball-link couplers and link clevises, and attach each to its respective servo arm or ball-link head. Detach-turn-reattach as needed, such at the servo approaches as close to top-dead-centre (arm retracted into well/slot) as possible, without binding or interference, while the tilting motor mount is firmly forward and pressed against the nacelle. As noted earlier, the clevis should attach to the highest hole in the servo arm, at 19.3mm arm distance. Some allowance can be made for bending this rod slightly to allow for the servo arm to fully retract without the clevis impacting the arm. If the servo is straining excessively when the motor mount is retracted, adjust accordingly.
10. The above steps assumed that the servos were able to be powered and
 commanded, but for completeness, this step verifies that the servos are able to actuate, and are not being stressed. For each servo, visit 1000us-1500us-2000us and observe deflection on Elevons or Motor Mount and verify that there is not excessive binding or stress. For each motor mount, simulate the load exhibited during forward flight by gently pulling on the motor in the forward direction (about 300 grams force), while the servo is actively commanded to retain the forward condition, and verify that the motor is retained/held in the forward flight position with minimal creepage. Elevons should actuate the full range with light loading on the control surface.

## Part 3 - Electronics and Final Configuration
1. Solder the Flight Controller as desired. This usually means soldering pin headers to attach the 3-pin servo connectors from the servos and ESCs. Solder a battery connection lead (XT60 or as desired). Power the Flight Controller and verify that it is booting and communicating correctly. Default (likely multicopter) firmware will be fine for the next few steps.
> Note for the Matek F722-WING: The following assignments are used for servos and ESCs <STEVE TODO>.
2. Bond the Battery and Flight Controller Trays into the main bay. This can be accomplished using M2 or M3 hardware and ample Hot-Melt-Adhesive and some reaming if necessary. The Battery Tray can be permanently mounted, but retain some ability to remove the Flight Controller Tray, as mounting/removing the flight controller requires access to the bottom of that tray. 
3. Solder the BLDC Motor leads to each respective ESC, or use bullet-connectors or otherwise as desired. Solder the ESC power connections directly to the Flight Controller's Power-Distribution region, or to intermediate connections as desired. Power on the Flight Controller carefully, such as with a "Smoke Stopper" or a current-limited power supply, and verify that the power system is wired correctly. Program the ESCs for proper rotation direction: Port/Left Motor is Clockwise (CW), Starboard/Right Motor is Counterclockwise (CCW). The Rear Motor may technically be either direction, but I **strongly** recommend Counterclockwise (CCW) to allow for most non-multicopter propeller options, and to force a consistent tradition that allows for future sharing of PID profiles and control schemes symmetrically.
 > A brief note on prop rotation directions: The reason for the front motors having the Clockwise and Counterclockwise directions as stated is such that when the vehicle is flying in forward flight, and then immediately commanded to hover, the advancing blade(s) are placed as far abeam (toward the wingtip) as possible, while the retreating blade is closer to the main body. This should allow for better roll control through the transition, and by placing the effective centeres of lift for each rotor slightly wider in this condition, any PID control effort is more likely to remain bounded and slightly attenuated by the slightly longer moment-arm. This also follows the typical configuration for quadrotors, which also have the front advancing blades placed on the outside of the arc.
4. At this point, flash the Flight Controller with the specific firmware relevant to controlling a Tricopter VTOL Fixed-Wing vehicle, if not already. Attach the servo and ESC headers to their required pins. Install the R/C receiver and connect to the Flight Controller as required. Mount the Flight Controller to its tray, and secure the tray inside the main bay. Power the vehicle and verify Flight Controller orientation is correct, servos are properly commanded, and that control surface efforts are in the correct direction. Reverse and trim servo outputs as necessary in the Flight Controller configurator.
5. (Optional) WS2812 LEDs may be mounted in each wingtip, provided each is a SMD5050 or smaller package, with wires directly soldered to the package pads, and then mounted in the light well on each tip.
6. Stow the ESCs to the side-walls of the main bay using tape or double-sided adhesive pads. Stow any excess wires, and generally clean up the inside of the main bay. Secure the battery using Velcro, Tape, or other measures.
7. Mount the propellers to their respective motors. For initial flight testing, it is recommended to use the same propeller for all three motors, a 5030 to 5040 three-blade prop is recommended. Later on, the rear propeller may be swapped with a 5535 or 6030 three-blade, and the front two may be swapped with a 5050 or similar.
8. The Center-of-Mass for the aircraft is intended to be at 165mm back from the tip of the nose, or 40mm back from the leading edge of the wing. This is exactly along the middle pair of mounting holes for the Battery Tray. This is an initial value, and the Center-of-Mass may be shifted back by around 8mm to 15mm from this point at some risk to stability. As this vehicle is both a fixed-wing and multicopter, the Center-of-Mass stated here is for the fixed-wing condition, and any measurement of Center-of-Mass should be performed with the motors tilted into the forward-flight condition, propellers attached, and the lid secured. Shift the battery fore or aft to achieve proper balance, or add ballast if merited.
9. Perform any other measures necessary to get the vehicle ready for flight. Decals, paint, or heat-activated covering are possiblilties. Vehicle mass should come to an All-Up-Weight around 700 grams to 800 grams, with the 3D-printed airframe alone measuring around 300 grams.

# Part 4 - Flight Testing (In Progress)
1. Discovering PIDs; test-stand setup and axis-isolation. Gain Scheduling for hover-to-forward-flight and reverse transitions.
2. Free hovering hops, progressing to static hovering, tuning hovering PIDs.
3. Forward-flight transitions with direct R/C control (no PIDs altering control surfaces)
4. PIDs for Forward flight pitch and roll. 

