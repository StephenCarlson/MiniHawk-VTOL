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
 - qty:2 1/16 2-56 Threaded Ball Link, such as GreatPlanes GPMQ3843. **CRITICAL!!! The Ball Link thread must be "116", 1/16-inch, 62.5mil, or 1.59mm.** The more popular variant is the 2-56 thread size ball, which is too big for the nacelle motor tilt attachment. Note that this is the ball-link thread size, the coupler that captures the ball is 2-56 threaded. This ball-link set attaches from the motor tilt servo linkage to the motor tilt mount, which holds the front left/right motor.
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
1. Clean all 3D-Printed parts, remove all brim/support material.
2. Bond the Empennage Halves together. Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. Set aside to cure.
3. Bond the Control Horn pieces (2) into each Elevon (Left Wing and Right Wing). Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. The Control Horn should be fairly flush on the Elevon Top Surface, approximately 0.5mm extending above the surface. Fit should be tight; carefully carve away any burrs or over-extrusion from the slot in the elevon if needed.
4. Glue the Du-Bro Nylon Mini-Hinge pieces (3 per wing, Du-Bro SKU#118) into the recesses along each elevon hinge. Hot-Melt-Adhesive, CA, or Epoxy should work.
3. Lightly sand the bonded empennage/tail interface surface until smooth and planar/flush. Test-fit to the Fuselage/Nose to confirm a proper flush joint, and then bond to the Fuselage/Nose using Thin or Medium Cyanoacrylate, or Epoxy. Set aside to cure.
4. Bond the Nacelle Pair Halves together. Thin or Medium Cyanoacrylate, or Epoxy, are acceptable. Proper alignment is cricital, be careful and precise. Set aside to cure.
5. Lightly sand both wing root interface surfaces on the completed fuselage/body until flush and smooth. Test-fit both wings to each respective surface to confim a proper flush joint. Bond either the left or right wing to the fuselage (not reccomended to attach both at once) using Epoxy. (Cyanoacrylate may not have the strength needed.) Set aside to cure. When the first wing is cured, bond the second wing and set aside to cure.
6. Test-fit each Motor Mount (Tilt Mount/Pod) with its respective completed nacelle. Sand or trim as needed such that the Motor Mount is able to tilt fully flush forward, and able to tilt up past 90 degrees of rotation.
7. For each Nacelle with its respective Motor Mount aligned and present, Ream (Drill to size) using a 1.58mm (1/16 Inch, 62.5mil) drill bit. (Should be 85% to 90% of diameter of hinge rod to be fitted. Hinge Rod diameter is 1.84mm or 72mil for this case.) Keep the Motor Mount and Nacelle together. Adapt a section of hinge rod to be used as a final precision reaming tool by sharpening the tip using a grinder or emery wheel. Use this improvised reaming tool to ream the hole in each nacelle-mount pair to the final diameter of 1.84mm (72mil).
8. Remove each Motor Mount from its respective Nacelle and ream only the Motor Mount hole to the next higher drill bit size, not to exceed 107% of diameter of the the hinge rod. Too large will allow for excessive play and possible rattling; too small will result in binding. 1.95mm (77mil, 5/64 Inch) is acceptable for hinge rod diamater of 1.84mm.
9. Cut the hinge rod pieces, not to exceed 24mm length. Roughen/knurl one or both ends if desired. Press-fit each hinge rod to each Nacelle through the respective Motor Mount. Verify that each Motor Mount can rotate freely and with minimal play in the hinge.
10. For each Motor Mount, ream the Motor Mount linkage mount hole to 1.19mm (3/64 Inch, 47mil). This should be about 80% of the major diameter of the threaded ball link to be mounted. (Great Planes Threaded Ball Link Set 1/16", GPMQ3843; ball-link is 1.50mm major diameter.) Mount the threaded ball-link to the linkage mount hole. The Motor Mount can sustain up to 3.3mm threaded bolt depth, verify that the bolt does not extend too far into the well, such that it will not make contact with the motor.
11. Bond each Nacelle to its respective wing; note that the ball-link should align with the respective servo linkage slot/well. Epoxy is recommended, as this is a significant load-bearing structure. Verify alignment and tweak/tune while the glue cures.
12. Bond both vertical fins to the wing(s). Medium Cyanoacrylate should be sufficient.

## Part 2 - Linkages and Initial Component Mounting

## Part 3 - Electronics






