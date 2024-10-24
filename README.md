# RyuuBoostLED-RE <img src="https://media.tenor.com/DNrK4vqeOzwAAAAM/atom-hydrogen-atom.gif" width="40" height="40">

### Overview 
This project involves reverse engineering the RyuuBoost Dispo vape to access and customize its LED display, as well as exploring potential firmware modifications through the USB-C port. The goal is to customize the onboard images and reset internal counters for reuse.

# Disclaimers/Hazards
Disposable vapes generally use Li-ion batteries without any protection circuitry. Short circuits could dissipate uncontrolled amounts of power, causing personal injury and/or property damage. Any work done on these vapes is done at your own risk.

It has been determined that there are multiple circuit revisions of these vapes, which may have incompatibilities that could result in device damage if versions are mismatched. Verify connections and firmware compatibility before proceeding with any modifications.

Additionally, vape juice/"e-liquid" can contain high concentrations of nicotine, which is absorbed through skin. Handling of the vape's internals should be done with gloves until the internal parts are cleaned of juice and/or residue.

### Tools

**ST-Link V2 / J-Link Debugger**
   - Hardware debuggers used for reading and writing to the microcontroller's internal Flash memory via the SWD (Serial Wire Debug) interface. This allows extraction of the firmware and uploading modifications.

**Ghidra / IDA Pro**
   - Software tools for decompiling the firmware dump extracted from the microcontroller. These tools help analyze and understand the assembly code for reverse engineering purposes.

**FlashROM / SPI Programmer**
   - Tools used to read and write to the external SPI NOR Flash memory, which contains images and usage counters. This allows for modifying the data displayed on the LED screen.

**Python**
   - Custom scripts (e.g., `split-flashdump.py`, `assemble-flashdump.py`) for splitting and reassembling the external Flash memory to modify image assets. Tools like **Rinky-Dink Electronics' ImageConverter565** can be used to convert images into a format compatible with the vape's display.

**OpenOCD / ST-Link Utility / J-Link Commander**
   - Software to interface with the SWD debugger, allowing you to interact with the microcontroller's internal memory and firmware through USB-C or SWD pins.

### Disclaimer
This project involves hardware modification, including working with Li-ion batteries. Be cautious of safety hazards and ensure proper handling to avoid damage or injury.
