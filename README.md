# EasyScartPCB
A simplified SCART cable PCB optimized for US modded TVs and hand soldering

### Summary
This is a fork of [screwbreaker/ScartPCB](https://github.com/screwbreaker/ScartPCB) designed for SCART modding on US-market TVs. Since these TVs don't use the +12V auto-switch or aspect ratio signal (SCART pin 8), this design removes the unnecessary boost converter and optimizes for easier hand assembly and part sourcing.

### Key Improvements
- **Hand-solder friendly**: All 0805 components (no tiny 0402 parts)
- **Better component sourcing**: Single package "B" tantalum 220µF/6.3V for decoupling instead of multiple MLCCs
- **Simplified buffer**: Single 74LVC1G17 instead of two transistors
- **Complete grounding**: All SCART ground signals properly connected
- **Removes unnecessary boost converter**: US TVs don't need the +12V signal


### How It Works
The PCB is modular – use 0Ω resistors as jumpers to enable/disable signals as needed:

**CSYNC Buffer**: The 74LVC1G17 buffer is specifically for Genesis/Mega Drive systems. Genesis outputs a TTL-level CSYNC that loses voltage when loaded by the 470Ω series resistor and 75Ω termination resistor. The buffer maintains +5V for proper sync detection. Close the NOBUF jumper to bypass if not needed.

**RGB Signals**: Use 0Ω resistors to pass through or add 75Ω termination resistors as needed.

**Jumpers**: NOBUF (bypass CSYNC buffer), MONO (mix left/right audio), RGB (enable blanking signal).

### PCB Details
4-layer board designed to fit inside standard SCART connectors. All components are 0805 or larger for easy hand soldering.


### 3D-Printed Cable Gland
SCART connector cable glands are notoriously brittle, so this project includes a 3D-printed replacement that's more durable.

![SCART_cable_gland](https://github.com/screwbreaker/ScartPCB/blob/main/Pictures/SCART_cable_gland.jpg?raw=true)

### License
The PCBs are under the CERN OHL license. This is an open project – improvements and contributions are welcome.

