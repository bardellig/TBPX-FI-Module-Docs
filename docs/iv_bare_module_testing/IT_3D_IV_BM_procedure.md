# **IT 3D Flip-CHIP IV procedure**

Material:

* [HV Tool](https://indico.cern.ch/event/1468581/contributions/6188526/attachments/2954303/5194113/HV_Tool.pdf)
    * The tool consists of two conductive rubber parts (GND and HV) and a mechanical structure equipped with a spring that allows the rubber to descend and make contact with the flip-chip. The HV rubber ("Up") supplies voltage to the sensor's back side, while the GND rubber ("Down") is in contact with the chip pads, grounding them. Both rubbers are connected via Lemo cables.
* Suction Pen
* HV Generator
![Set-up dettagliato](https://codimd.web.cern.ch/uploads/upload_133b902f648598805a45c5416e51b7a8.png)

![Gomma conduttiva e connessioni GND e HV](https://codimd.web.cern.ch/uploads/upload_a809b5407b6fef66fd2409d200d46af1.png)

Preliminary Operations:
* Activating vacuum on the pump outside the cleanroom
    * Open the vacuum line in the laboratory. The valve is located on the elevated grid where the tubes and cables run. The vacuum line that reaches the granite table where the measurements are performed is the central one. To enable it, open the valve located at the center of the grid immediately after entering the cleanroom where the IV measurements take place.
* Prepare the rubber tubing to supply vacuum to the gel-paks and the structure with conductive rubber.
* Connecting the HV generator to the tool with conductive rubber
    * Connect SMU1 to the GND of the tool and SMU2 to the HV of the tool.
    * The GND rubber is located beneath the mechanical structure (down), while the connection for the HV rubber is located above the mechanical structure (up).
* Switching on the generator and the computer
    * Open the executable IV_standard on the PC. In the software, set the folder name for saving data to \MISURE_IV\CROC_v2 (add the date if necessary, for example, for repeated measurements or if the folder is already full).
    * Set the IV limits from 0 to -30 V (use the minus sign) with steps of 1 V, a step speed of 5 V/s, and a delay between steps of at least 1–1.5 seconds. The current compliance is set to 1 µA.
* Create the new folder before proceeding.




Measurement:

* Preparing the flip-chip:
    * Place the gel-pak on the metal support and activate the vacuum.
    * Remove the desired flip-chip using the suction pen and place it on a piece of paper.
    * Turn off the vacuum on the gel-pak, disconnect the tube, remove the gel-pak, and connect the tube to the HV tool’s vacuum (do not activate the vacuum yet).

* Flipping the flip-chip, if needed:
    * If the flip-chip arrives upside down with the chip back exposed, flip it as follows:
        1. Position the pads facing the user.
        2. Use the suction pen to apply gentle pressure with your index finger.
        3. Rotate 180°, resting the flip-chip's thickness on the paper.
        4. Gently tilt the suction pen until the flip-chip is flipped, leaving the sensor back exposed.
    *  Alternatively, use two pieces of paper (one above and one below the flip-chip) to flip it while maintaining contact to prevent slipping.
![Back del Sensore](https://codimd.web.cern.ch/uploads/upload_ca63c6b909d1e98a0b25c52630282062.png)
*  Visual Inspection:
    *  Check that the sensor back, once flipped, has no scratches or anomalies. Perform a detailed visual inspection and take photos if anomalies are detected.
*  Positioning in the HV tool:
    *  Keep the flip-chip on the paper and move it toward the HV tool using the suction pen.
    *  Place the flip-chip on the end of the tool without cables or pins, with the pads facing the mechanical structure and Lemo cables.
    *  Gently slide the flip-chip toward the measurement area without activating the vacuum. Align it with the white pins and adjust its depth using the black support screw.
    *  Ensure the pads are below the "down" rubber. If not, adjust the black support by loosening and then tightening it.
    *  From above, verify that the flip-chip is parallel and that all pads align with the "down" rubber.
![Allineamento](https://codimd.web.cern.ch/uploads/upload_f363abcbac66e4649bae82a8976d01ff.png)
*  Activate the vacuum.
*  Lower the supporting structure gently, in small steps, assisting the spring mechanism if blocked, until contact is achieved with both rubbers.
*  Performing the measurement:
    *  If the measurement fails, showing only ~pA currents, check the contacts.
    *  If it stops without reaching compliance, increase the delay between steps.
    *  If a breakdown occurs, repeat the measurement. If the issue persists, classify the flip-chip as "bad."

*  Save the measurement.
*  Raise the mechanical support, turn off the vacuum, and move the flip-chip onto a piece of paper for transport.
*  Reconnect the tool’s tube to the gel-pak metal support.
*  Return the flip-chip to its original location, this time flipped over, and proceed with the next one.

[← Back to main page](../../index.md)
