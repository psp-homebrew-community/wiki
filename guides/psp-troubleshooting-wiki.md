---
layout: default
title: PSP Troubleshooting Wiki
---
# PSP Troubleshooting Wiki

Common issues reported by the PSP community with possible causes and fixes.

> This list is intended as a troubleshooting reference and does not guarantee a fix. Multiple causes may produce similar symptoms.

---

# Power / Charging / Boot

| Issue                        | Symptoms                                                                                            | Possible Causes                                                                 | Possible Fix                                                                                |
| ---------------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Charging LED Always On       | Charging LED remains permanently lit (sometimes faintly), even without battery or charger connected | Defective power switch board, damaged ribbon cable, liquid damage causing short | Inspect & replace power switch board and or ribbon, check for corrosion                                  |
| Super Capacitor Problems     | Power instability, charging issues, abnormal boot behavior, time and date not kept, and constant battery drain even when off with battery connected                                          | Failing super capacitor                                                         | Try **disabling** the super capacitor before removing it (more data needed)                 |
| Battery Flashing Icon        | Incorrect battery reporting or unstable charge display                                              | Battery BMS issue, degraded battery cell                                        | Briefly short **battery + and - terminals only** to reset BMS (**do not touch middle pin**) |
| Black Screen + Green Light   | Power LED turns on but no display or boot                                                           | Possibly Blown backlight fuse, broken or incorrectly connected display connectors, bricked firmware, other filed motherboard problems            | Check LCD connection, test backlight, attempt recovery                                      |
| Brief Green Flash → Shutdown | PSP powers briefly then immediately turns off                                                       | Connector issues, motherboard/power/connection short, liquid damage, failing components          | Disconnect accessories and inspect board barebones outside the shell with power switch only                                                   |
| Bricked                      | Black screen with backlight but system never loads                                                  | Failed firmware install/update                                                  | Use recovery methods depending on model and CFW support                                     |

### Super Capacitor Disable / Removal Outcomes

#### Positives

* Stops passive battery drain caused by failed capacitor
* PSP may begin charging normally again
* System may start accepting external power again

#### Negatives

* PSP may stop functioning entirely (could be user error, motherboard stress or prolonged capacitor failure leaking/shorting stressing the power/charging IC)
* Charging IC may already be damaged
* Can introduce unusual power behaviors, example:
  * Charges but does not boot unless battery is removed first, etc
---

# Storage / Memory / Firmware

| Issue                                      | Symptoms                      | Possible Causes                                                       | Possible Fix                                             |
| ------------------------------------------ | ----------------------------- | --------------------------------------------------------------------- | -------------------------------------------------------- |
| Memory Stick Not Reading correctly                | Memory card not detected or not formating     | Dirty contacts, damaged slot, fake card, defective MicroSD adapter, card larger than 128gb    | Clean contacts, adjust pins if bent, test another adapter/card                |
| VSH / Extra Menu / Custom Launcher Missing | Missing ARK-4 features        | Older ARK-4 revision with missing ARK_01234                                                 | Ensure `ARK_01234` savedata from `ARK4.zip` is installed |
| Games Black Screen / Shutdown / Crashing   | Games fail to launch or crash | Corrupt files, Inferno cache issues, fake memory card, faulty adapter, wrong or old or faulty plugin running in the wrong place | Verify storage, disable plugins, reinstall affected files              |

---

# Controls / Input

| Issue                           | Symptoms                                       | Possible Causes                                              | Possible Fix                           |
| ------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | -------------------------------------- |
| Stuck Trigger Buttons           | Triggers feel stuck or register inconsistently | Worn membranes (1000), worn ribbon (2000/3000/E1000) | Add spacers or replace membrane/ribbon |
| Analog Stick Drift              | Movement without touching analog               | Poor contact, calibration issues, worn analog assembly, (drift without analog is normal behavior)     | Clean, reseat, adjust pressure, install originl faceplate if shell swapped       |
| Power Switch Not Working        | Switch movement does nothing                   | Ribbon damage, shell misalignment, failed switch board       | Inspect switch lever alignment, possibly bad aftermarket shell   |
| Wireless Switch Not Working     | WLAN toggle not detected                       | Broken switch, damaged board, broken plastic lever           | Inspect switch and lever                |
| PSP 1000 D-Pad Feels Pressed    | D-Pad lacks click or feels soft                | Torn or worn membrane                                        | Replace membrane, could also be cheap aftermarker shell swap                       |
| Square Button Overhang | Uneven button feel or sensitivity              | Original Sony design limitations, worn parts                 | Use original components where possible |

---

# Display / Screen

| Issue                             | Symptoms                       | Possible Causes                          | Possible Fix                                                                 |
| --------------------------------- | ------------------------------ | ---------------------------------------- | ---------------------------------------------------------------------------- |
| PSP 2000 Vertical Lines           | Persistent vertical artifacts  | LCD failure, poor connection, possible failing GPU             | Replace display                                                    |
| Yellowing Screen                  | Uneven yellow tint             | Age, environmental conditions            | Replace with healthy original LCD, install IPS, or run white screen at max brightness for 8+ hours to reduce effects |
| Screen Replacement Quality Issues | Poor colors, DoA | Low-quality aftermarket LCD              | Refund poor panels and use original LCD (`LX01/LX02/LX03`) or IPS            |
| Screen Dust                       | Dust under display             | Worn foam gasket, internal contamination | Deep clean + replace foam gasket or install laminated IPS                                          |
| Black Screen         | Black screen but can see something when shining a light                   | Blown Fuse              | Replace fuse or bridge it (not recommended but could work)                      |

---

# Audio

| Issue                     | Symptoms                              | Possible Causes                              | Possible Fix                                               |
| ------------------------- | ------------------------------------- | -------------------------------------------- | ---------------------------------------------------------- |
| Stuck Headphone Mode      | Audio only outputs through headphones | Stuck headphone jack sensor leaf pin                  | Carefully insert a trimmed cotton swab, wiggle inside the headphone jack to try and free the sensor |
| Crackly / Distorted Audio | Rattling or poor sound quality        | Dirty speaker, liquid damage, missing gasket | Clean or replace speaker                                   |

---

# UMD

| Issue                       | Symptoms                    | Possible Causes           | Possible Fix                      |
| --------------------------- | --------------------------- | ------------------------- | --------------------------------- |
| UMD Not Running             | Disc does not spin/read     | Drive or laser fault, dirty      | Inspect drive assembly            |
| UMD Drive Noisy             | Loud Noises when in use    | Dirty mechanics      | Disassemble, clean, lubricate            |
| UMD Preventing Boot         | PSP hangs during startup    | Faulty UMD sensors        | Test boot with drive disconnected |
| UMD Disc Breaking           | Disc shell separation       | Shell removed incorrectly | Super glue shell or replace shell |
| PSP 1000 UMD Door Not Flush | Door does not sit correctly | Mechanical misalignment   | Realign hinges and shell          |

---

# Connectors / Hardware Repair

| Issue                               | Symptoms                      | Possible Causes                               | Possible Fix                                   |
| ----------------------------------- | ----------------------------- | --------------------------------------------- | ---------------------------------------------- |
| Broken ZIF Connector                | Ribbon cable not securing     | Ribbon inserted incorrectly and force closed | Replace connector or add a piece of tape ontop of the hard part of the ribbon and carefully feed inside to restore pressure, then tape over to stop from losening                              |
| Media Buttons Stuck or Constantly Pressed                 | Buttons stop registering or stuck in pressed state     | Damaged ribbon                                | Replace media ribbon                                 |
| Wrong Screwdriver / Stripped Screws | Damaged screw heads           | Low quality, incorrect or faulty screw driver, skipping and user continues to try unscrewing thus stripping the screw head                               | Use quality **PH0 / Phillips 1.2** screwdriver |
| Shell Swapping Troubles             | Poor fit or alignment         | Low-quality aftermarket shell                 | Adjust fitment or use original shell / parts          |
| Memory Card Slot Problems                    | Storage realted failures              | Bent, dirty, broken, or corroded pins         | Disassemble and inspect slot, adjust bent pins, clean, and if missing a pin, replace slot                |

---
